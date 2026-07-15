---
tags: [software-engineering, year-11, hsc, oop, classes, objects, uml, diagrams, design]
aliases: [SE OOP, Object-Oriented Programming, Class Diagrams, DFD, Structure Charts]
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 11 Object-Oriented Paradigm
created: 2026-07-15
updated: 2026-07-15
---

# Object-Oriented Programming — Year 11 SE

> Self-contained note on OOP concepts, design diagrams (DFD, Structure Chart, Class Diagram), design processes/approaches, and effectiveness & collaboration. Built from INO1–INO4 and the Intro to OOP presentation. Every definition sourced. A known classroom simplification ("redefinition of constructor is polymorphism") is reproduced as written and flagged.

---

## 1. OOP Core Concepts

| Term | Definition (as given) |
|---|---|
| **Object** | "Self-contained unit that consists of both data (attributes) and functionality (methods). It represents a real-world entity or concept." |
| **Class** | "Blueprint or template for creating objects. It defines the properties and behaviors that objects of that type will have." |
| **Encapsulation** | "The bundling of data and methods that operate on the data into a single unit or class. It hides the internal state of an object from the outside world." |
| **Abstraction** | "Process of hiding the complex implementation details and showing only the essential features of an object." |
| **Inheritance** | "Mechanism where a new class (derived class) is created from an existing class (base class). The derived class inherits properties and behaviors from the base class." |
| **Generalisation** | "Process of extracting common properties and behaviors from multiple classes and creating a more general superclass to represent them." |
| **Polymorphism** | "Allows objects of different classes to be treated as objects of a common superclass. It enables methods to behave differently based on the object that calls them." |
| **Attribute** | "A piece of data or a property that belongs to an object … typically represented by variables within a class." |
| **Method** | "Function or subroutine that is defined within a class and operates on objects created from that class." |
| **Instantiation** | "The process where you create an instance of a class … creating an object from a blueprint (class)." |

[All INO1]

### Classroom illustration: Apple / Orange / Fruit
- `class Apple:` with attributes `Colour`, `Shape`, `Taste` and methods `def __init__(): # Constructor`, `def Eat():`. [Intro OOP]
- Inheritance: `class Apple(Fruit):` and `class Orange(Fruit):`. [Intro OOP]
- Instantiation: `GrannySmithApple = Apple()` and `ValenciaOrange = Orange()`. [Intro OOP]
- **Classroom wording (reproduced as written, not a strict CS definition):** "Redefinition of constructor is polymorphism" — each subclass redefines `__init__()`. [Intro OOP]

### JavaScript code mappings (INO1)
- **Object** → `const square = new Rectangle(10, 10);`
- **Class** → `class Student { constructor() { var name; var marks; } getName() {...} setName(name){...} }` then `var stud = new Student(); stud.setName("John");`
- **Inheritance** → `class firstClass { add(){} } class secondClass extends firstClass { add(){ console.log(30+40);} } class thirdClass extends secondClass { add(){} }`
- **Attribute** → `this.height`, `this.width` inside `class Rectangle`.
- **Method** → `calcArea()` / `get area()` inside `class Rectangle`.

### Benefit of instantiation (past-HSC style answer, INO1)
"One benefit of instantiation in OOP is being able to create multiple objects from the same class, each with its own data. For example: `student1 = student("sashank")`, `student2 = student("fayez")`. Each student variable has its own name and can act independently while sharing the same class structure."

### Factors influencing paradigm choice (INO1)
- **Modularity** = how easily the program can be broken into smaller, reusable modules.
- **Data management** = how data is stored, accessed, passed around.
- **Maintainability** = how simple to update, debug, scale without errors.
"OOP is more suitable for complex systems with multiple interacting elements, while procedural programming may be more efficient for simpler, task-driven modules."

---

## 2. OOP Design Diagrams

Three diagram types are taught: **DFD, Structure Chart, Class Diagram**. (Note: object diagrams, UML sequence/communication diagrams, and state diagrams are NOT covered in the provided sources.)

### Data Flow Diagrams (DFD) [INO2]
"A data flow diagram shows the flow of the data among a set of components … The actors are not included in the data flow diagram."
Rules:
- **Boxes are processes and must be verb phrases** → become your **classes** and/or **methods**.
- **Arcs / data flows are noun phrases** → become your **variables or attributes**.
- **Control is not shown** (some sequencing inferred from ordering).
Symbols: Process (transforms data), Data Store (storage), External Entity (outside the system), Data Flow (movement of data).
Intro OOP applies DFDs to the Fruit system: Level 0 (Make Fruit), Level 1 (Process Apple / Process Orange), Level 2 (Initialise fruit → Eat/Drink/Slice/Peel), data flows labelled `Shape, colour, taste`.

### Structure Charts (INO2)
"used to model the hierarchy (top-down design) of processes … Data movements between processes are included … decisions and repetitions are also indicated."
Symbols:
- **Filled circle** = a flag or control variable sent between subroutines.
- **Empty circle** = data flow between subroutines (arguments).
- **Tiny diamond** = a binary or multi-way selection (a choice).
- **Box** = a function / manageable section of code.
- **Control Box** = the first box; tells which part of the program is being diagramed (e.g. `Process invoices`).
- **Parameter vs Control parameter:** a parameter is ordinary data; a control parameter is a flag (filled circle) that affects which path is taken (e.g. `"OK funds"` returned so the parent "now knows that it can generate the cheque").

