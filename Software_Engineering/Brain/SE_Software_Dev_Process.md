---
tags: [software-engineering, year-11, hsc, software-dev-lifecycle, processes]
aliases: [SE SDLC, Software Development Steps, Software Process]
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 11 Programming Fundamentals
created: 2026-07-15
updated: 2026-07-15
---

# Software Development Process — Year 11 SE

> Self-contained note on the software development steps (SDLC), the tools used at each step, the structured (Waterfall) vs Agile approaches, and comparative software dev approaches. Built only from the classroom docs (PF1, PF2, PF3, PF5, PF8, Logic Paradigm Starter). No external content added.

---

## 1. The canonical software development steps

The classroom materials name these steps across the PF series: requirements definition, determining specifications, design, coding, testing, installation, maintenance, evaluation.

### Step-to-tool mapping (from the Logic Paradigm Starter)

Each tool/term is associated with a step number. These are the literal relationships students were asked to produce:

- **Step 1 (Requirements):** needs analysis, requirements definition, flowchart
- **Step 2 (Specifications):** data dictionary
- **Step 3 (Design):** flowchart, pseudocode, decision tree, storyboard, algorithm, Data Flow Diagram (DFD), structure chart, IPO chart, class diagram
- **Step 4 (Coding):** control structures
- **Step 5 (Installation):** phased conversion, pilot conversion, direct conversion, parallel conversion
- **Step 6 (Testing):** run-time error, syntax error, logic error, white box testing, black box testing, grey box testing
- **Step 7 (Installation/delivery):** installation plan
- **Step 8 (Maintenance):** maintenance plan

Source: `Logic Paradigm Starter.pdf` (the relationship facts `software_steps("flowchart", 1).`, `software_steps("pseudocode", 3).`, etc.).

> Note: the "Logic Paradigm Starter (Answers)" file is only a template, not a filled answer key. The associations above come from the student-version starter which lists them.

---

## 2. Requirements Definition and Determining Specifications (Step 1 and 2)

From `PF1`, four case studies with student-completed requirement/specification analyses:

- **(a) Computer-controlled baggage sorting system** — Requirements: sort baggage by reading bar-coded label (passenger class + destination), move along conveyor to assigned chute. Specifications: (1) day's flight schedule loaded to find bottlenecks / compress chute count; (2) Automatic "Compression Rules" used; (3) chutes assigned per destination+class; (4) chute assignments auto-changed as bookings vary.
- **(b) ABC Motel** — Requirements: reserve rooms tracking availability in real time; issue bills, record payments, give receipts; integrate credit card + EFTPOS. Specifications: allow credit card/EFTPOS; auto-generate financial reports to XYZ Company.
- **(c) Old bank system (COBOL, imperative paradigm)** — Requirements: add new customers; create multiple account types (savings, cheque, loan); process deposits/withdrawals with real-time balance updates; prepare statements; delete customers whose accounts all closed.
- **(d) Theatre booking system (80 seats, 8 rows x 10)** — Requirements: identify/print unsold seats on purchase enquiry via interactive theatre display. Specifications: store/track all 80 seats; identify+display unsold seats on enquiry; print list of available seats.

---

## 3. The Structured (Waterfall) Approach — 5 stages (PF8)

"There are five main stages to the Structured Approach (often called the Waterfall Model)."

1. Defining and understanding the problem
2. Planning and designing
3. Implementing
4. Testing and evaluating
5. Maintaining

Stage descriptions (PF8):
- **1. Defining and understanding the problem:** "Read the problem and understand the user needs and specifications."
- **2. Planning and designing:** the project is planned in detail. Documents such as Gantt charts, context diagrams, DFDs, and system flowcharts are created. Budget, hardware/software needs, timeframes determined. A test plan is created.
- **3. Implementing:** the system is built and installed.
- **4. Testing and evaluating:** testing ensures it meets requirements (can users operate it, run tests, verify it does its job). Fixes applied if needed.
- **5. Maintaining:** ongoing updates/improvements. Strategies: running old and new together, step-by-step changes, or changing a small part before transitioning everything.

Task-to-stage mapping (PF8, verbatim):
| Task | Stage |
| Requirements report | 1 |
| Preliminary investigation | 1 |
| Gantt Chart | 2 |
| Context diagram | 2 |
| Data Flow Diagram (DFD) | 2 |
| Systems Flowchart | 2 |
| Work out your budget | 2 |
| Choose computers | 2 |
| Write test plan | 2 |
| Install new software | 3 |
| Check if people can use it | 4 |
| Check to see if the system does its job | 4 |
| Change straight away | 4 |
| Run old and new at the same time | 5 |
| Change slowly step-by-step | 4 |
| Change small part, then everything | 4 |

---

## 4. Agile Approach (PF8)

