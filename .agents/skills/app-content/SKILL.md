---
name: app-content
description: Use for any content work in this app - researching, writing, extending, correcting or reviewing its competencies, chapters, pages, rounds, questions, exercises, figures, terms or sources. This app's own content decisions; they take precedence over the generic lernapps content skills. Load it before you change any content.
---

# Content guide of this app

## Curriculum

- **Subject & level:** German as a Foreign Language (`subject: daf`), CEFR **A1** (learning map band `5-6`).
- **Orientation:** Learning map `https://lernapps.net/apps/map/daf.json` (canonical source `lernapps/apps/map/daf.yaml`, based on ZfA/KMK *Rahmenplan DaF*, Goethe-Institut / ÖSD / telc A1, and CEFR Companion Volume 2020) and build brief `lernapps/apps#880` (part of overview epic `lernapps/apps#887`).
- **Standard variety:** Standard German as used in Germany (*Bundesdeutsch*) only — Austrian and Swiss everyday specialties are excluded at A1 to avoid confusing beginners.
- **Languages:** `languages: [de, en]` (`de` first per `@lernapps/app-templates 0.20.0`, full English UI tree at `/en/`).

## Competencies

### Chapter 1: `ankommen-vorstellen` — Arriving, Greetings and Forms (A1 · 5–6)
1. `begruessung-vorstellung` (*I can greet people, say goodbye, and give basic personal details like my name, age, and country.*) → `src/ankommen-vorstellen/begruessung-vorstellung.yaml`
2. `duzen-siezen` (*I can choose appropriately between informal du and formal Sie when addressing people in German-speaking countries.*) → `src/ankommen-vorstellen/duzen-siezen.yaml`
3. `alltag-hoeflichkeit` (*I can use typical greeting, thanking, and apologizing conventions in German-speaking everyday life.*) → `src/ankommen-vorstellen/alltag-hoeflichkeit.yaml`
4. `formulare-ausfuellen` (*I can understand and fill in simple registration or hotel forms with my personal details.*) → `src/ankommen-vorstellen/formulare-ausfuellen.yaml`
5. `sich-vorstellen-monolog` (*I can introduce myself in a few simple connected sentences about my name, home, family, and hobbies.*) → `src/ankommen-vorstellen/sich-vorstellen-monolog.yaml`

### Chapter 2: `zahlen-zeit-schule` — Numbers, Time, Dates, Announcements and School (A1 · 5–6)
6. `zahlen-preise` (*I can understand and say numbers, prices in euros and cents, and phone numbers.*) → `src/zahlen-zeit-schule/zahlen-preise.yaml`
7. `zeit-datum-wochentage` (*I can tell the time (formal and informal) and name days of the week, months, and dates.*) → `src/zahlen-zeit-schule/zeit-datum-wochentage.yaml`
8. `schule-unterricht` (*I can name classroom objects and school subjects and use basic classroom phrases.*) → `src/zahlen-zeit-schule/schule-unterricht.yaml`
9. `schilder-hinweise-lesen` (*I can extract key facts from short signs, opening hours, timetables, and public notices.*) → `src/zahlen-zeit-schule/schilder-hinweise-lesen.yaml`
10. `durchsagen-verstehen-a1` (*I can pick out key details like times, prices, and platform numbers from short announcements and voicemails.*) → `src/zahlen-zeit-schule/durchsagen-verstehen-a1.yaml`

### Chapter 3: `erste-nachrichten` — Short Messages and First Mediation (A1 · 5–6)
- Recap page: `src/erste-nachrichten/das-brauchst-du-hier.yaml` (`recap: daf/verb-zweitstellung` — *Verb-second word order*, from `lernapps/apps#874`).
11. `kurze-nachrichten-lesen` (*I can understand short text messages, postcards, and simple personal notes.*) → `src/erste-nachrichten/kurze-nachrichten-lesen.yaml`
12. `kurze-nachrichten-schreiben` (*I can write short messages, postcards, or simple emails to invite someone or ask for basic information.*) → `src/erste-nachrichten/kurze-nachrichten-schreiben.yaml`
13. `sprachmittlung-a1` (*I can pass on simple key facts (times, places, prices) from a short notice or message in another language.*) → `src/erste-nachrichten/sprachmittlung-a1.yaml`

## Content structure

- **Story world (fixed across all pages):** **Peter** (15, English-speaking exchange student spending a year in **Lindenberg**, a fictional mid-sized town in central Germany), host family **Weber** (**Frau Weber / Katrin**, **Herr Weber / Thomas**, **Lukas** 15, **Mina** 12), German teacher **Herr Braun**, classmate **Nadia** (15), visiting friend **Alex** (Ch 3.3). Recurring artifact: Peter's growing **Arrival Folder** (*Ankommens-Ordner*).
- **Page flow (1 competency per page, max 350 reading words, max 4 consecutive text blocks):**
  1. `einstieg` (Opening): 1–2 sentence Lindenberg scene + an immediate, easy opening task before the main explanation.
  2. `wortschatz` / `regel` / `beispiel` (Introduce): Arrival Folder SVG figure and/or `vocabulary` block (every German noun with its article) + concise rule/note naming the main English-speaker trap.
  3. `uebung` (Practice): 3 more varied exercises (4 total per competency page), progressing from recognizing to applying, ending with what Peter can do now and what comes next.
