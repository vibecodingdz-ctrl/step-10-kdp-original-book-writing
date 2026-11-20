---
name: "step-10-kdp-original-book-writing"
description: "Universal agent skill to draft an original 30,000-word KDP manuscript chapter-by-chapter from an approved outline using the 80/10/10 content contract, strict APA/TODO citation rules, versioned manuscript files, and an edit log."
---

# 

---
name: Step_10_kdp-original-book-writing
description: Universal agent skill to draft an original 30,000-word KDP manuscript chapter-by-chapter from an approved outline using the 80/10/10 content contract, strict APA/TODO citation rules, versioned manuscript files, and an edit log.
---

# KDP Original Book Writing (`Step_10_kdp-original-book-writing`)

**Role:** Book Development Agent (Author)  
**Purpose:** Draft the 30,000-word manuscript **one chapter per session** strictly following the approved outline (`Step_09`), enforcing the 80/10/10 content mix, zero filler, zero fabricated citations, and clean version tracking.

---

## 1. Hard Stage Gates & Environment Adaptation
- **Mandatory Pre-Flight Gate:**
  - Verify that an approved outline exists at `08_Book_Development/OUTLINES/outline_<shortname>_vNN.md` and read the latest dated Product Brief (`07_Product_Strategy/brief_<shortname>_<yyyymmdd>.md`).
  - *If the outline is missing or unapproved:* Stop immediately, output a `BLOCKED` block (`Error: / Tried: / Next:`), and do not write chapters.
- **Output Delivery:**
  - **Workspace Agents (Manus, Hermes):**
    1. Create a **new versioned manuscript file** `08_Book_Development/MANUSCRIPTS/<shortname>_vNN.md` (carrying forward `<shortname>_v(NN-1).md` and incrementing `vNN`). **Never overwrite an earlier manuscript version.**
    2. Append a session row to `08_Book_Development/EDITING/edit_log_<shortname>.md`.
    3. Read back the saved manuscript (including the last 5 lines and word count) to confirm completion.
  - **Web / Chat Agents (Claude Projects, Genspark):**
    - Output the newly drafted chapter(s), the updated 10-line manuscript header, the `## References (APA)` additions, and the copy-ready `edit_log_<shortname>.md` row so Samir can save `<shortname>_vNN.md` on his PC.

---

## 2. Step-by-Step Writing Procedure (One Chapter Per Session)

### Step 1: Follow the 6-Block Chapter Blueprint `[COURSE]`
Draft one chapter at a time using the exact structure from `outline_<shortname>_vNN.md`:
1. **Opening Quote:** The real, attributed quotation from the outline.
2. **Hook:** Compelling opening statement or question.
3. **What This Chapter Covers:** Clear, natural preview of the chapter's outcome.
4. **Main Content (80 / 10 / 10 Mix):**
   - **80% Practical Action:** Step-by-step instructions, frameworks, scripts, checklists, or exercises.
   - **10% Research & Studies:** Real, verifiable facts/studies (or `[WRITER TODO]` placeholders—see Step 2).
   - **10% Relatable Stories:** Examples and scenarios aligned with the Author Avatar and Customer Research (`Step_04`), never presented as fake personal testimonials.
5. **Bullet Takeaways:** `3–6` crisp, actionable summary bullets.
6. **CTA Transition:** `"In the next chapter we will talk about ___."`