### Class Diagrams (INO2)
"used to show the hierarchical relationship between classes, especially when there is inheritance, abstraction and/or polymorphism."
Notation:
- **Three compartments:** top = class name, middle = attributes, bottom = methods.
- **Inheritance / subclass** notation: pseudocode `subclass VirtualLibrary is LibrarySystem { … }`; Python `class VirtualLibrary(LibrarySystem):`.
- Multiplicity is handled by **subclassing** rather than UML `1..*` notation: e.g. `LibrarySystem` → `VirtualLibrary` (website URL, copies, regional restrictions) and `PortableLibrary` (vehicle registration, driver licence). "Adding all these items to the LibrarySystem class would make it enormous … The solution is inheritance and polymorphism."
- Intro OOP class diagram: `Fruit` → `shape: string, colour: string, taste: string`, methods `__init__(), Eat(), Drink()`; `Apple` → `__init__(), Slice()`; `Orange` → `__init__(), Slice()` (note: deck labels Orange's method `Slice()` but text elsewhere uses `Peel()`).

### DFD → Structure Chart → Class/Pseudocode → Python pipeline (INO2)
- "The name of the system as given on the Level 0 DFD should be the name of the **class**."
- "The Level 1 DFD process names should ideally be the names of the **methods**."
- "The attributes or variables should come from the **data items on the data flow**."
- "The Structure Chart could be reflected in this code … the main box or control box should be the class name and the modules below it … could also be in the code."
Example skeleton (LibrarySystem) — note the docs plant an **error in the constructor** (`def __init__(admin, teachers, books):` is missing `self`) for students to fix:
```python
class LibrarySystem:
    def __init__(admin, teachers, books):   # error: should be self
        self.adminstaff = admin
        self.teachingstaff = teachers
        self.books = books
    def BorrowBook(BookNumber, StudentID, StudentName): ...
```

---

## 3. OOP Design Processes & Approaches (INO3)

| Approach | Definition |
|---|---|
| **Top-Down** | "starts with the general concept and repeatedly breaks it down into its component parts … from the abstract to the specific." |
| **Bottom-Up** | "starts with the component parts and repeatedly combines them to achieve the general concept … from the specific to the abstract." |
| **Façade Pattern** | "an object that serves as a front-facing interface masking more complex underlying or structural code." Useful "when a system is very complex, has many interdependent classes, or the source code is unavailable." Reduces complexity, dependencies; single entry point. |
| **Agility** | "divide the problem into small chunks … tested both individually and together … added to the main program as they prove their stability … rapid **Design - Build - Test** cycle." |

Top-down + bottom-up are often combined: identify domain objects and refine them (top-down), then compose them (bottom-up). Information hiding / encapsulation: "you do not expose the implementation details of your code, but instead provide well-behaved methods."

---

## 4. OOP Effectiveness & Collaboration (INO4)

### Algorithm Effectiveness Criteria (10)
| Criterion | Definition |
|---|---|
| **Correctness** | "checking if the code does what it's supposed to do … shouldn't break or give weird answers." |
| **Efficiency** | "how fast and how much memory the code needs." (Time + Space complexity.) |
| **Readability & Maintainability** | "like a well-written story that's easy to understand … other people can make changes without getting confused." |
| **Scalability** | "whether the code can handle bigger and bigger tasks without getting slow or messing up." |
| **Robustness** | "the code can handle unexpected things without crashing." |
| **Portability** | "work on different computers without needing lots of changes." |
| **Testing** | "trying out the code to make sure it does what it's supposed to and doesn't have bugs." |
| **Security** | "only the right people can see or change important information" (input validation, injection prevention). |
| **Documentation** | "a user manual for the code … tells you how to use it and what everything does." |
| **Feedback and Iteration** | "making the code better over time … with suggestions and changes." |

### Why OOP is effective
- **Reuse / reusability:** "methods and pointers … Code optimization … also promotes reusability and helps save time."
- **Readability:** "easy to read or understand."
- **Code optimisation:** "a technique that helps make programs run faster and use fewer resources. It is often performed at the end of the development stage. It reduces readability but improves performance."

### Collaboration factors (INO4)
| Factor | How it helps |
|---|---|
| **Consistency** | "speaking the same language within a team" — same coding style/conventions (e.g. camel case `playerName`). |
| **Code Commenting** | "helpful notes for your teammates" — reduces need for back-and-forth explanation. |
| **Version Control** | "a shared timeline of your team's progress" (Git) — track changes, collaborate, revert. |
| **Feedback** | "a support network within your team" — catch errors, learn techniques. |

"By promoting consistency, encouraging code commenting, utilizing version control, and fostering a culture of feedback, teams can work more efficiently … and deliver higher-quality software together."

---

> **See also:** [[SE_Programming_Paradigms]] | [[SE_Algorithms_and_Desk_Checks]] | [[SE_Software_Dev_Process]] | [[SE_Numbering_Systems]] | [[SE_Mechatronics]]
