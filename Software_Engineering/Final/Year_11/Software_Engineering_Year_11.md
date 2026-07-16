---
tags: [software-engineering, hsc, final, exam-ready, year-11]
aliases: [SE Yr11 Final, Software Engineering Year 11 Notes]
cssclass: topic-notes
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 11 (Programming Fundamentals, OOP, Mechatronics)
created: 2026-07-15
updated: 2026-07-15
---

# Software Engineering — Year 11 (Final Exam Notes)

> Complete, self-contained revision document for HSC Software Engineering Year 11. Covers Programming Fundamentals (SDLC, algorithms, desk checks, numbering systems, paradigms), Object-Oriented Programming, and Mechatronics. Built only from classroom sources — no external content.

---

## 1. Software Development Process (SDLC)

**Steps:** requirements definition → determining specifications → design → coding → testing → installation → maintenance → evaluation.

**Tool-to-step mapping (Logic Paradigm Starter):**
- Step 1 (Requirements): needs analysis, requirements definition, flowchart
- Step 2 (Specifications): data dictionary
- Step 3 (Design): flowchart, pseudocode, decision tree, storyboard, algorithm, DFD, structure chart, IPO chart, class diagram
- Step 4 (Coding): control structures
- Step 5 (Installation): phased / pilot / direct / parallel conversion
- Step 6 (Testing): syntax / logic / runtime errors; white / black / grey box testing
- Step 7: installation plan. Step 8: maintenance plan.

**Waterfall (5 stages, PF8):** 1 Define problem → 2 Plan & design (Gantt, context diagram, DFD, system flowchart, test plan) → 3 Implement → 4 Test & evaluate → 5 Maintain.

**Agile (PF8):** 1 Define → 2 Plan/design/implement → 3 Test & evaluate → 4 Release → 5 New requirements (stages 2–5 repeat). "Agile is iterative and flexible; Waterfall is linear and sequential. Agile more adaptable to changing requirements; Waterfall better for well-defined requirements."

**Errors:** Logic (wrong output), Syntax (breaks language rules), Runtime (only at execution).

**Installation methods:** Complete download; Partial download; Cloud-based deployment (e.g. Google Suite, no install). **Conversion:** Parallel (old+new together), Pilot (small group first), Phased (step-by-step), Direct (straight swap).

**Maintenance reasons:** changing user requirements, UI upgrades, data changes, new hardware/software, org focus, gov requirements, poor code. **Maintenance plan** includes: issue, urgency, change description, who, timeframe.

---

## 2. Algorithms & Desk Checks

**Three control structures:** Sequence, Selection, Repetition.

**Pseudocode templates (PF2):**
- `BEGIN … END` (start/end)
- `IF … THEN / ELSEIF … THEN / ELSE / ENDIF` (selection)
- `FOR I = 1 TO … / NEXT` (repetition)
- `WHILE … / ENDWHILE` (pre-test loop)
- `DO … WHILE …` (post-test loop)
- `PRINT` (output), `INPUT` / `READ` / `DISPLAY` (input/output), `LET x = 0` (process)

**Flowchart symbols:** terminator (start/stop), parallelogram (I/O), rectangle (process), diamond (decision), arrow (flow line).

### DESK CHECK RULES (PF2A Q2) — memorise
1. Variables must be there
2. Conditions must be there
3. Output statements must be there
4. Statements appear in the order they do in the code

### How to actually do a desk check (step by step)

A desk check is a **trace table**: you run the code by hand, one line at a time, and write down what each variable holds AFTER every line. That is the whole skill. Markers just want to see your variables tracked step by step.

**Set it up:**
- One column per variable, plus an `OUTPUT` column and a `STEP` column.
- Use `-` for not assigned yet / unknown.
- For an `INPUT` line, drop in the test value you are feeding it.
- After each line, write the NEW value of whatever that line changed.

**Exam rules to lock in:**
- Every variable gets a column, even before it is used. Unused = `-`.
- Write the value AFTER the line runs, not before.
- The condition line (`IF` / `WHILE`) gets its own step. Jot true/false next to it.
- When a loop finishes, show the final FALSE check too. Markers look for that.
- Feed in test data as normal / boundary / extreme. That is the validation side of it.

**Worked example — straight lines (sequence):**
```
x = 5
y = 10
x = x + y
OUTPUT x
```
| STEP | x | y | OUTPUT |
|---|---|---|---|
| 1 | - | - | - |
| 2 | 5 | - | - |
| 3 | 5 | 10 | - |
| 4 | 15 | 10 | - |
| 5 | 15 | 10 | 15 |

Final output = 15. Note x changes twice; row 4 shows the new 15.