- **Chapter self-assessment:** Each `chapter.yaml` defines `selfAssessment` drawing 2–3 exercises per competency page.

## Terminology

- **Address to learners:** Informal *you* in English (`en`) and informal *du* in German (`de`) throughout.
- **Standard German in Germany (*Bundesdeutsch*) used:** *Brötchen* (not *Semmel/Gipfeli*), *Fahrrad* (not *Velo*), *Januar* (not *Jänner*), *PLZ* (5-digit postal code), *Gleis*, *Verspätung*, *Einlass*, *Beginn*, *Treffpunkt*, decimal comma in Euro prices (`2,45 €`), German dot-dates (`14.05.2011`).
- **Avoided:** Austrian/Swiss everyday vocabulary in A1 scenes; grammatical jargon beyond what A1 learners need (full grammar rules live in `#874`–`#879`).

## Exercise patterns

- **Pattern 1 — Situation opening (`single-choice`):** Short Lindenberg scene testing a classic English-speaker trap (e.g. `begruessung-vorstellung`, `begruessung-nachmittag`). Every option has a rule-based `info`.
- **Pattern 2 — Pair recognition (`matching`):** Match German phrases/fields/objects (with articles) to English meanings or social roles (e.g. `duzen-siezen`, `du-sie-zuordnen`).
- **Pattern 3 — Guided form/phrase completion (`language-task`, `mode: gap` or `choice`):** `languages: { source: en, target: de }`, plain English `source`/`cue`, German `[gap]` targets, `form: { case: hint, punctuation: ok }`, plus rule-based `mistakes`.
- **Pattern 4 — Productive sentence building (`language-task`, `mode: write` or `ordering`):** Learners order a German introduction/message or write a short German sentence with variants `(a|b)` and diagnosed mistakes.
- **Pattern 5 — Fact & sign verification (`multiple-choice`, `true-false`, `number`):** Check real German signs, opening hours, prices, and announcements.
- Every competency page has **4 varied exercises** (≤ 2 guessable choices, ≥ 2 active tasks); exercise combinations vary across pages (`explainer-interaction`, `explainer-page-variety`).

## Figures

- **Arrival Folder SVGs (`src/images/*.svg`):** Self-drawn inline SVGs, `viewBox="0 0 340 <h>"` (clean at 360px), `source: { de: "Eigene Zeichnung", en: "Own drawing" }`, `licence: CC0-1.0`.
- **Color & contrast convention (≥ 4.5:1 in light and dark mode):** Neutral light card `#f8fafc` with `#cbd5e1` border and `#0f172a` dark slate text; semantic accents: masculine/*der*/daytime blue (`#dbeafe` / `#1e3a8a`), feminine/*die*/warning rose (`#ffe4e6` / `#9f1239`), neuter/*das*/positive green (`#dcfce7` / `#14532d`), morning/highlight amber (`#fef3c7` / `#78350f`).
- Every figure illustrates what is given and **never reveals the answer** to a task (`explainer-figure-hides-answer`); `alt` describes what is shown, `caption` tells what to look at.

## Sources

- `https://lernapps.net/apps/map/daf.json` (canonical `lernapps/apps/map/daf.yaml`) — verified.
- `lernapps/apps#887` (DaF explainer overview) and `lernapps/apps#880` (build brief) — verified.
- Basic vocabulary `map/daf/vocabulary/` — not yet published (no openly licensed TSV); A1 words follow standard CEFR A1 beginner vocabulary and are introduced in `vocabulary` blocks on each page.
- No private creator material is committed.

## Adding a chapter or round

1. Check `https://lernapps.net/apps/map/daf.json` for competency ids and `requires`.
2. Create `src/<chapter-id>/chapter.yaml` and one YAML file per competency (plus one compact `recap` page first if any external prerequisite is needed).
3. Register `<chapter-id>` in `src/app.yaml` (`chapters`).
4. Follow the 4-exercise pattern and Arrival Folder SVG conventions above, add `selfAssessment` to `chapter.yaml`, and update this content guide.
5. Run `npx vp check --fix`, `npx vp build`, `npx --no -- lernapps screenshots`, and `npx --no -- lernapps check`, then commit on a feature branch.

## Rules learned from mistakes

- Protagonist name must be **Peter** (never "Sam", whose German pronunciation is unrecognizable to English beginners).
- In `language-task`, `cue`, `source`, `target`, and `distractors` are plain strings (never `{ de, en }` maps), whereas `vocabulary` `note` and `number` `unit` must be `{ de, en }` maps when `languages: [de, en]`.
- Never put Markdown emphasis (`**...**`) inside a recap page's competency title in a way that breaks `recap-names-competencies` exact matching.
- Leave at least 24 px of empty space at the bottom-right of every `src/images/*.svg` so the runtime's `© CC0-1.0` badge never overlaps text at 360 px.
- Explain special German characters (`ß`, umlauts), noun capitalization, and any English-speaker clue right before first use — in plain age-15 language, never linguistics jargon ("long diphthong").
- Never copy the exact same sentences across the vocabulary examples, Exercise 3, and Exercise 4 — vary names/places/ages so Exercise 4 tests real transfer, and never list verbatim answers in `hint`.
