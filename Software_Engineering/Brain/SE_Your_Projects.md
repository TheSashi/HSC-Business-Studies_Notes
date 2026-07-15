---
tags: [software-engineering, hsc, case-study, projects, year-11, year-12, assessment]
aliases: [SE Projects, D&D App, Wicked Problems, Systems Report]
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Assessments
created: 2026-07-15
updated: 2026-07-15
---

# Your SE Projects (Case Studies)

> Real assessment work, used as exam case-study evidence (like Apple/McDonald's in Business Studies). Grounded in your actual submitted assessments: the Year 12 D&D App Systems Report, the Year 11 Group Project (Wicked Problems), and the Year 11 Stage 6 group task. Only what is verifiable from the provided files is included; report-body detail that did not extract from the PDF is not invented.

---

## 1. Year 12 — D&D App Systems Report (Sashank Vuppala)

This is your Software Engineering Stage 6 (Year 12) systems report. It follows the NSW Education SE report structure:

1. **Identifying and defining** — define and analyse problem requirements
2. **Research and planning** — project management, quality assurance, systems modelling
3. **Producing and implementing** — screenshots of the program working
4. **Testing and evaluating** — evaluation of code + evaluation of solution against quality success criteria

### Problem context (from the report)
Client: **Ms Sheldon**, an experienced Dungeons & Dragons player, currently manages character info on physical handwritten character sheets. A client interview was conducted **19 March 2026**. Problems identified with the paper system:

- **Arithmetic errors:** Secondary stats (ability modifiers, proficiency bonuses, saving throws, skill checks) are derived from base ability scores using fixed formulas. Manual calculation introduces frequent errors, especially under gameplay time pressure.
- **Data vulnerability:** Paper sheets can be damaged or lost. Mid-session updates (e.g. decrementing HP after damage) are slow and error-prone.
- **Complex character creation:** Client uses **point-buy** — a fixed budget of **27 points** across six ability scores, each with a non-linear cost; racial and background modifiers layered on top. Hard to track manually.
- **Accessibility:** Needs character data on a **mobile device** during sessions.
- **Session persistence:** Must distinguish between short one-off sessions and long-running campaigns with separate save requirements.

### How this maps to exam topics
- **SDLC / requirements definition** → [[SE_Software_Dev_Process]] (Step 1 needs analysis)
- **Systems modelling (DFDs, structure charts, class diagrams, IPO, data dictionaries)** → [[SE_Object_Oriented_Programming]] §2
- **OOP implementation** → the character classes (Ability, Character, Campaign) are textbook OOP
- **Testing & evaluation against quality criteria** → [[SE_Object_Oriented_Programming]] §4 (effectiveness criteria) and [[SE_Software_Dev_Process]] §5 (testing)
- **Mobile/accessibility + data persistence** → links to [[SE_Web_Programming]] (PWAs, web storage) and [[SE_Secure_Software_Architecture]] (data vulnerability → confidentiality/integrity)

---

## 2. Year 11 — Group Project: Wicked Problems 2025

Assessment Task Notification (Technological and Applied Studies Faculty):
- **Course:** Software Engineering
- **Task Type:** Group project (portfolio + presentation + software solution)
- **Topic:** Object-Oriented Programming
- **Weighting:** 40% (40 marks)
- **Outcomes assessed:** SE-11-01 (plan/develop/engineer software), SE-11-02 (structural elements), SE-11-06 (tools/resources), SE-11-07 (safe/secure solutions), SE-11-08 (language structures), SE-11-09 (manage/document project)
- **Solution:** Python code, groups of ≤3.

### Component 1: Systems Report (using the provided template)
Sections required:
1. **Identifying and Defining** — defining and analysing problem requirements
2. **Researching and Planning** — systems modelling: Algorithms, DFDs, Structure Charts, Class Diagrams, IPO Charts, Data Dictionaries
3. **Producing and Implementing** — screenshots of the program working
4. **Testing and Evaluating** — evaluation against quality success criteria

### Component 2: Presentation
- ≤8 minutes, memorised, professional, "more pictures with very few words" (<10 per slide except noted).
- Required slides: title (group members + name); topics list; problem definition + quality success criteria; systems analysis (DFDs/Structure Charts/Class Diagrams/IPO/Data Dictionaries); one-slide flowchart overview; Gantt chart for the Producing/Implementing phase.

This assessment directly examines the Year 11 OOP + algorithms + dev-process content.

---

## 3. Year 11 — Stage 6 Group Task ([7], [Bilal, Sashank, Daksh])

A Year 11 SE group task submission (group members Bilal, Sashank, Daksh). Treated as a worked example of collaborative SE project work (consistency, code commenting, version control, feedback — see [[SE_Object_Oriented_Programming]] §4.4).

---

## 4. How to use these as exam evidence

In extended responses, you can reference YOUR OWN project work as a concrete example:
- "In my D&D character manager, I applied OOP by modelling Character as a class with ability-score attributes and a point-buy method…"
- "For the Wicked Problems group project, our Systems Report used a DFD at Level 0 (Make X) decomposed to Level 1 processes…"
- This mirrors how Business Studies notes weave Apple/McDonald's — real, specific, verifiable.

---

> **See also:** [[SE_Software_Dev_Process]] | [[SE_Object_Oriented_Programming]] | [[SE_Algorithms_and_Desk_Checks]] | [[SE_Web_Programming]] | [[SE_Secure_Software_Architecture]]
