# Day 20 — AuraSync: Multimodal Biometric Face Puzzle

**Challenge:** #60DayClaudeChallenge
**Task:** Build an AI Face Puzzle Game — turn your face into an interactive puzzle game
**Tool used:** Claude (Sonnet 4.6)
**Output type:** Single self-contained HTML file (no frameworks, no build step)

---

## 1. What I built

The base task asked for a face puzzle game. I took it further and designed **AuraSync: Multimodal Biometric Face Puzzle** — a dark "AI dashboard" themed
app that frames the puzzle as a biometric scan: capture your face, solve the scrambled grid, then get a (clearly fictional, clearly labeled) AI "wellness
report" once the scan completes.

Everything — HTML, CSS, and JavaScript — lives in one `.html` file. No backend, no npm install, no external JS framework. It only loads fonts from the approved
CDN (`cdn.jsdelivr.net`) and uses the Tailwind CDN script for styling, as required.

---

## 2. The base prompt

```
You are an expert front-end developer. Build me a complete, fully working face puzzle game as a single self-contained HTML file (no external dependencies
except what can load from cdnjs.cloudflare.com, cdn.jsdelivr.net, or unpkg.com).

FEATURES REQUIRED — deliver ALL of these in one complete response:

1. CAMERA ACCESS
   - On load, request webcam permission using getUserMedia()
   - Show a live video preview (front-facing camera preferred)
   - Display a 'Take Photo' button to snapshot the user's face onto a canvas

2. PUZZLE GENERATION
   - After snapshot, let the user choose difficulty: 3×3, 4×4, or 5×5 grid
   - Slice the captured face image into equal puzzle pieces
   - Randomly scramble the pieces (guarantee it is solvable)
   - Render each piece as a draggable tile at its scrambled position

3. DRAG & TOUCH GESTURE CONTROLS
   - Support both mouse drag (desktop) and touch drag (mobile/tablet)
   - When a piece is dropped onto another piece's cell, swap their positions
   - Snap pieces to the nearest grid cell on release
   - Highlight a piece with a coloured border while it is being dragged
   - Show a green border on pieces that land in their correct position

4. TIMER & MOVE COUNTER
   - Start the timer the moment the puzzle begins
   - Display elapsed time live (format: mm:ss.t)
   - Count and display total moves made
   - Show how many pieces are correctly placed out of the total

5. WIN DETECTION & RESULTS SCREEN
   - Detect automatically when all pieces are in the correct position
   - Stop the timer immediately on win
   - Show a results overlay with: final time, total moves, and difficulty
   - Save the top 5 best times to localStorage with date, time, moves, and difficulty
   - Display a leaderboard of saved best times

6. UI & POLISH
   - Clean, modern design
   - Works on desktop and mobile
   - 'Retake Photo' button
   - 'Play Again' button
   - 'New Photo' button
   - Responsive layout

TECHNICAL REQUIREMENTS:
- Single HTML file
- All CSS and JS inline
- No frameworks
- Must work in Chrome, Firefox, and Safari
- Camera must work over HTTPS or localhost
- Handle camera permission denied gracefully
- Do NOT leave placeholder comments

Output the complete HTML file in one code block. Do not truncate or summarise any section.
```

---

## 3. Workflow followed

1. Read the base task brief, then rewrote it into the phase-by-phase prompt.
2. Opened Claude (Sonnet 4.6) in a new conversation and set effort to a level suited for a long single-file build.
3. Pasted the AuraSync prompt.
4. Claude checked its frontend-design skill before writing any code, then planned the dark "AI dashboard" visual language (slate background,
   cyan/emerald neon, monospace type, scanning-reticle motif) before generating any code.
5. Generated the full HTML file: camera capture with center-crop, canvas-based slicing and solvable scramble, drag-and-drop plus touch-drag gameplay, the
   hint system with its penalty animation, the laser-scan win sequence, the wellness report modal, and the leaderboard/control buttons.
6. Claude unit-tested the trickiest logic in a sandboxed Node environment before handing off the file:
   - confirmed every scramble is a valid permutation and is (almost) never pre-solved,
   - confirmed the hint logic never highlights the same tile twice,
   - confirmed `mm:ss.t` timer formatting is correct at edge cases.
7. Saved the file as `aurasync.html`.
8. Opened it in the browser, granted webcam permission, and played through all three difficulty levels to confirm:
   - the 1:1 crop produces an undistorted square photo,
   - drag/drop (desktop) and touch-drag (mobile emulation) both swap tiles correctly,
   - the "Agent Co-Pilot Hint" button adds exactly 5 seconds and flashes the two genuinely-swappable wrong tiles,
   - the board locks and the laser-scan animation plays exactly once at 100%,
   - the wellness report shows 3 random indicators with animated confidence bars and a protocol list, with the disclaimer clearly visible,
   - "Re-Scan Same Subject", "New Subject Capture", and "Wipe System Data" all behave as named,
   - the top-5 leaderboard persists across reloads via `localStorage`.

