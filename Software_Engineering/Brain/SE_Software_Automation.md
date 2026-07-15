---
tags: [software-engineering, year-12, hsc, software-automation, ai, machine-learning, regression, neural-networks, decision-trees, ethics]
aliases: [SE Automation, AI vs ML, Machine Learning, Regression, Neural Networks]
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 12 Software Automation
created: 2026-07-15
updated: 2026-07-15
---

# Software Automation (AI/ML) — Year 12 SE

> Self-contained note on AI vs ML, types of ML, regression (linear/polynomial/logistic/KNN) with worked examples, decision trees & neural networks, the psychology/cognition links, and the ethics/limits of automation. Built from SA1–SA4 and the Student Version pptx. Every definition sourced. (Note: the SA0 .xlsx starter was not readable from the source set — flagged, not fabricated.)

---

## 1. AI vs ML Distinction (SA1)

- **Artificial Intelligence (AI):** "a broad field of computer science focused on creating systems that can perform tasks requiring human-like intelligence. AI encompasses reasoning, problem-solving, perception, language understanding, and learning. It includes rule-based systems, expert systems, robotics, and machine learning."
- **Machine Learning (ML):** "a subset of Artificial Intelligence (AI) that enables computers to learn from data and improve their performance over time without being explicitly programmed. It involves algorithms that identify patterns, make decisions, and adapt based on experience."
- **Relationship:** ML is a **subset** of AI. AI is the broader concept; ML is one (data-driven) way of achieving it.

### Types of ML (SA1)
- **Supervised:** "taught using labeled examples … finds patterns from past examples to make predictions."
- **Unsupervised:** "given a lot of data but no answers. It figures out patterns by itself."
- **Semi-Supervised:** "some labeled examples but also a lot of unlabeled data."
- **Reinforcement:** "learns by trial and error and gets rewards or penalties based on its actions."

### Regression types (overview; maths in SA2) (SA1)
- **Linear Regression:** "drawing a straight line that helps guess" a value; good where one thing increases as another increases.
- **Logistic Regression:** "helps computers make yes/no decisions, like 'Will it rain?'"
- **K-Nearest Neighbors (KNN):** "group things by looking at what's nearby."
- **Polynomial Regression:** "finds patterns that aren't straight … draws a curvy line."
- Regression generally: "using past and present mathematical data to predict future values i.e. consequences. Also known as finding the Line of Best Fit."

### Automation ML supports (SA1)
- **DevOps:** combines software dev + IT operations; automation manages deployment, monitors, fixes errors; ML predicts failures.
- **RPA (Robotic Process Automation):** automates repetitive tasks (data entry, invoices, customer responses); bots learn from past actions.
- **BPA (Business Process Automation):** automates entire workflows; integrates multiple systems/departments.

---

## 2. Applying ML & Regression (SA2)

### Linear Regression via Least Squares (SA2)
Goal: "make the equation of a straight line of best fit y = mx + b." Build `x | y | xy | x²` table, sums Σx, Σy, Σxy, Σx², n = data points; compute slope **m** and intercept **b**.
- Worked 1: x=[1,2,3,4,5], y=[2,3,5,6,8] → **y = 1.5x + 0.3** (x=1→1.8, 2→3.3, 3→4.8, 4→6.3, 5→7.8).
- Worked 2: x=[2,4,6,8], y=[3,4,7,9] → **m = −9.5, b = 58 → y = −9.5x + 58** (x=2→39, 4→20, 6→1, 8→−18).

### Polynomial Regression via Least Squares, matrix form (SA2)
Goal: "make the equation of a curve y = ax² + bx + c." Choice rule: plot data; curvy → polynomial, straight → linear.
Worked: x=[1,2,3,4,5], y=[2,5,10,17,26] → **y = x² + 1** (x=1→3, 2→7, 3→13, 4→21, 5→31).
Second: x=[2,4,6,8,10], y=[4,12,18,22,25]; n=5 → **a=0.25, b=2.75, c=78 → y = 0.25x² + 2.75x + 78**.

### Logistic Regression (SA2)
Aim: "calculate the probability of something being a yes (1) or no (0)." Produces a **sigmoid / S-curve from 0 to 1**. Passing-grade example: "passing grade is approximately 3.5, where the curve crosses the 0.5 probability threshold." Mark 4.5 → "Approximately 50%"; mark 7 → "Approximately 95%."