**Worked example — WHILE loop:**
```
total = 0
count = 1
WHILE count <= 3:
    total = total + count
    count = count + 1
OUTPUT total
```
| STEP | total | count | OUTPUT | note |
|---|---|---|---|---|
| 1 | 0 | - | - | init |
| 2 | 0 | 1 | - | init |
| 3 | 0 | 1 | - | check 1<=3 TRUE |
| 4 | 1 | 1 | - | total = 0+1 |
| 5 | 1 | 2 | - | count = 2 |
| 6 | 1 | 2 | - | check 2<=3 TRUE |
| 7 | 3 | 2 | - | total = 1+2 |
| 8 | 3 | 3 | - | count = 3 |
| 9 | 3 | 3 | - | check 3<=3 TRUE |
| 10 | 6 | 3 | - | total = 3+3 |
| 11 | 6 | 4 | - | count = 4 |
| 12 | 6 | 4 | - | check 4<=3 FALSE, exit |
| 13 | 6 | 4 | 6 | output |

Final output = 6 (that is 1+2+3). Loop ran 3 times.

**Worked example — IF / ELSE:**
```
age = 16
IF age >= 18 THEN
    status = "adult"
ELSE
    status = "minor"
OUTPUT status
```
| STEP | age | status | OUTPUT |
|---|---|---|---|
| 1 | 16 | - | - |
| 2 | 16 | - | (16>=18? false, go ELSE) |
| 3 | 16 | minor | - |
| 4 | 16 | minor | minor |

Output = "minor".

### Worked Desk Check (a) — Multiplication
```
READ num1, num2
LET multi = num1*num2
DISPLAY multi
```
| num1 | num2 | multi | DISPLAY multi |
|---|---|---|---|
| 2 | 3 | 2*3 = 6 | 6 |
| 5 | 4 | 5*4 = 20 | 20 |
| 7 | 8 | 7*8 = 56 | 56 |
| 10 | 0 | 10*0 = 0 | 0 |

### Worked Desk Check (b) — IF/ELSEIF/ELSE
```
READ isfive
IF (isfive = 5)      DISPLAY "your number is 5"
ELSE IF (isfive = 6) DISPLAY "your number is 6"
ELSE                  DISPLAY "your number is not 5 or 6"
ENDIF
```
| isFive | isFive=5? | isFive=6? | DISPLAY |
|---|---|---|---|
| 5 | T | F | "Your number is 5" |
| 6 | F | T | "Your number is 6" |
| 8 | F | F | "Your number is not 5 or 6" |
| 0 | F | F | "Your number is not 5 or 6" |
| -1 | F | F | "Your number is not 5 or 6" |

### Worked Desk Check (c) — WHILE loop
```
READ count
LET x = 0
WHILE (x < count)
    LET even = even + 2
    LET x = x + 1
    DISPLAY even
ENDWHILE
```
| X | Even (before update) | Even = even + 2 | X = x + 1 | DISPLAY even |
|---|---|---|---|---|
| 0 | 0 | 2 | 1 | 2 |
| 1 | 2 | 4 | 2 | 4 |
| 2 | 4 | 6 | 3 | 6 |
| 3 | 6 | 8 | 4 | 8 |
| 4 | 8 | 10 | 5 | 10 |

