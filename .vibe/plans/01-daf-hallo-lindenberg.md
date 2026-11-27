---
# Read by the hooks, the review, the evals. Schema: @lernapps/tooling/guidance/plan-front-matter.v1.schema.json
# Written by `lernapps plan` and the hooks. Never change a key or a value by hand.
# Archetype, null until chosen in Explore. Allowed values: explainer, interactive, quiz.
archetype: explainer
# Current phase. Allowed values: explore, plan, code, commit.
phase: code
# prePushFailures: failed pre-push runs, written by the hook.
prePushFailures: 0
# failedChecks: failed rules and runs, written by lernapps check and the hooks.
failedChecks: {}
---

# Plan: daf-hallo-lindenberg, first version

<!--
For you, the assistant. The process is in AGENTS.md; this plan holds the method.
- `npx --no -- lernapps plan next` prints the task to do now, `plan done` ticks it and prints the next one.
- You write only below Goal, Key decisions, Notes, Answers, Entry draft, Content method and Retrospective, in the
  creator's language. Delete the comment of a section once the section is filled.
- Work on the branch `work`, locally: push nothing before Commit.
-->

*Started 2026-11-26. Explore, Plan, Code, Commit.*

## Goal

English-speaking A1 beginners follow Peter's arrival in Lindenberg, Germany to learn and practice everyday greetings, informal *du* vs. formal *Sie*, politeness formulas, registration forms, numbers/prices, time/dates, classroom phrases, signs, short station announcements, and short personal messages and mediation.

## Key decisions

