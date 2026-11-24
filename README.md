# Paperwise — DSSSB TGT Computer Science

A single-user, local-first study and CBT practice app. It uses plain HTML, CSS, and JavaScript, so there is no build step or package installation. It is published with GitHub Pages.

## Run it

Open `index.html` in a modern browser. For a local server, run `python3 -m http.server 8000` from this directory and open `http://localhost:8000`.

## GitHub Pages deployment

The `.github/workflows/pages.yml` workflow deploys the repository root to GitHub Pages on each push to `main`. The workflow attempts to enable Pages during setup. Check the Actions tab for deployment status.

## Data and exam settings

The built-in set contains 24 **original practice questions**, not past-year questions. No PYQs or externally copied questions are bundled. On the Question bank page, import your own JSON or CSV questions. Imported PYQs carry their provided year, shift, source, and answer verification flag. Verify an answer against a final official answer key before setting `verified` to `true`.

Question JSON accepts an object with a `questions` array (or a bare array). Example:

```json
{
  "questions": [
    {
      "question": "Question text",
      "options": ["Option A", "Option B", "Option C", "Option D"],
      "answer": "B",
      "explanation": "Why B is correct.",
      "section": "Computer Science",
      "topic": "Operating Systems",
      "difficulty": "Medium",
      "source": "Official paper / URL",
      "sourceType": "pyq",
      "year": 2025,
      "shift": "Shift 1",
      "verified": false,
      "sourceRef": "Official final answer-key reference"
    }
  ]
}
```

CSV headers: `id,question,options,answer,explanation,section,topic,difficulty,source,sourceType,year,shift,verified,sourceRef`. Separate the four options with `|`. Answers can be `A`–`D` or `0`–`3`. Import validates the basic question shape and flags. PDF/image OCR is not built in; extract and check the question text and answer key before importing structured data.

Attempts, settings, notes, bookmarks, revisions, and imported questions persist in this browser's local storage. Use **My progress → Back up my data** or **Exam & settings → Export backup** to save a JSON backup. Restore is available on the settings page. Clearing browser site data removes the local copy.

## Official exam reference and limits

The official DSSSB **Advertisement No. 06/2025**, dated **03 October 2025**, covers TGT post codes **55/25–70/25** and drawing/special education posts 71/25–72/25. Its TGT scheme states 2 hours, 200 MCQs/marks, Section A 100 questions and Section B 100 questions, with 0.25 marks deducted per wrong answer. The board's indicative syllabus index also links to a one-tier technical/teaching 200-mark syllabus. The app links to the official notice and syllabus index.

That advertisement does **not** list TGT Computer Science. As a result, the exact Computer Science post code, applicable cycle, and current syllabus version are **not confirmed** here. The scheme appears only as an editable reference. The official notice and current cycle supersede these local settings. The simulator can only present questions in the local question bank; the 24 seed questions are insufficient for a real 200-question mock. It uses each available question once and tells you how many are available. Import a sufficiently large, checked question bank for a full-length simulation. No outcome or score is guaranteed.

## Current scope

Included: responsive dashboard, study history, topic/section performance, evidence-based next-step prompts after enough attempts, section/topic/wrong/daily/custom practice, timed simulation, response states and palette, confirm/automatic submission, answer review, notes, bookmarks, revision queue, configurable sections/marking/timing/goals, local persistence, and backup/import.

The app is a single-user browser build; cloud sync, account login, OCR, and automatic official notice updates are not included.
