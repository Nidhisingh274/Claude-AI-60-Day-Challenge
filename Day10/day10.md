# Personal Portfolio Website - Day 10

Welcome to my personal portfolio! This project was built as part of the **ABTalks 60 Days Coding Challenge**. The goal was to create a modern, responsive, and professional portfolio website to showcase my skills, projects, and professional background.

## 🚀 Live Demo
https://tranquil-florentine-a1f828.netlify.app/

## 📸 Screenshots

<img width="1880" height="897" alt="aa" src="https://github.com/user-attachments/assets/df7fcd53-8bb4-495b-8239-ed594751bcfa" />

## 💡 Key Learnings
Building this portfolio helped me understand:
- **Personal Branding:** How to effectively communicate my professional value proposition.
- **Modern UI Design:** Utilizing Tailwind CSS via CDN for rapid, responsive, and minimalist styling.
- **Constraint-Based Development:** Working with strict rules (privacy, specific text requirements, and structural limitations) to achieve a precise output.
- **Frontend Basics:** Understanding the structure of a single-file HTML application with integrated Tailwind and vanilla JS.

## 🛠 Tech Stack
- **HTML5 & Tailwind CSS** (via CDN)
- **Vanilla JavaScript** (for interactivity and dark/light mode toggle)

## 📋 The Prompt Used
To generate this portfolio, I used the following customized prompt:

```text
You are an expert full-stack web developer and personal branding designer.

Build a complete, modern, single-file personal portfolio website using HTML, Tailwind CSS (CDN), and vanilla JavaScript.

=== CRITICAL RULES & CONSTRAINTS ===
1. STRICT EXPERIENCE ACCURACY: If extracting from a resume, keep the experience exactly as "~2 years" or "nearly 2 years". DO NOT hallucinate or change this to "2+ years" under any circumstances.
2. STRICT PRIVACY & CONTACT SECTION: DO NOT include any email addresses, phone numbers, or physical addresses anywhere in the code. 
3. NO CONTACT FORM: Do NOT build a functional or dummy input form (Name, Email, Message). Instead, the "Get In Touch" section must only feature a stylized, prominent button linking to LinkedIn for direct messaging.
4. EXACT CONTACT TEXT: The text in the contact section MUST exactly read: "Open to full-time Gen AI, Agentic AI, and AI Engineer roles, as well as research collaborations. Drop me a message on LinkedIn." Do NOT mention freelance work.
5. NO JSX/RAW CODE IN HTML: Render all "Tech Tags" (like RAG, LangChain, etc.) as pure, static HTML elements (e.g., `<span class="bg-blue-600 text-white px-3 py-1 rounded-full text-sm">RAG</span>`). The UI must be clean with no raw JavaScript array methods like `.map()` visible on the screen.

=== PERSONAL INFO ===
Name: [Your Name]
Title: [e.g., 'Data Science Enthusiast | GenAI Builder']
Location: [City, Country]
Email: [email]
LinkedIn: [URL]
GitHub: [URL]
About: [2-3 sentences about yourself]

=== SKILLS ===
Technical: Python, RAG, LangChain, LangGraph, LLMs, OpenAI API, Hugging Face, Groq, FAISS, Ollama, FastAPI, MySQL, Agentic AI, Prompt Engineering, Machine Learning
Tools: Langsmith, VS Code
Soft Skills: Analytical Thinking, Cross-domain Adaptability, Technical Documentation

=== PROJECTS ===
1. [Project Name] — [1 line description] — Tech: [stack]
2. [Project Name] — [1 line description] — Tech: [stack]
3. [Project Name] — [1 line description] — Tech: [stack]
=== EXPERIENCE & ACHIEVEMENTS ===
- [Internship / Hackathon / Certification]
- [Award / Rank / Notable achievement]

=== DESIGN PREFERENCES ===
Mode: Dark/Light toggle
Style: Modern, minimal, premium
Colors: Deep Purple and Tech Blue accents
Font: Clean sans-serif display font

=== REQUIREMENTS ===
Include these sections:
- Hero (name, title, typing animation, social links)
- About Me
- Skills (Static, styled HTML tags/pills)
- Projects (cards with static tech tags)
- Achievements & Certifications
- Contact (Text specified above + LinkedIn Button ONLY)
- Dark/Light mode toggle
- Mobile responsive
- Smooth scroll animations
- Active nav highlighting
- Single HTML file, no build step
- Tailwind via CDN
- SEO meta tags included

Optional:
- If a resume is uploaded, extract details automatically but keeping the above instructions in mind.
- If a profile photo is uploaded, use it in the portfolio.
- Generate recruiter-friendly content and project descriptions from resume data.

Return ONLY the complete HTML code. Do not include any markdown formatting or explanations outside the code block.
