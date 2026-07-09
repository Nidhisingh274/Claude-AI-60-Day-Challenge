# Day 39 — Build PDF Splitter & Merger (Premium Browser-Based PDF Utility)

## 🎯 What I Built
A **premium, single-page, browser-based PDF Splitter & Merger** — a self-contained `.html` file that runs entirely client-side. No file ever leaves the browser; all splitting and merging happens locally using JavaScript PDF libraries (`pdf.js` for page previews, `pdf-lib` for splitting/merging, `JSZip` for multi-file downloads).

The generated single-page app - `pdf-splitter-merger.html`

### Core Features
**PDF Splitter**
- Upload a PDF, auto-detect total pages, view thumbnail previews of every page
- Split by custom page ranges / shorthand (e.g. `1-3, 5, 8-10`)
- Split every N pages
- Split after specific page numbers (click the scissors icon between thumbnails, or type page numbers)
- Click-to-select pages and extract them as a new file
- Build multiple output files in one "Output Plan" before processing, with live validation of invalid/empty ranges
- Downloads a single PDF, or a `.zip` when multiple output files are generated

**PDF Merger**
- Drag-and-drop or browse to upload multiple PDFs
- Sortable file list with drag-to-reorder, page count, and thumbnail preview per file
- Live summary: total files, total pages, estimated output size
- Merges files in the chosen order into one downloadable `merged.pdf`

**Polish**
- Dark mode toggle, keyboard shortcuts (`?` for shortcuts panel, `Alt+1/2` to switch tools, `Ctrl+Enter` to run, `Ctrl+O` to browse, `Ctrl+D` for dark mode)
- Drag-and-drop uploads, loading/progress indicators, toast notifications, accessible focus states and ARIA roles, fully responsive layout

---

## 🧠 The Prompt I Used

> You are an expert UI/UX designer, frontend developer, document processing specialist, and JavaScript engineer.
> Before generating anything, ask the user the following question.
> 1. Would you like Claude to automatically design the application, or would you like to customize its features?
> If the user chooses customization, ask which additional PDF features they would like included.
> After collecting the response, generate a premium single-page interactive HTML application called 'PDF Splitter & Merger'.
>
> **PDF Splitter:**
> Allow users to upload a PDF and automatically detect the total number of pages. Display visual page thumbnails for every page and allow users to preview the document before splitting. Users should be able to split the PDF by entering page numbers, selecting custom page ranges, splitting after specific pages, splitting every N pages, or extracting selected pages into one or more new PDF files. Allow users to create multiple split ranges in a single operation, validate all page ranges, preview the resulting document structure before processing, and clearly highlight invalid inputs.
>
> **PDF Merger:**
> Allow users to upload multiple PDF files using drag-and-drop or file selection. Display all uploaded files in a sortable list with page counts and visual previews. Users should be able to reorder the PDFs using drag-and-drop before merging. Display the total number of files, total page count, and estimated output before generating the merged document. Generate the merged PDF and provide an easy download option.
>
> Perform all PDF processing entirely within the browser using client-side JavaScript. Do not upload files to external servers or rely on backend services. Use reliable browser-compatible libraries where necessary and ensure the application continues to work offline after the initial page load.
>
> Include drag-and-drop uploads, processing indicators, loading animations, responsive layouts, dark mode, accessibility features, intuitive error handling, keyboard shortcuts where appropriate, and smooth micro-interactions throughout the application.
>
> Generate everything as a single self-contained HTML file using HTML, CSS, and JavaScript only.
> Design the interface as a polished commercial application comparable to professional PDF utilities, with exceptional UI/UX, beautiful typography, modern layouts, smooth animations, intuitive navigation, and an experience users would genuinely choose over existing online PDF tools.

**Claude's interview question, and my answer:** Claude asked whether I wanted it to auto-design the app or let me customize the feature set. I chose **auto-design**, and Claude proceeded to generate the full application in one pass.

---

## 🧪 How I Tested It
1. Opened the generated `pdf-splitter-merger.html` file locally in the browser (double-click, no server needed).
2. **Splitter test:** Uploaded `Attention is all you need.pdf`, previewed all pages as thumbnails, used **Split every N pages** to break it into two files: `Attention is all you need part 1.pdf` (pages 1–12) and `Attention is all you need part 2.pdf` (pages 13–15).
3. **Merger test:** Uploaded both split files back in, reordered them, and merged them into `merged.pdf` — confirmed the content matched the original document.
4. Verified dark mode, keyboard shortcuts, drag-and-drop, and error handling (invalid ranges, non-PDF files) all worked as expected.

---

## 📸 Screenshots

<img width="1872" height="814" alt="split-interface" src="https://github.com/user-attachments/assets/e8775192-95f5-4b41-a60e-0b2e37b142a7" />

<img width="1881" height="1986" alt="page selection-for-splitting" src="https://github.com/user-attachments/assets/7921916c-7517-49c3-934e-8d3d8e59c142" />

<img width="1832" height="1956" alt="split-output" src="https://github.com/user-attachments/assets/40da66e8-bd7e-4af6-98a2-2314a5c20bfc" />

<img width="1874" height="654" alt="merge-interface" src="https://github.com/user-attachments/assets/f8074747-1212-41cf-bffc-49d18cb8b973" />

<img width="1864" height="980" alt="merge-output" src="https://github.com/user-attachments/assets/364e616b-ee30-40fb-994a-6270954ce572" />

---

## 💡 Key Learnings

1. **Client-side PDF processing is genuinely production-viable.** Using `pdf.js` for rendering and `pdf-lib` for document manipulation, an entire PDF utility can run without a backend, better privacy (files never leave the device) and zero server cost.
2. **A single prompt can produce a fully working, multi-feature app** when the brief is specific about functionality (all four split modes, sortable merge list, validation, offline support), specificity in the prompt directly translates to completeness in the output.
3. **Design tokens matter even for utility software.** Treating a "boring" productivity tool with real typography, a coherent color system, and a thoughtful metaphor (scissors/perforation for splitting, paperclip/stack for merging) made it feel like commercial software instead of a generic demo.
4. **Validation and empty/error states are what separate a prototype from a usable tool.** Highlighting invalid ranges, showing clear empty states, and giving specific error messages (not generic "something went wrong") made the tool trustworthy to actually use.
5. **Real-world application:** this kind of tool is directly useful for splitting large reports/textbooks into chapters, or recombining scanned document pages, all without uploading sensitive files to a third-party website.

---

## 🔗 Prompted with Claude (Sonnet)
Built as part of the **#60DayClaudeChallenge**.
