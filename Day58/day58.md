# Day 58: Testing, Debugging & Production Optimization (MedGuide AI - Day 8)

**Project Repository:** [https://github.com/Nidhisingh274/medguide-ai]

## 📝 Prompt Used Today
```
Day 8: Testing, Debugging & Production Optimization

Today is Day 8, continuing our chat from the previous days.

If you've forgotten the project or no longer have enough context, ask me to upload the 10-Day Blueprint (Sprint Workbook) before continuing. Use it as the source of truth.

Review everything built so far, then complete only the work scheduled for Day 8 in the Sprint Workbook. Do not redesign the project or begin tomorrow's work.

Use only free tools, APIs, SDKs, hosting platforms, and services unless the Sprint Workbook explicitly specifies otherwise. Prefer free-tier solutions such as Gemini API, Supabase, Firebase, Vercel, Netlify, Render, Railway, or equivalent free alternatives.

Assume I have zero technical experience unless I tell you otherwise.

Whenever I need to perform a manual step (running tests, configuring services, deploying, installing packages, etc.), stop and give me exact step-by-step instructions using the real button names, menu names, and terminal commands.

Prioritize implementation over explanation. Keep explanations concise and spend most of your response generating production-ready code and complete files.

Build today's work one milestone at a time.

For each milestone:

1. Briefly explain what we're testing or improving and why.
2. Show every file that needs to be created, modified, or deleted.
3. Generate the complete final contents of every required file. Never generate snippets, placeholders, TODOs, "...existing code...", or "add this below..." instructions.
4. Clearly state where each file belongs and whether it is new or replaces an existing file.
5. If you provide the implementation as a downloadable ZIP because the project is too large to fit comfortably in chat, also explain exactly how to use it. Tell me where to extract it, which files replace existing ones, which files are new, any commands I should run afterward, and how to verify everything was applied correctly.
6. Provide every command I need to run.
7. Pause only after major testing milestones, deployments, or when debugging requires my input.
8. If anything breaks, help me debug it completely before moving forward.

Continue across as many responses as necessary until every Day 8 task in the Sprint Workbook has been successfully completed and verified.

Before writing any code, perform a complete review of the project like a Senior QA Engineer, Senior Software Engineer, Security Reviewer, and Performance Engineer.

Look for and fix issues such as:

* Bugs and broken functionality
* Edge cases
* Error handling
* Form validation
* API failures
* Loading, empty, and offline states
* Responsive design issues
* Accessibility improvements
* Performance bottlenecks
* Duplicate or unnecessary code
* Security concerns appropriate for this project
* Console warnings and runtime errors
* Production-readiness issues

Do not introduce unnecessary new features. Focus on making the existing application stable, reliable, and production-ready.

When today's implementation is complete:

* Perform a complete end-to-end walkthrough of the application.
* Verify every planned feature works correctly.
* Verify there are no obvious runtime errors.
* Deploy the latest version if changes were made.
* Ask me to test the live application and share screenshots or any issues I encounter.
* Update any affected documentation.
* Help me commit and push today's work to GitHub with a meaningful commit message.
* Finish with a concise summary of everything improved today and what remains before launch.

Your goal is not simply to fix bugs. Your goal is to ensure the application is stable, reliable, polished, and ready for launch. Never optimize for brevity. Optimize for helping me successfully complete today's implementation.

Conduct a comprehensive release-readiness review. Assume the application will be launched publicly tomorrow. Continue reviewing, testing, debugging, and optimizing until you are confident you would personally approve this release.

Do not stop after finding a few issues.

Continue looking for additional bugs, UX problems, performance bottlenecks, security concerns, accessibility issues, edge cases, production risks, and code quality improvements until you are satisfied no major improvements remain.
```

## 🐛 Issues Found & Fixed Today
During our QA and Security review, identified and resolved 11 production risks:
1. **Missing Error Handling in Retrievers:** Wrapped `search_guidelines()` and `check_labs()` in try-except blocks to prevent app crashes if Chroma DB or CSVs fail to load.
2. **Silent Zero Bug (Trickiest Bug):** Streamlit defaulted empty number inputs to `0.0`, causing false "LOW" lab flags. Fixed by enforcing `value=None` and adding form validation warnings.
3. **Transient LLM Routing Errors:** Router failures used to silently skip guideline searches. Now, ambiguous responses safely default to `True` (always search).
4. **Performance Bottleneck:** `validate_labs()` read the CSV from the disk on every call. Fixed by globally caching the reference table at import time.
5. **XSS / HTML Injection Risk:** Unescaped PDF text was injected via `unsafe_allow_html=True`. Mitigated by running all extracted text through `html.escape()`.
6. **Generic Error Messages:** Upgraded generic LLM errors to specifically identify Rate Limit (HTTP 429), Auth/API Key (HTTP 401), and Network Timeout issues.
7. **Unpinned Dependencies:** Completely pinned `requirements.txt` to exact local working versions to prevent future deployment breakages.
8. **Accessibility Failures:** Step-pill and footer text failed WCAG AA 4.5:1 contrast ratios. Fixed by adjusting to darker teal shades (`#015A64` and `#4F6863`).
9. **Stale GitHub README:** Replaced the default GitHub repository placeholder with a complete, production-ready `README.md`.
10. **`.gitignore` Hygiene:** Removed `chroma_store/` from `.gitignore` as it was deliberately committed in Day 7.
11. **Mid-word Excerpt Hyphenation:** Logged as a known PDF-source artifact. Explicitly bypassed as fixing it required disproportionate NLP dehyphenation logic.

## 📸 Screenshots

**1. Happy Path Walkthrough**

<img width="547" height="866" alt="happy_path" src="https://github.com/user-attachments/assets/60a5ad5c-a7a1-4b3f-923a-55177ccbca03" />

**2. Blank Value Validation Warning (Edge Case Fixed)**

<img width="836" height="862" alt="blank_value_warning" src="https://github.com/user-attachments/assets/418e417f-0d6b-4456-9ac9-4f03fdabaf5b" />

**3. Empty Question Error Handling**

<img width="840" height="861" alt="empty_question" src="https://github.com/user-attachments/assets/5cdb7c17-0ebd-4cca-b448-c697de025607" />

## 📋 DAY8-SUMMARY.md
I have uploaded the complete summary generated by Claude as a separate file. 
👉 **[Click here to read the full DAY8-SUMMARY.md](./DAY8-SUMMARY.md)**

## 🧠 Key Learnings
1. **Never Trust Defaults:** Streamlit’s default behavior of assigning `0.0` to empty number inputs is a major logical risk in healthcare apps. Explicitly defining `value=None` and validating user inputs is critical to avoid dangerous false positives.
2. **Security in RAG Pipelines:** Extracted text from PDFs is fundamentally "user input" and shouldn't be trusted blindly. Rendering it directly into a frontend using `unsafe_allow_html=True` creates massive XSS vulnerabilities. Always sanitize using `html.escape()`.
3. **Accessibility is Non-Negotiable:** A UI might look beautiful, but if it fails the WCAG 4.5:1 contrast ratio, it is unusable for many. Small tweaks in hex codes can make an app completely accessible without ruining the design aesthetic.
4. **Pinning Requirements Saves Lives:** A deployed app can break overnight without a single code change if `requirements.txt` is unpinned and a library releases a breaking update. Hard-pinning versions ensures stability.
