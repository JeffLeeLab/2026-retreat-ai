# Spec: My academic website

## What this document is

This is a **specification** — a plan that you (the human) and the AI write *together* before any code exists. The AI reads this whole file before building anything. A good spec means fewer wrong guesses, less back-and-forth, and a site that's actually yours.

Blanks marked **`➡️ YOUR TURN`** are for you to fill in. You don't have to fill them all in by typing — you can also just ask the AI to interview you and fill them in as you talk.

---

## 1. Instructions to the AI

**AI, read this section carefully. These rules govern how you work, not just what you build.**

1. Before writing any code, read this entire file **and** `docs/cv.json`.
2. If any `➡️ YOUR TURN` blank below is still unfilled, or anything here is ambiguous, **do not guess — stop and ask the user**. Ask one question at a time, in plain language, offering options where helpful.
3. While building, keep consulting: if you're about to make a decision the spec doesn't cover ("I'm thinking of a sticky navigation bar — want that?"), check with the user first. This is a conversation, not a one-shot job.
4. Build in small steps. After each significant change, tell the user to refresh their Live Server preview and ask what they think before moving on.
5. All content comes from `docs/cv.json`. Never hard-code the user's name, papers, or dates into the HTML — if it's in the JSON, read it from the JSON.

---

## 2. Whose site is this?

- **Name:** `➡️ YOUR TURN`
- **Role / one-line pitch:** `➡️ YOUR TURN` (e.g. "PhD student who makes neurons glow and slay")
- **Main audience:** `➡️ YOUR TURN` — who do you most want to impress? (a hiring committee? future collaborators? funders? your mum?) This should shape what's biggest and first on the page.

---

## 3. Site structure

Default sections, top to bottom. Cross out what you don't want, reorder, or add your own:

- [x] **Hero** — name, role, blurb, photo/image, links
- [x] **Research highlights** — the publications marked `"highlight": true`, given room to shine
- [x] **Positions** — career history from the `positions` list
- [x] **Publications** — the full list, with DOI links
- [ ] **Talks**
- [ ] **Skills**
- [x] **Contact / footer** — email and links

**Changes to the default:** `➡️ YOUR TURN` (or write "defaults are fine")

---

## 4. Look & feel

This is where you get to be creative. There are no wrong answers — brutalist, terminal-green-on-black, glossy magazine, hand-drawn sketchbook, 1990s Geocities, Swiss minimalism. The AI is very good at CSS; make it work for its supper.

- **Three mood words for the site:** `➡️ YOUR TURN` (e.g. "calm, precise, warm" or "loud, weird, unforgettable")
- **Colours:** `➡️ YOUR TURN` — name a palette, paste hex codes, or write "AI: propose three palettes and let me pick"
- **Typography feel:** `➡️ YOUR TURN` (e.g. classic serif / clean sans / monospace nerd)
- **Light, dark, or both with a toggle?** `➡️ YOUR TURN`
- **A website whose vibe you admire (optional):** `➡️ YOUR TURN`
- **Anything you hate and never want to see:** `➡️ YOUR TURN` (e.g. "no purple gradients, no emoji")

### Images

- Put any images (headshot, hero banner, favourite paper figure) in the **`docs/assets/`** folder and reference them as `assets/<filename>`. One example image is already there: `assets/larval-brain-development.png` — it's wired up as the `image` field in `cv.json`, so the site can use it straight away. A few ways it could appear: a full-width hero banner behind your name, a framed image beside your blurb, a subtle dimmed page background, or the visual for your top highlighted paper. Swap the file and update the `image` field when you have your own.
- Keep files web-sized (roughly under 1 MB each) — this is a webpage, not a poster.
- Want more than one image? Add your own image fields to `cv.json` wherever they make sense, pointing at files in `docs/assets/`. For example, a `"figure"` on a publication, or a separate `"headshot"` next to the top-level `"image"`:

  ```json
  "publications": [
    { "title": "...", "figure": "assets/fig-yfp-traps.png", ... }
  ]
  ```

  The JSON is yours to extend — just list any fields you added below so the AI knows to render them (and remember rule 4 in section 6: entries *without* an image must still look fine).
- **How should images be used?** `➡️ YOUR TURN` (e.g. "my headshot in the hero", "the brain image as a full-width banner", "each highlighted paper shows its `figure`", plus any image fields you added and where they should appear)

---

## 5. One weird feature

Every CV site has a name and a publication list. Yours will have **exactly one** thing no other CV site has. Pick from the menu or invent your own:

- **Terminal CV** — the whole site is a fake command line: `ls`, `cat publications.txt`, `whoami`, `sudo hire_me`
- **Honest-CV toggle** — a switch that flips every line to what actually happened ("Awarded fellowship" → "rejected four times first")
- **Publication time machine** — drag a slider through the years and watch papers and positions appear
- **Plain-English toggle** — one switch swaps every paper title for its `plain` one-sentence summary from cv.json
- **Choose your audience** — visitor picks "I'm a PhD applicant / collaborator / funder" and the site reorders itself for them
- **Co-author constellation** — your co-authors as an interactive star map; hover to see shared papers

**My weird feature:** `➡️ YOUR TURN`

---

## 6. Technical rules (fixed — do not change these)

**AI: these are constraints, not suggestions.**

1. The entire site is **one file**: `docs/index.html`. All CSS and JavaScript live inside it.
2. It loads its data from `docs/cv.json` using `fetch("cv.json")` — see rule 5 in section 1.
3. Styling: Tailwind CSS via CDN **or** hand-written CSS in the same file. Vanilla JavaScript only — no frameworks, no build step, no npm.
4. **Degrade gracefully.** Missing field → skip that line. Empty section → hide its heading. Never show `undefined`, and never a blank page.
5. Must look good on a phone as well as a laptop.
6. Preview via the VSCode **Live Server** extension (right-click `docs/index.html` → "Open with Live Server"). Opening the file directly in a browser won't work, because `fetch()` needs a server.

---

## 7. Definition of done

- [ ] The site renders **my** cv.json (not Priya's) with no console errors
- [ ] My one weird feature works
- [ ] It looks good on a phone-width window
- [ ] Someone who has never met me understands what I do within five seconds
- [ ] It's live at my GitHub Pages URL