---

## 4. Features delivered

- [x] Webcam capture via `getUserMedia()` with graceful permission-denied handling
- [x] Live video preview inside a CSS scanning-reticle/crosshair frame
- [x] 1:1 center-crop of the captured frame before slicing (no stretched faces)
- [x] "Initiate Biometric Capture" snapshot button
- [x] Difficulty selection: 3×3 / 4×4 / 5×5
- [x] Canvas-based image slicing into equal tiles
- [x] Guaranteed-solvable scramble (free-swap mechanic, so every permutation is solvable by construction — no sliding-blank parity constraint)
- [x] Mouse drag-and-drop (desktop) and custom touch-drag (mobile/tablet)
- [x] Snap-to-grid swap on drop, dragged-piece highlight, green border on correct placement
- [x] Live timer (`mm:ss.t`), move counter, correct-pieces counter (`x/N`)
- [x] **Agent Co-Pilot Hint** — flags two genuinely swappable wrong tiles, adds exactly **+5s** to the timer with a floating red penalty animation
- [x] Auto win-detection at 100% match, instant timer stop, board lock
- [x] 3-second CSS laser-scan animation with "Grid Synchronized. Analyzing Facial Topography & Wellness Indicators..." overlay text
- [x] **Biometric Wellness Report** modal with red/yellow non-clinical disclaimer, 3 randomly-selected indicators with animated confidence-score
      progress bars, a "Recommended Protocol" list, and final stats (time / moves / difficulty)
- [x] Top-5 leaderboard in `localStorage` (date, time, moves, grid size), shown inside the report modal
- [x] **Re-Scan Same Subject**, **New Subject Capture**, and **Wipe System Data** (danger button with confirmation) controls
- [x] Fully responsive dark "AI dashboard" theme throughout

---

## 5. Results

| Metric | Value |
|---|---|
| Fastest completion time | 00:20.5 |
| Difficulty played | 3×3 |
| Total moves on best run | 8 |
| Hints used on best run | 0 |
| Browsers tested | Chrome (desktop) |

---

## 6. Screenshots

<img width="1697" height="876" alt="capturing" src="https://github.com/user-attachments/assets/c6169db1-e4a4-409a-9d76-39921203d447" />

<img width="1197" height="832" alt="puzzle" src="https://github.com/user-attachments/assets/6630f9fc-e6c9-4bdb-a098-19931b5ea1f8" />

<img width="696" height="767" alt="report" src="https://github.com/user-attachments/assets/e426aa98-0dfa-4f14-a8bf-5cac97708e45" />

---

## 7. Key learnings

- **A themed prompt produces a themed product.** Naming the app "AuraSync," giving the hint button an in-world name ("Agent Co-Pilot Hint"), and writing
  the scan overlay copy myself ("Grid Synchronized. Analyzing Facial Topography & Wellness Indicators...") made the output feel like a designed product
  rather than a generic puzzle demo — that voice has to be specified, it doesn't emerge from a plain feature list on its own.
- **A simulated AI report needs an explicit, prominent disclaimer.** I asked for the red/yellow "Probabilistic AI wellness analysis. Not a clinical
  medical diagnosis" notice up front in the spec, precisely because the feature simulates medical-adjacent language with randomized numbers — being
  explicit about the disclaimer in the prompt meant Claude treated it as a non-negotiable UI element, not an afterthought.
- **"Guaranteed solvable" needs a real mechanism, not just a comment.** Because this puzzle uses free drag-to-swap (any tile can swap with any tile) rather
  than a classic sliding-blank mechanic, every permutation is solvable by definition — there's no parity constraint to fight. Worth understanding the
  math before asking for a "guarantee" so the implementation isn't just decorative.
- **1:1 cropping matters more than it looks.** Webcams default to wide aspect ratios; without an explicit center-crop step before slicing, every puzzle
  tile comes out visibly stretched and the final face looks distorted even when solved correctly.
- **Penalty and reward feedback (the +5s float, the green correct-border, the locked board on win) are cheap to spec explicitly and easy to miss if you
  only describe the core mechanic** — they're what makes the game feel finished.
- **Asking Claude to self-verify the trickiest logic pays off.** Having it sandbox-test the scramble generator, the hint-targeting logic, and the timer
  formatter before delivery caught edge cases a single visual playtest could have missed.

---

## 8. Try it yourself

- **Live demo:** https://neon-duckanoo-903670.netlify.app/

Requires a webcam and a browser with HTTPS or `localhost` (camera access will not work over plain HTTP on a remote host).