**Sorting:** Bubble Sort (swaps if next value higher; source notes a buggy version where swap isn't inside the if → infinite loop). Selection Sort (uses `Swap(A,B)` subroutine).

---

## 3. Numbering Systems

- **Decimal (base 10):** digits 0–9, powers of 10. **Binary (base 2):** 0/1, powers of 2 (8,4,2,1), leading zeros written. **Hex (base 16):** 0–9 then A–F, powers of 16.
- **Binary→Decimal:** sum each bit × place value. `1010` = 8+2 = 10.
- **Hex→Binary:** straight substitution, each hex digit = 4 bits. `3AB2` = `0011 1010 1011 0010`. `F`=1111, `A`=1010, `B`=1011.
- **Hex→Decimal:** digit × 16^position. `DEAF` = 13×4096+14×256+10×16+15 = 57007. `FEED` = 65261.
- **2s complement** (PF7 answers): `-127`→`1 0000001`; `+32`→`0 0100000`; `-14`→`1 1110010`. Binary addition/subtraction worked in source.

---

## 4. Programming Paradigms

- **Object-Oriented (PF4):** Class (blueprint), Object (instance), Encapsulation (bundle data+methods, hide internals), Abstraction (show essentials only), Inheritance (child gets parent's properties/methods), Polymorphism (different classes treated via common interface; same method name, different behaviour), Instantiation (create object from class), Attribute/Property (data), Method (function in class).
- **Logic (PF4):** Variable, Rule ("if this then that"), Facts (knowledge base), Heuristics (shortcuts), Goals, Inference Engine, Backward/Forward Chaining, Expert system.
- **Imperative/Procedural:** named in sources (COBOL example) but NOT defined — do not assume a definition.
- **Functional:** absent from provided docs.

---

## 5. Object-Oriented Programming (detail)

**Design diagrams taught:** DFD, Structure Chart, Class Diagram. (No object/sequence/state diagrams in sources.)
- **DFD:** boxes = verb phrases (→ classes/methods); arcs = noun phrases (→ attributes); no actors; symbols: process, data store, external entity, data flow.
- **Structure Chart:** filled circle = control flag; empty circle = data parameter; diamond = selection; box = function; control box = top.
- **Class Diagram:** 3 compartments (name / attributes / methods); inheritance via `class Child(Parent):`; multiplicity handled by subclassing.

**DFD → code pipeline (INO2):** Level 0 DFD name → class name; Level 1 process names → methods; data-flow items → attributes.

**Design approaches (INO3):** Top-Down (general→specific), Bottom-Up (specific→general), Façade Pattern (hides complexity behind simple interface), Agility (Design-Build-Test cycles).

**Algorithm Effectiveness Criteria (10, INO4):** Correctness, Efficiency, Readability & Maintainability, Scalability, Robustness, Portability, Testing, Security, Documentation, Feedback & Iteration.

**Collaboration factors (INO4):** Consistency (shared style), Code Commenting, Version Control (Git), Feedback.

---

## 6. Mechatronics

**Definition:** Mechanics + Electronics + Computing + Control Systems. Coined by Tetsuro Mori (Yaskawa, Japan). Benefits: efficiency, fewer errors, dangerous-task take-over. Drawbacks: job loss, cost, ethics.

**CPU vs Microcontroller (M2):** CPU = processor only, needs extra parts, general-purpose, fast, complex opcodes. Microcontroller = CPU + memory + I/O in one chip, specific/embedded tasks (e.g. Arduino). Registers: PC (next address), MAR (address accessed), ACC (operation results), CIR/IR (current instruction). **Fetch-execute:** PC→MAR→RAM→MDR→CIR→decode (opcode bits 0–3, operand 4–7)→execute→PC+1.

**Sensors/Actuators (M3):** Sensor transduces physical→electrical (PIR, accelerometer, gyroscope, ultrasonic, LDR, I2C light, joystick). Actuator converts electrical→mechanical (servos, hydraulic, gripper). Data layer: operational/diagnostic/optimisation data; feedback loop sensor→controller→actuator.

**Control algorithms (M4):** read sensors → compute toward set point → output to actuators. **Open-loop** (no feedback: TV remote, traffic light, washing-machine timing) vs **Closed-loop** (feedback: cruise control, steering, A/C, line-follower). Three closed-loop types: On/off (bang-bang), Proportional (correction ∝ error; small steady-state error), PID (integral removes error; derivative damps overshoot).

**Electricity (Starter answers):** ammeter in series, voltmeter in parallel. Putty at 25 cm, 0.15 A → **37.5 Ω**; PD = 37.5×0.15 = **5.625 V**. "thicker putty = lower resistance." Reliability: repeat + mean.

---

## 7. HSC Exam Response Structures

**Verb → what to do:**
- **Define:** state meaning + essential qualities
- **Describe:** characteristics/features
- **Explain:** cause and effect; why/how
- **Analyse:** components + relationships + implications
- **Justify:** support an argument
- **Evaluate:** judgement by criteria

**Desk-check question scaffold:** (1) Write header row with every variable, condition, output in code order. (2) Execute row-by-row. (3) For loops, one row per iteration tracking counter + changed vars.

**Paragraph scaffold (extended):** Topic sentence (define term) → explain with mechanism → apply to a scenario (your D&D app / Wicked Problems project / a given case) → link to a syllabus concept (e.g. security by design, effectiveness criterion).

---

## 8. Quick Revision Checklist
- [ ] Name the 8 SDLC steps and a tool for each
- [ ] Waterfall vs Agile difference
- [ ] 4 desk-check rules + can run one
- [ ] Pseudocode templates (IF/WHILE/FOR/REPEAT)
- [ ] Binary/hex conversion (straight substitution)
- [ ] OOP 4 pillars (encapsulation, inheritance, polymorphism, abstraction) + definitions
- [ ] DFD/Structure/Class diagram notation
- [ ] CPU vs microcontroller; fetch-execute steps
- [ ] Open vs closed loop; PID
- [ ] 10 effectiveness criteria

---

> **See also:** [[Software_Engineering_Year_12]] | [[SE_Your_Projects]]