### K-Nearest Neighbour (KNN) (SA2)
"KNN Regression does not make data fit a formula. Instead, it highlights K points within range of the Line of Best Fit … will not be smooth." Increasing K changes which points are near the line.

### Programming regression (SA2)
Linear (Python): compute n, Σx, Σy, Σxy, Σx²; `m = (n*Σxy − Σx*Σy) / (n*Σx² − Σx²)`, `b = (Σy − m*Σx) / n`; print `y = mx + b`. Polynomial: `numpy.polyfit(x, y, 2)` → a, b, c.

---

## 3. Decision Trees, Neural Networks & Psychology (SA3 + Student)

- **Neural Networks:** "a type of machine learning model inspired by the human brain. Layers of interconnected neurons … effective for recognising patterns in large, complex datasets." Architecture: **Input layer → Hidden layer → Output layer**. Excel at image recognition, NLP, deep learning; need lots of data/compute; often "black boxes" (lack interpretability).
- **Decision Trees:** "splits data into branches based on feature-based rules, forming a tree-like structure." Used for classification and regression; "clear, interpretable"; "can suffer from overfitting if not properly pruned."
- **Suitability:** Neural Networks → self-driving, recommendations, face recognition, image/spam. Decision Trees → semi-supervised note task, fruit-grouping (unsupervised), math-with-answers (supervised), spam filter.
- **Application buckets:** Data Analysis & Forecasting (Regression KNN averages similar points; Decision Tree transparent decisions), Virtual Personal Assistants (Logistic classifies intent; Neural net powers NLP), Image Recognition (Logistic binary classification; Neural net CNN detects edges/shapes).

### Psychology / cognition links (Student)
- Terms: Stimulus, Response, Arousal, Impulse, Regulation.
- Psychological responses: Regression, Conditioning, Habituation, Sensitisation, Flight-Fight-Fawn, Stress.
- **"Goldilocks Zone":** "between complete impulsivity and total regulation" — the band IT companies exploit.
- Human behaviour influencing AI: psychological response, acute stress, cultural protocols, belief systems.

---

## 4. Ethics & Limits of Automation (SA4 + Student)

**Driving question:** "To what extent should software automation rule the world?"

Must address impacts on: **safety of workers; people with disability; nature/skills of employment; production efficiency, waste, environment; economy and wealth distribution.** Must explore "how patterns in human behaviour influence ML and AI … psychological responses; acute stress response; cultural protocols; belief systems." Note: "Do not use AI in this classroom task." [SA4]

### Benefits
- **Safety:** AI image recognition detects hazards (construction), defects (manufacturing).
- **Disability:** screen readers, self-driving cars for mobility.
- **Employment:** repetitive tasks automated → demand for data analysis, AI programming, tech-ethics skills; upskilling needed.
- **Efficiency/environment:** ML catches errors early (less waste); AI energy-management lowers carbon.
- **Economy:** "AI can boost productivity, but raises concerns about job displacement. Wealth distribution may become more unequal unless governments invest in retraining."

### Risks / manipulation
- **Fake news & 2016 US election:** bot accounts, fake-news sites; algorithms "amplified content aligned with existing views"; social engineering exploits cognitive biases.
- **COVID vaccine misinformation:** clickbait/fabricated testimony → hesitancy.
- **Astroturfing:** fake grassroots/fake accounts to discredit or promote.
- **Bias:** syllabus requires investigating "the effect of human and dataset source bias."
- **Human oversight implied:** weigh ethical implications, bias, need for retraining/safeguards — automation bounded by human judgement.

---

## 5. Coverage note
- **SA0 Starter (.xlsx)** is referenced in the Student pptx as a "tell a story with data" starter using `=COUNTIF` and charts, but the .xlsx was **not present in the readable source set** and could not be extracted. Not fabricated.
- The `Key Terms - Software Engineering.pdf` contains **HSC command terms only** (List/State/Define/Describe/Explain/Analyse/Justify/Evaluate; Create/Present/Design/Develop) — no AI/ML-specific vocabulary.

---

> **See also:** [[SE_Web_Programming]] | [[SE_Secure_Software_Architecture]] | [[SE_Software_Dev_Process]] | [[SE_Algorithms_and_Desk_Checks]]