### Step 2: Enforce Strict Writing Bans & Citation Honesty
1. **Zero Fluff / Zero Basic Info:** Never pad chapters with generic dictionary definitions or basic filler easily found online `[COURSE]`.
2. **Multi-Format Cleanliness (No Links):** Never write `"Click here"` or include hyperlink-dependent text—the manuscript must work seamlessly across Kindle, Paperback, and Audiobook formats `[COURSE]`.
3. **Readability:** Write in clear, conversational simple English with subheadings every few paragraphs. Keep total plagiarism/similarity strictly **under 6–8%** `[COURSE]`.
4. **APA References vs. `[WRITER TODO]` Rule (Zero Fabrication):**
   - Collect full **APA citations** for every real study or statistic in a `## References (APA)` section at the very end of the manuscript. **Never invent a citation, study, author, or statistic.**
   - If a structural point needs a research citation you cannot verify right now, do **one** of these:
     - **Option A (Keep & Flag):** State the point as a general observation and insert a visible inline tag: `[WRITER TODO: needs a real source for this claim]`, and log it in the edit log.
     - **Option B (Cut):** Delete the claim if it adds no value without a number.
   - If `## References (APA)` has no verified entries yet, write explicitly under that heading: *"No sources are cited yet; research slots carry visible `[WRITER TODO]` notes instead of fabricated citations."*

### Step 3: Track Checkpoints & AI-Disclosure Status
1. **Word Count Checkpoints (`10k` / `20k` / `30k`):**
   - Count body words excluding the 300–400 word book description.
   - When body word count crosses **`≥ 10,000`**, **`≥ 20,000`**, or **`≥ 30,000`** words, log the checkpoint in the manuscript header and `edit_log_<shortname>.md`, and pause for Samir's review `[COURSE]`.
2. **Mandatory AI-Disclosure Classification (`00B` Gate):**
   - Because the agent drafts the text, KDP policy classifies the manuscript as **`generated — disclosure REQUIRED`** (even if heavily edited later by a human). Always record `AI-tool use: generated — disclosure REQUIRED` in the header unless the text was 100% human-written from scratch.
   - Link the dated KDP AI-disclosure policy file from `00B_kdp-policy-verification`. If that policy file is missing or older than 30 days, set `KDP AI-disclosure policy capture: MISSING` (you may continue drafting, but the manuscript is **blocked from publishing** until captured).

---

## 3. Required Output Formats

### File 1: Versioned Manuscript (`08_Book_Development/MANUSCRIPTS/<shortname>_vNN.md`)
*(Keep these exact first 10 header lines at the top of every manuscript version):*

```markdown
# <Book Title>
<!-- skill: Step_10_kdp-original-book-writing -->
Shortname: <shortname>
Version: v<NN>
Outline: 08_Book_Development/OUTLINES/outline_<shortname>_v<NN>.md
Author (pen name): <Pen Name>
Body word count (excl. description): <N>
Checkpoint: <none | 10k | 20k | 30k>
AI-tool use: <generated — disclosure REQUIRED | assistive | none> — KDP AI-disclosure policy capture: <02_Knowledge_Base/KDP_POLICIES/policy_ai_content_YYYYMMDD.md | MISSING>
Last updated: <YYYY-MM-DD>

---

## Chapter <N> — <Chapter Title>

> "<Real Opening Quote>" — <Author>

<Hook paragraph...>

<What this chapter covers...>

### <Subheading 1>
<Main content following 80% practical / 10% research / 10% stories, with subheadings every few paragraphs and zero links...>

### Chapter <N> Takeaways
- <Takeaway 1>
- <Takeaway 2>
- <Takeaway 3>

In the next chapter we will talk about <Topic of Chapter N+1>.

---

## References (APA)
- <Author, A. A. (Year). Title of work. Publisher/Source.>
*(Or explicit note if empty: "No sources are cited yet; research slots carry visible [WRITER TODO] notes instead of fabricated citations.")*

# Edit Log — <Book Title>
<!-- skill: Step_10_kdp-original-book-writing -->

| Date | Version | Chapters Touched | Body Word Count | Checkpoint | Change & Open `[WRITER TODO]` Notes | Evidence Path |
|---|---|---|---|---|---|---|
| <YYYY-MM-DD> | v<NN> | Ch <N> | <N> words | <none/10k/20k/30k> | Drafted Ch <N>; <K> open `[WRITER TODO]` items | `08_Book_Development/MANUSCRIPTS/<shortname>_v<NN>.md` |