- **Archetype: `explainer` (format 2, `subject: daf`).** Learners need structured explanations, visual artifacts (Peter's Arrival Folder: profile card, timetable, calendar, signs, chat thread), vocabulary blocks, and progressive exercises (`language-task`, `single-choice`, `multiple-choice`, `matching`, `ordering`, `true-false`, `number`, `open-task`). `quiz` lacks explanatory pages and `vocabulary` blocks; `interactive` fits a single-screen game/trainer rather than a 3-chapter situational sequence.
- **Setting & variety: Germany (*Standard German / Bundesdeutsch*).** Everyday scenes, vocabulary (*Brötchen*, *Fahrrad*, *Januar*, *PLZ*, *Deutsche Bahn*), and civic norms follow Germany consistently; Austrian and Swiss specialties are not mixed into A1 daily life (creator decision).
- **Protagonist name: Peter.** Replaced "Sam" with **Peter** so the name has a clear, recognizable German pronunciation (creator decision).
- **Languages: `[de, en]` (`de` first, full English tree at `/en/`).** Required by `@lernapps/app-templates 0.20.0` (which enforces `languages[0] === "de"`). English-speaking learners use `/en/` with 100% English runtime UI and explanations teaching German; `/` provides the complete German tree.
- **Audio / speaking tasks: omitted in v1 (guess).** `@lernapps/app-templates` synthetic audio currently supports English, French, Spanish, and Italian — not German (`de`). Announcements (`durchsagen-verstehen-a1`) and spoken introductions (`sich-vorstellen-monolog`) use realistic transcripts, signal-word scanning, and structured building/open tasks instead.
- **Chapter self-assessments (`selfAssessment`): included per chapter (guess).** Allows learners to check readiness across each chapter and hand results to the tutor.

## Notes

- **Subject & focus:** `subject: daf` (`explainerFocus: competency`, unit app across strands `wortschatz`, `landeskunde`, `texte`; one strand per page).
- **Primary sources verified:**
  - Learning map: `https://lernapps.net/apps/map/daf.json` (local canonical source `lernapps/apps/map/daf.yaml`, verified).
  - Epic & issue brief: `lernapps/apps#887` (overview) and `lernapps/apps#880` (verified).
  - Basic vocabulary (`map/daf/vocabulary/`): not yet available on `lernapps.net` (CEFRLex DAFlex has no downloadable TSV yet); A1 words are kept strictly to everyday CEFR A1 beginner vocabulary and introduced in `vocabulary` blocks with articles before any exercise asks for them.
- **Story world (Lindenberg Series, Part 1):**
  - **Place:** Lindenberg, a fictional mid-sized town in central Germany (train station, marketplace, bakery, school/language course, town library, Kulturhaus).
  - **Cast:** **Peter** (15, English-speaking exchange student spending a year in Germany), host family **Weber** (**Frau Weber / Katrin**, **Herr Weber / Thomas**, **Lukas** 15, **Mina** 12), teacher **Herr Braun**, classmate **Nadia** (15).
  - **Recurring visual artifact:** Peter's growing **Arrival Folder** (SVG illustrations & visual scenes: station greeting card, du/Sie badge chart, registration form, German number/Euro card, clock & calendar visual, classroom desk diagram, library opening-hours sign, platform departure board, chat bubbles, concert poster).
- **Chapters, pages, competencies, external prerequisites, derivation & misconceptions:**
  - **Chapter 1: `ankommen-vorstellen` — Arriving, Greetings and Forms (A1 · 5–6)** (0 external prerequisites):
    1. `begruessung-vorstellung` (`wortschatz`, req: none) — Derive greeting choice from time of day at Lindenberg station; catches *Guten Morgen* in afternoon & *Gute Nacht* as greeting.
    2. `duzen-siezen` (`landeskunde`, req: none) — Derive *du* vs. *Sie* from social role (peers/family vs. teachers/unfamiliar adults); catches using *du* with Herr Braun or lowercase *sie* for formal *Sie*.
    3. `alltag-hoeflichkeit` (`landeskunde`, req: `duzen-siezen`) — Derive situational politeness (*Bitte schön* as reply to *Danke*, *Entschuldigung*, *Gesundheit*, *Guten Appetit*); catches English literal *Du bist willkommen*.
    4. `formulare-ausfuellen` (`texte`, req: `begruessung-vorstellung`) — Derive German form conventions (street before number, 5-digit PLZ before town, DD.MM.YYYY with dots); catches English address order (`12 Lindenstraße`) and MM/DD dates.
    5. `sich-vorstellen-monolog` (`texte`, req: `formulare-ausfuellen`) — Derive a 5-step spoken profile structure from Peter's profile card; catches *Ich bin 15 Jahre* (missing *alt*) and English word order.
  - **Chapter 2: `zahlen-zeit-schule` — Numbers, Time, Dates, Announcements and School (A1 · 5–6)** (0 external prerequisites):
    6. `zahlen-preise` (`wortschatz`, req: `begruessung-vorstellung`) — Derive inverted German tens (ones + *und* + tens) and Euro decimal comma (`2,45 €`); catches digit swaps (*vierundfünfzig* vs. *fünfundvierzig*).
    7. `zeit-datum-wochentage` (`wortschatz`, req: `zahlen-preise`) — Derive German *halb* looking forward (*halb drei* = 14:30) and time prepositions (*um / am / im*); catches reading *halb drei* as 3:30.
    8. `schule-unterricht` (`wortschatz`, req: `begruessung-vorstellung`) — Derive noun+article pairing (*der/die/das*) on Peter's desk and polite classroom questions with *Sie*; catches dropping articles or using *du* with Herr Braun.
    9. `schilder-hinweise-lesen` (`texte`, req: `formulare-ausfuellen`) — Derive scanning strategy (days `Mo–Fr`, `Sa`, `So`, 24h hours, *geöffnet/geschlossen*); catches assuming weekday hours apply on Saturday/Sunday.
    10. `durchsagen-verstehen-a1` (`texte`, req: `schilder-hinweise-lesen`) — Derive 4-signal-word listening/reading strategy (*Gleis*, *Abfahrt*, time, *Verspätung*); catches picking the old platform number or confusing delay minutes with platform numbers.
  - **Chapter 3: `erste-nachrichten` — Short Messages and First Mediation (A1 · 5–6)** (1 external prerequisite: `daf/verb-zweitstellung` from `#874` → placed on one compact recap page `das-brauchst-du-hier` at chapter start):
    0. `das-brauchst-du-hier` (`recap: daf/verb-zweitstellung`) — Compact refresher naming `Verb-second word order` (*I can place the conjugated verb in second position in German statements, including when time or place comes first.*), no new content.
    11. `kurze-nachrichten-lesen` (`texte`, req: `schilder-hinweise-lesen`) — Derive 4-W scanning (*Wer, Was, Wann, Wo*) on Lukas's chat message; catches skimming past *Treffpunkt* or misreading what to bring.
    12. `kurze-nachrichten-schreiben` (`texte`, req: `kurze-nachrichten-lesen`, `verb-zweitstellung`) — Derive 3-part message blueprint (greeting, body with verb-second after time, sign-off); catches English verb-third (*Um 15 Uhr ich gehe*) and uncapitalized nouns.
    13. `sprachmittlung-a1` (`texte`, req: `kurze-nachrichten-lesen`) — Derive fact-relaying (not word-for-word translation) from a German poster to English; catches confusing *Einlass* (doors open) with *Beginn* (start) or date with price.
- **Scope:**
  - **In:** All 13 A1 competencies of `#880` across 3 chapters + 1 recap page (`daf/verb-zweitstellung`), Peter's Arrival Folder SVG visuals, 4+ varied exercises per competency page (choice, matching, ordering, number, `language-task` gap/choice/write, and `open-task` where learners produce their own introduction/message), chapter self-assessments, `languages: [de, en]`.
  - **Out:** Full grammar rules (live in `#874`–`#879`, fixed phrases only here); home/family/food/weather/health (`#881`); town/travel/D-A-CH (`#882`); synthetic German audio (not yet supported by `@lernapps/app-templates`).
  - **Data range:** Numbers 0–100 and Euro prices; 24-hour and everyday clock times; all 7 weekdays and 12 months; core A1 classroom objects and everyday signs.

## Explore

<!--
- Find out what the app teaches, for whom, how much and how it looks. Ask; write no code, run no `create`.
- An answer counts only in the creator's words under "Answers". At most 2 questions per message, one topic each.
-->

### Tasks

- [x] Check the start: the folder `.agents/skills/lernapps-app` exists (else stop and tell the creator that the folder
      was not started with `init`), and `git branch --show-current` prints `work` (else `git switch -c work`).
- [x] Load skill `lernapps-app`. Tell the creator in two sentences what a lernapps app is and where it will live: at
      their own address, free and public, and once listed as a copy on lernapps.net. Say that the technical part
      (GitHub) comes at the end and that you do it.
- [x] Interview: ask the topics "Goal" and "Learners" of "Answers".
- [x] Load skill `lernapps-map-assignment` and read the learning map of the subject as it says. The creator brings
      the content themselves (material, a word list, the pages): note under "Notes" which competencies of the map it
      covers. Else write the skill's assignment, with its story; the creator's yes answers the topics Content and
      Amount. A subject without a map: skip this task and say so.
- [x] Load skill `lernapps-exercise-patterns` and read its reference for the subject. Note under "Notes" how learners
      will practise what the goal names.
- [x] Choose the archetype as skill `lernapps-app` says: read the README of each archetype in question, then tell the
      creator in plain words what the chosen one can and cannot do. Write the archetype and its reason under "Key
      decisions".
- [x] Run `npx --no -- lernapps skills --archetype <name>` with the chosen archetype. It installs the archetype's
      skills and adds the archetype's tasks to this plan.
- [x] Load skill `lernapps-explainer-design`. An explainer has the look of the runtime: write "fixed by the
      archetype" under the topic "Look and feel" of "Answers".
- [x] Interview: ask every other topic of "Answers", in order. Leave out only a topic that an answer of the creator
      already covers, and note which answer. A topic nobody answered is asked once before you write an assumption
      with "(guess)".
- [x] Load skill `lernapps-content-research` and research as it says. Write under "Notes": the strand or subject, the
      competencies by chapter with their ids, the sources you opened.
- [x] Write under "Notes" which competency goes on which page and which pages form a chapter, as "Map the content" of
      skill `lernapps-explainer-design` says. Per page, name the prerequisites the app does not practise.
- [x] Write under "Notes", one line per competency: how learners get there (they derive it, they do not only read it
      off), and which misconception the feedback catches.
- [x] Write under "Notes" the scope: what is in, what is out and why, the data range (for example "all main-group
      elements", never a silent "1–20"), the languages.
- [x] **Checkpoint:** research. Show in plain words: the strand or why none, the competencies by chapter, the didactic
      approach, the scope, every "(guess)", the sources and what is unchecked, the archetype and its reason. Stop and
      wait. Changes: change them, then ask again.
      Creator: Ok. Move on

### Answers

- Goal: Guide English-speaking A1 beginners through Peter's first days in Lindenberg, Germany — greetings, *du* vs. *Sie*, everyday politeness, forms, self-introduction, numbers/prices, time/dates, classroom phrases, signs, short announcements, short messages, and A1 mediation (from `#880`).
- Learners: English-speaking beginners learning German as a Foreign Language (DaF) at CEFR A1 (`5-6`), starting with no prior knowledge of German (from `#887`).
- Model and focus: Modeled on the Millbrook English series (`lernapps/apps#489`, e.g. `#470` *Hello, Millbrook!*); focus on authentic everyday scenes in Germany, clear visual artifacts (Arrival Folder), and varied interactive practice (4+ exercises per page).
- Hurdles: English-speaker traps — *du* vs. *Sie* (and capital *Sie*), inverted numbers (*fünfundvierzig* = 45), forward-looking *halb drei* (= 2:30, not 3:30), German address/date formats (`Lindenstraße 12`, `DD.MM.YYYY`), decimal comma (`2,45 €`), noun capitalization, *Einlass* vs. *Beginn*, and verb-second order after time expressions.
- Content: Written from `map/daf.yaml` and `#880` following Standard German in Germany (*Bundesdeutsch*); no private creator worksheets.
- Amount: Full A1 unit of `#880` — 3 chapters, 13 competency pages + 1 compact recap page (`daf/verb-zweitstellung`) + chapter self-assessments.
- Languages: `[de, en]` (`de` first as required by `@lernapps/app-templates 0.20.0`, complete English tree at `/en/`).
- Look and feel: fixed by the archetype.
- Terms: Standard German in Germany (*Bundesdeutsch*): *Brötchen*, *PLZ*, *Gleis*, *Verspätung*, *Einlass*, *Beginn*, *Treffpunkt*; story terms: *Lindenberg*, *Peter*, *Familie Weber* (*Frau Weber*, *Herr Weber*, *Lukas*, *Mina*), *Herr Braun*, *Nadia*, *Arrival Folder* (*Ankommens-Ordner*).
- Finding the app: "German A1", "DaF", "Deutsch als Fremdsprache", "greetings", "du und Sie", "numbers and time", "Hallo Lindenberg".

## Plan

<!--
- Map the confirmed content onto the archetype. No new content questions: a gap in the content goes back to Explore.
- The creator confirms the plan in one read. After the yes you work on your own.
-->

### Tasks

- [x] Map the content as "Map the content" of skill `lernapps-explainer-design` says, and write the result under
      "Content method".
- [x] Choose a pattern per competency as skill `lernapps-exercise-patterns` says, and add it to "Content method".
- [x] Add to "Content method" one line per page, as "Engagement" of skill `lernapps-explainer-design` says: the
      opening task, the change of activity, the reward, the story.
- [x] Add the tasks of Code, each one a piece of work that ends in a commit. First the pattern: one complete page or
      screen, `npx --no -- lernapps plan add --at pattern "<task>"`. Then the others, one call each:
      `npx --no -- lernapps plan add --at pages "<task>"`. Each task says what it builds and what it shows.
- [x] Draw a sketch of each screen, component or interactive exercise: a static SVG or image, or the steps with what
      learners see after each. Keep the files in `.vibe/sketches/`.
- [x] Show the creator, short: goal, competencies by chapter, the Code tasks, the sketches, and the content method in
      plain words (what learners see and do, what the app cannot do). At most 2 questions.
- [x] **Checkpoint:** confirm the plan and the content method. Stop and wait for an explicit yes. Changes: change
      them, then ask again.
      Creator: ye

### Content method

#### Language practice (`explainer-language-practice`)
1. **Listening and speaking:** Omitted in v1 (`@lernapps/app-templates 0.20.0` synthetic audio supports EN/FR/ES/IT only, not DE); announcements (`durchsagen-verstehen-a1`) and self-introduction (`sich-vorstellen-monolog`) use realistic transcripts, signal-word scanning, and structured building tasks.
2. **Words:** Every German noun is introduced with its article (`der`, `die`, `das`) in a `vocabulary` block before any exercise asks for it. Source: standard CEFR A1 beginner vocabulary grounded in Germany (*Bundesdeutsch*) because `map/daf/vocabulary/` has no openly licensed TSV yet.
3. **Exercise variety (`explainer-interaction`, `explainer-page-variety`):** Every competency page has **4 varied exercises** progressing from recognizing to applying (`single-choice` / `multiple-choice` / `true-false` ≤ 2 per page, paired with ≥ 2 active tasks from `language-task` [gap, choice, write, table], `matching`, `ordering`, `number`, and `open-task` where learners produce their own text). Exercise sets vary across pages so no single combination appears on ≥ 50% of pages.
4. **Typical English-speaker mistakes:** Every wrong option `info` and `language-task` `mistakes` entry names the rule — *Guten Morgen* vs. *Guten Tag*, *du* vs. capital *Sie*, literal *Du bist willkommen* → *Bitte schön*, English address/date order → `Straße + Nr.`, `DD.MM.YYYY`, inverted tens (*fünfundvierzig* = 45), forward-looking *halb drei* = 2:30, decimal comma (`2,45 €`), *Einlass* vs. *Beginn*, and verb-second after time phrases.

#### Built-in blocks vs. components (`prefer-built-in-block`)
- All 13 competencies fit built-in explainer blocks (`vocabulary`, `table`, `figure`, `example`, `note`, `single-choice`, `multiple-choice`, `true-false`, `matching`, `ordering`, `number`, `language-task`). No custom Vue component is needed.
- Because `open-task` requires `scope` on every page in `src/app.yaml`, v1 uses `language-task` (`mode: write` / `gap` / `choice`) + `ordering` + `matching` for auto-checked productive writing instead of `open-task` (keeps every task immediately checkable without a tutor).

#### Figures (Peter's Arrival Folder — 10 custom SVGs in `src/images/`, CC0-1.0, 360px-safe, ≥ 4.5:1 contrast)
1. `station-clock-greetings.svg` (`begruessung-vorstellung`): A day-timeline strip showing morning (06–11 *Guten Morgen*), midday/afternoon (11–18 *Guten Tag*), evening (18–22 *Guten Abend*), and night (*Gute Nacht*) at Lindenberg station; learners derive the right greeting from the clock time without giving away the 15:00 task answer.
2. `du-sie-map.svg` (`duzen-siezen`): Two-zone social circle card showing Peter's inner circle (*du*: Lukas, Mina, Nadia) vs. outer adult/formal circle (*Sie*: Herr Braun, ticket clerk, unfamiliar adults); learners map new people onto the right zone.
3. `registration-form.svg` (`formulare-ausfuellen`): Clean German *Anmeldeformular* card showing labeled blank boxes for *Vorname*, *Nachname*, *Geburtsdatum (TT.MM.JJJJ)*, *Straße, Hausnummer*, and *PLZ (5 digits), Wohnort*; learners compare German field order against English conventions.
4. `profile-card-steps.svg` (`sich-vorstellen-monolog`): Five numbered stepping-stone cards (*1 Begrüßung → 2 Name & Herkunft → 3 Alter → 4 Wohnort → 5 Hobbys*) showing how a spoken self-introduction builds step by step.
5. `number-swap-diagram.svg` (`zahlen-preise`): Visual arrow diagram for German two-digit numbers (`45 → fünf · und · vierzig`, ones arrow pointing left before tens) plus a German bakery price tag showing the decimal comma (`2,45 €`).
6. `clock-halb-drei.svg` (`zeit-datum-wochentage`): Analog clock face comparing English "half past 2" with German *halb drei* (shaded half-hour leading *toward* 3:00 = 14:30), paired with the `um / am / im` triangle.
7. `classroom-desk.svg` (`schule-unterricht`): Top-down labelled desk illustration of Peter's school desk in Herr Braun's room (*der Stift*, *das Heft*, *das Buch*, *der Stundenplan*) color-coded by gender (*der* blue, *die* red, *das* green).
8. `library-hours-sign.svg` (`schilder-hinweise-lesen`): Authentic German *Öffnungszeiten* door sign for *Stadtbibliothek Lindenberg* (`Mo–Fr 10:00–18:00`, `Sa 09:00–13:00`, `So geschlossen`) so learners practice real sign scanning.
9. `platform-board.svg` (`durchsagen-verstehen-a1`): Blue *Deutsche Bahn*-style departure board showing `RE Frankfurt · Plan 14:20 · +10 Min · Gleis 6` with icons for the 4 signal words (*Gleis, Abfahrt, Zeit, Verspätung*).
10. `concert-poster.svg` (`sprachmittlung-a1`): Clean German youth-concert poster (*Kulturhaus Lindenberg · Sa, 18. Okt · Einlass 18:30 · Beginn 19:00 · 5,00 € / Schüler 3,00 €*) for mediation practice.

#### Prerequisites outside the app
- Chapters 1 and 2: **none** (all prerequisites are internal in reading order).
- Chapter 3 (`erste-nachrichten`): 1 external prerequisite (`daf/verb-zweitstellung` from `#874`) → placed on one compact recap page `erste-nachrichten/das-brauchst-du-hier.yaml` (`recap: daf/verb-zweitstellung`) at the start of Chapter 3, naming *Verb-second word order* and its `"I can …"` statement, with no new content and 1 quick self-check.

#### Engagement & exercise pattern per page (Opening · Change · Reward · Story)
- **Ch 1.1 `begruessung-vorstellung` (pilot page):** Opening: 15:00 arrival greeting choice (`single-choice`) → Change: `station-clock-greetings.svg` + `vocabulary` + `matching` + `language-task` (`gap`) + `language-task` (`write`) → Reward: Peter's first Arrival Folder badge ("I can greet and introduce myself") → Story: Peter steps off the train at Lindenberg station and meets Frau Weber, Lukas, and Mina; next he learns when to use *du* vs. *Sie*.
- **Ch 1.2 `duzen-siezen`:** Opening: Greeting Herr Braun (`single-choice`) → Change: `du-sie-map.svg` + `table` + `matching` + `true-false` + `language-task` (`choice`) → Reward: Ready to address anyone in Lindenberg politely → Story: First morning at school; next comes everyday politeness at the Webers' table.
- **Ch 1.3 `alltag-hoeflichkeit`:** Opening: Mina sneezes at dinner (`single-choice`) → Change: `vocabulary` + `language-task` (`choice`) + `matching` + `language-task` (`gap`) → Reward: Confident with polite German replies → Story: First dinner with the Webers; next morning Peter fills in his registration form.
- **Ch 1.4 `formulare-ausfuellen`:** Opening: Spot the German address format (`single-choice`) → Change: `registration-form.svg` + `table` + `matching` + `true-false` + `language-task` (`gap`) → Reward: Peter's Arrival Folder registration card is complete → Story: At the language school office; next Peter introduces himself aloud in class.
- **Ch 1.5 `sich-vorstellen-monolog`:** Opening: Order Nadia's introduction (`ordering`) → Change: `profile-card-steps.svg` + `example` + `language-task` (`gap`) + `single-choice` + `language-task` (`write`) → Reward: Chapter 1 complete — Peter can introduce himself in 5 connected sentences → Story: Herr Braun's class applauds; next Peter heads into town for tickets and *Brötchen*.
- **Ch 2.1 `zahlen-preise`:** Opening: Bakery price digit-swap trap (`single-choice`) → Change: `number-swap-diagram.svg` + `vocabulary` + `number` + `matching` + `language-task` (`write`) → Reward: Can pay and read German prices in € → Story: Buying *Brötchen* and a bus ticket; next Peter checks his school timetable.
- **Ch 2.2 `zeit-datum-wochentage`:** Opening: Lukas's *halb drei* meeting trap (`single-choice`) → Change: `clock-halb-drei.svg` + `table` + `matching` + `language-task` (`choice`) + `language-task` (`gap`) → Reward: Never late for a German *halb* appointment → Story: Adding class times to the Arrival Folder calendar; next Peter unpacks in class.
- **Ch 2.3 `schule-unterricht`:** Opening: Ask Herr Braun to repeat (`single-choice`) → Change: `classroom-desk.svg` + `vocabulary` + `matching` + `language-task` (`gap`) + `language-task` (`choice`) → Reward: Can ask for help in German during class → Story: First lesson with Nadia; after school Peter walks to the library.
- **Ch 2.4 `schilder-hinweise-lesen`:** Opening: Can Peter enter the library at 14:00 Saturday? (`single-choice`) → Change: `library-hours-sign.svg` + `table` + `multiple-choice` + `true-false` + `matching` → Reward: Can scan real German signs and hours → Story: Exploring Lindenberg's town center; next Peter listens to station announcements.
- **Ch 2.5 `durchsagen-verstehen-a1`:** Opening: Which platform does the Frankfurt train leave from? (`single-choice`) → Change: `platform-board.svg` + `example` + `true-false` + `number` + `matching` → Reward: Chapter 2 complete — ready for German stations and schedules → Story: Weekend trip prep at Lindenberg station; next Peter texts Lukas and Nadia.
- **Ch 3.0 `das-brauchst-du-hier` (`recap: daf/verb-zweitstellung`):** Compact refresher + 1 quick mental check (no new content).
- **Ch 3.1 `kurze-nachrichten-lesen`:** Opening: Find the meeting point in Lukas's chat (`single-choice`) → Change: `example` + `true-false` + `multiple-choice` + `matching` → Reward: Can scan German chats with the 4-W method → Story: Lukas invites Peter to the town park; next Peter writes his own invitation.
- **Ch 3.2 `kurze-nachrichten-schreiben`:** Opening: Order Peter's reply (`ordering`) → Change: `example` + `language-task` (`gap`) + `single-choice` + `language-task` (`write`) → Reward: Can write a complete German invitation with verb-second order → Story: Inviting Nadia to the café; next Peter's friend Alex visits from England.
- **Ch 3.3 `sprachmittlung-a1`:** Opening: Tell Alex the student-ID price (`single-choice`) → Change: `concert-poster.svg` + `multiple-choice` + `true-false` + `matching` → Reward: Chapter 3 & Arrival Folder complete — ready for everyday life at the Webers' (`#881`) → Story: Peter and Alex head to the youth concert at Kulturhaus Lindenberg.

#### How a later agent adds a chapter
- Add a new folder `src/<chapter-id>/` with `chapter.yaml` (including `selfAssessment`), add its id to `chapters` in `src/app.yaml`, place one compact recap page first if it has external `map/daf.yaml` prerequisites, keep 1 competency per page, include 4+ varied exercises and at least 1 Arrival Folder SVG per 2 pages, and update `.agents/skills/app-content/SKILL.md`.

## Code

<!--
- Build the app, locally on `work`, on your own. After each task: `plan done`, then one commit with the work and this
  plan. The hooks check each commit; a failing check is fixed from its message, as skill `lernapps-cli` says.
- What you cannot decide: choose, write it under "Key decisions" with "(guess)", go on.
- The creator asks for a change: say your reading in one sentence first, then change every place it holds for
  (`feedback-applied-everywhere`).
-->

### Tasks

- [x] Load skill `lernapps-cli`. Create the app as its section "Create" says:
      `npx --no -- lernapps create --archetype explainer`.
- [x] Fill the content guide `.agents/skills/app-content/SKILL.md` from "Notes" and "Content method": every heading,
      no "FILL IN" left. Commit it before any content.
- [ ] Load skill `lernapps-explainer`.
- [ ] Load skill `lernapps-content-questions`. Read whole, with your file tool:
      `.agents/skills/lernapps-explainer/references/blocks.md` and
      `.agents/skills/lernapps-explainer/references/exercises.md`. A foreign language: also
      `references/language-tasks.md` in the same folder. A component in the plan: also `references/components.md`.
- [ ] Decide whether the app needs `scope`, as "`scope`" in
      `.agents/skills/lernapps-explainer/references/structure.md` says. Write the choice under "Key decisions".
- [ ] Build pilot page ankommen-vorstellen/begruessung-vorstellung with station-clock-greetings.svg, vocabulary block, and 4 varied exercises; verify with vp build, screenshots, and learner check before scaling.
<!-- tasks: pattern (1 added): the one page or screen that is the pattern for the others -->
- [ ] **Checkpoint:** the pattern page. Load skill `lernapps-learner-check` and do its learner check on the page. Fix
      what it finds. Then show the creator the page and ask whether the others may follow it. Stop and wait. A
      change: change the pattern first.
- [ ] Complete Chapter 1 (duzen-siezen, alltag-hoeflichkeit, formulare-ausfuellen, sich-vorstellen-monolog) with Arrival Folder SVGs (du-sie-map, registration-form, profile-card-steps), 4 varied exercises per page, and chapter selfAssessment.
- [ ] Build Chapter 2 (zahlen-preise, zeit-datum-wochentage, schule-unterricht, schilder-hinweise-lesen, durchsagen-verstehen-a1) with 5 Arrival Folder SVGs, 4 varied exercises per page, and chapter selfAssessment.
- [ ] Build Chapter 3 (recap page das-brauchst-du-hier for daf/verb-zweitstellung, kurze-nachrichten-lesen, kurze-nachrichten-schreiben, sprachmittlung-a1) with concert-poster.svg, 4 varied exercises per page, and chapter selfAssessment.
- [ ] Fill .agents/skills/app-content/SKILL.md, run lernapps screenshots, and run independent learner + DaF subject-matter review agents on the complete app.
<!-- tasks: pages (4 added): the other pages or screens, after the pattern -->
- [ ] Update the content guide so that it describes the app as built (`app-content-matches`).
- [ ] Run `npx --no -- lernapps check` until it passes.
- [ ] Look at every screen and state, at 360 px and on a desktop, as "Look at the app" of skill `lernapps-cli` says.
      Compare each with its sketch.
- [ ] Do the whole-app check of skill `lernapps-learner-check`. Fix what it finds and write under "Notes" what you
      fixed.

## Commit

<!--
- Put the app on GitHub, publish it with the creator's yes, then list it. A push to `main` publishes.
- Open the pull requests (to `main`, to the catalog) without asking: they publish nothing.
- The creator asked to stop before publishing (a trial): stop here and say so.
-->

### Tasks

- [ ] Load skill `lernapps-explainer-self-assessment`. Add the self-assessment as it says, or write under "Key
      decisions" why the app has none. Commit.
- [ ] Load skill `lernapps-github`. Set up the repository and Pages as it says. Ask for the repository's name and
      every click only the creator can make, in one message.
- [ ] Push `work`, open the preview pull request and see its checks to green, as skill `lernapps-github` says.
- [ ] **Checkpoint:** publish. Show what the app does and the preview link from the comment "Vorschau der App". Ask
      whether it may go online. Stop and wait for the yes.
- [ ] Load skill `lernapps-commit`. Publish as skill `lernapps-github` says: `work` into `main` as one squash commit,
      the run of `Pages` watched to its end.
- [ ] Open the address the job `deploy` printed and confirm that the app shows. Never use a derived address.
- [ ] Load skill `lernapps-listing`. Write the entry under "Entry draft" as it says, with the creator's answer to
      "Finding the app".
- [ ] Fill the retrospective.
- [ ] Commit this plan on `main` and push it: the listing check and the review read it there.
- [ ] **Checkpoint:** list. Open the listing pull request as skill `lernapps-listing` says, without asking first: the
      pull request is the review. See it to "bestanden", then show the creator the pull request and its result.
- [ ] If the plan changed since its last push, commit it on `main` and push again.

### Entry draft

<!-- YAML valid against the entry schema the listing skill names. Only known values, never invented. -->

```yaml
```

## Retrospective

<!-- At the end of Commit, before the listing pull request. Facts, short, no names. Read by review and evals. -->

### Phases reached

<!-- Last phase completed, checkpoints passed. E.g. "commit; confirmed, published". -->

### Creator turns after the plan

<!-- Number of creator messages after the confirmation, topic of each. Target: at most 3. -->

### Where I had to guess

<!-- Each gap in plan, skills, messages or answers, and your choice. "None" if none. -->
