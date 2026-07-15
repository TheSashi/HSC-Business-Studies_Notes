---
tags: [software-engineering, year-11, hsc, paradigms, object-oriented, logic, imperative, procedural]
aliases: [SE Paradigms, Programming Paradigms, OOP, Logic Paradigm]
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 11 Programming Fundamentals
created: 2026-07-15
updated: 2026-07-15
---

# Programming Paradigms — Year 11 SE

> Self-contained note on the programming paradigms covered in the classroom docs (Object-Oriented and Logic defined in full; Imperative/Procedural named but NOT defined in sources; Functional absent from sources). Every definition is sourced from PF4. Gaps are flagged honestly — no invented definitions.

---

## 1. Object-Oriented Paradigm — definitions (PF4)

- **Class:** "A blueprint or template for creating objects. It defines the properties and methods that objects of this class will have."
- **Object:** "An instance of a class that has specific values for its properties and can perform methods defined in the class."
- **Properties:** "Characteristics or data associated with an object. These define the state of the object."
- **Attributes:** "Another term for properties, representing variables that store information about an object."
- **Methods:** "Functions defined inside a class that describe the behaviors of an object."
- **Variables:** "Containers that store data values, which can be used as attributes of objects or independently within a program."
- **Abstraction:** "The process of hiding complex implementation details and showing only essential features to the user."
- **Instantiation:** "The creation of an object from a class."
- **Inheritance:** "A mechanism in OOP where a new class (child class) inherits properties and methods from an existing class (parent class)."
- **Polymorphism:** "The ability of different classes to be treated as instances of the same class through a common interface. Methods in different classes can have the same name but perform different tasks."
- **Encapsulation:** "The bundling of data (attributes) and methods that operate on the data within a single unit (class), restricting direct access to some details."

PF4 also works through an `ArrayWorker` class (pseudocode) whose purpose is: "useful for managing the size of the array when needed."

See [[SE_Object_Oriented_Programming]] for OOP design diagrams, processes, and effectiveness.

---

## 2. Logic Paradigm — definitions (PF4)

- **Variable:** "A name that holds a value, like a box storing something."
- **Rule:** "A 'if this, then that' statement. Example: If it rains, the ground is wet."
- **Facts (Knowledge Base):** "True statements we already know."
- **Heuristics:** "Smart guesses or shortcuts to find answers faster."
- **Goals:** "What we are trying to find out."
- **Inference Engine:** "The part of a system that figures things out using rules and facts."
- **Backward Chaining:** "Starts with the goal and works backward to find the facts."
- **Forward Chaining:** "Starts with facts and keeps adding new information."
- **Expert system:** "A smart computer that gives advice like a human expert."

Logic paradigm Prolog examples given (solar system; animals/pets; `eat` transitive rule `eat(A,C) :- eat(A,B), eat(B,C).`).

---

## 3. Imperative / Procedural paradigm (what the sources actually say)

- The Terminology starter lists an "Imperative (Procedural) Paradigm" table with rows **If** and **For** (definition/example cells left blank in the source).
- PF1 (Old bank system): "was written using the programming language COBOL (Common Business Oriented Language), which supports the imperative programming paradigm."
- **No full definition of imperative/procedural is provided in the extracted texts.** Do not assume one for the exam unless your teacher gives it.

---

## 4. Functional paradigm

**Not present in any source document in this cluster.** No definition, no example. The classroom docs do not cover it.

---

## 5. Honest coverage report

| Paradigm | Status in sources |
|---|---|
| Object-Oriented | Fully defined (PF4) |
| Logic | Fully defined (PF4) |
| Imperative / Procedural | Named only; definition cells blank; COBOL example only |
| Functional | Absent from all provided docs |

No paradigm *comparison table* is given in the sources. The OOP vs Procedural comparison that IS supported appears in [[SE_Object_Oriented_Programming]] (modularity, data management, maintainability from INO1).

---

> **See also:** [[SE_Object_Oriented_Programming]] | [[SE_Algorithms_and_Desk_Checks]] | [[SE_Software_Dev_Process]] | [[SE_Numbering_Systems]] | [[SE_Mechatronics]]