Stages (repeated cyclically):
1. Defining and understanding the problem
2. Plan, design and implement
3. Test and evaluate current solution
4. Release working version to users
5. Define and understand new requirements
("Note that stages 2 - 5 are repeated.")

**Agile vs Waterfall (verbatim from PF8):**
- "The Agile approach is iterative and flexible, whereas the Structured (Waterfall) approach is linear and sequential."
- "In Agile, development occurs in cycles where small updates are tested and released frequently."
- "Structured development follows a fixed sequence, meaning each phase is completed before moving to the next."
- "Agile is more adaptable to changing requirements, while Waterfall is better for projects with well-defined requirements from the start."

---

## 5. Testing, Installation, Maintenance (PF5)

### Types of coding errors
- **Logic:** code written which does not produce the desired output or otherwise does not work correctly.
- **Syntax:** statements written do not follow the rules of the target programming language.
- **Runtime:** occur when the program is actually run/executed and may not appear before everything else is done.
(Student note: "Logic and Syntax errors as the ones that mainly happen.")

### Testing / evaluation methods (tick as appropriate for the bubble-sort algorithm) — all ticked:
- Looking at different versions of the same problem
- Peer checking (getting someone you work with to check the program)
- Structured walk through (guided tour of program)
- Desk checking
- Checking solution against Needs Analysis in Defining and Understanding stage

### Debugging techniques
- **Stubs:** 'dummy' procedures/fragments of code placed there to test program logic or execution, completed later.
- **Flags:** a Boolean variable that checks whether something is executed or done as intended (example: `fileSuccess` set true if a file loads correctly).
- **Debugging output statements:** output statements showing what stage the program is at (one of the most common strategies).
- **Automated debugging tools:** variable watch statements (tracks a variable's value live), breakpoints (program stops but keeps memory), trace stepping (execute one line at a time).

### Internal / intrinsic documentation
"Internal or intrinsic documentation for developers is vital if your programming source code is to be understood and thus extended or expanded on in the future. This can take the form of good, clear variable names, use of whitespace, use of comments, appropriately-sized procedures etc."
A sample (`mysteryalgorithm` with vague names `a`, `do something`, inconsistent indentation, no comments) is judged NOT good internal documentation.

### Installation methods (how software is delivered)
- **Complete download and installation:** user clicks a link / USB / double-clicks an archive or executable; files copied to a location; "a lot of programs nowadays use customised installers."
- **Partial download and installation:** downloading a part, then running the rest online or downloading essential bits as required.
- **Cloud-based deployment:** requires no software installation; runs through an internet-enabled application such as a web browser. Best example: Google Suite or Microsoft Office Online.

### Installation / conversion methods (four main)
- **Parallel conversion:** old and new system used at once for a time, then new takes over completely.
- **Pilot conversion:** a small team/department/component uses the entirety of the new system, then everyone else depending on its success.
- **Phased conversion:** new system gradually implemented step by step until no old system remains.
- **Direct conversion:** new system implemented/installed straight away with no time the old system is in use.

Software to method mapping (PF5):
| Software | Installation method | Conversion method |
| Facebook | Cloud-based deployment | Direct conversion |
| Instagram | Cloud-based deployment | Direct conversion |
| Gmail | Cloud-based deployment | Direct conversion |
| Adobe Connect | Partial download and installation | Pilot conversion |
| Microsoft OneNote | Complete download and installation | Parallel conversion |
| Fortnite | Complete download and installation | Parallel conversion |
| Mario RPG | Complete download and installation | Direct conversion |
| Microsoft Teams | Cloud-based deployment | Parallel conversion |

### Maintenance
Major software/websites are changed/upgraded per changing legal, customer or technical needs. Reasons: changing user requirements; upgrading the UI; changes in the data to be processed; new hardware/software; changing organisational focus; changes in government requirements; poorly implemented code.

A **maintenance plan** should include: the issue, the level of urgency of the change, the type/description of the change required, who has to do it and the time frame.
Examples given: *Sentral* (data-to-be-processed changes / RFID gate errors; High; Building Management + Sentral DB admins + developers; 1 week) and *Microsoft Teams* (bad third-party integration — Medium/2 weeks; outdated UI — low/3 weeks; security concerns — High/1 week).

---

## 6. Comparative Software Development Approaches (PF8 summary)

- **Structured (Waterfall):** Linear/sequential; each phase completed before moving to the next. "Waterfall is better for projects with well-defined requirements from the start."
- **Agile:** Iterative and flexible; development in cycles, small updates tested and released frequently; more adaptable to changing requirements.

---

> **See also:** [[SE_Algorithms_and_Desk_Checks]] | [[SE_Numbering_Systems]] | [[SE_Programming_Paradigms]] | [[SE_Object_Oriented_Programming]] | [[SE_Mechatronics]] | [[SE_Web_Programming]] | [[SE_Software_Automation]] | [[SE_Secure_Software_Architecture]]
