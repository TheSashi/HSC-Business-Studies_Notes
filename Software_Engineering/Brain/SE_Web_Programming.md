---
tags: [software-engineering, year-12, hsc, web, client-side, server-side, networking, big-data, w3c, version-control, security-web]
aliases: [SE Web, Programming for the Web, Client vs Server, Networking]
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 12 Programming for the Web
created: 2026-07-15
updated: 2026-07-15
---

# Programming for the Web — Year 12 SE

> Self-contained note on client-side vs server-side, networking, big data, W3C standards, version control & open source, server-side & CMSes, secure web services, the need for standards, JavaScript/web algorithm description, and the Caesar cipher (including the flagged error in the starter doc). Built from W1–W7, W3, Starters, JS1.2/1.3/1.5, and the MAIN web PDF. Every definition sourced.

---

## 1. Client-Side vs Server-Side Programming

- **Client:** "your device, like your phone or computer." **Server:** "a powerful computer that stores and manages websites." (customer ordering food vs kitchen staff). [W1]
- **HTML** displays structure; **CSS** makes it pretty; **JS** makes it interactive. [W1]
- **Client-side:** "your interaction with the restaurant … displaying the webpage, handling user interactions, running JavaScript." Languages: JavaScript, HTML, CSS. [W1]
- **Server-side:** "the kitchen staff preparing your meal … retrieving information from a database, processing requests, generating content." Languages: PHP, Java, Python, Ruby on Rails (JavaScript usable both; Node.js is server-side). [W1]
- **When used:** Client renders UI, handles clicks (YouTube); Server stores data, processes search. e-Commerce: Client displays cart/checkout; Server manages DB, processes transactions securely. [W1]
- **Full-stack:** browser (JS/jQuery/Angular/Vue), server (PHP/ASP/Python/Node), database (SQL/SQLite/MongoDB). [MAIN]
- **Stacks:** MERN (MongoDB, Express, React, Node); MEAN (MongoDB, Express, Angular, Node). [MAIN]
- **PWA (client-side):** interactivity, dynamic updates without reload, offline via service workers, local storage (IndexedDB/LocalStorage). [MAIN]

---

## 2. Networking Fundamentals (W2 + MAIN)

### Hardware
- **Hub:** data in/out one cable; slow; small networks. "like a road where all cars meet at an intersection."
- **Switch:** many in/out; "traffic lights"; large networks/offices.
- **Router:** "best way" for data; "Sat-Nav"; connects to internet.
- **Bridge:** connects two *same* networks. **Gateway:** connects two *different* networks.

### Topologies
Star (central device), Ring (circular one-direction), Bus (single line, terminators), Hybrid, Wireless (Starlink example). Student examples: bus=lift control, ring=driverless metro, mesh=GPS, cloud=social media, client-server=online games. [W2]

### MAC vs IP
MAC "permanent"; IP "changes depending on connection." Both show "where a computer is located." Highest IPv4 = 255.255.255.255; IPv6 = FFFF… (hex). [W2]

### DNS
"Like a phone book for the internet … translates [website name] into an IP address." Primary DNS asked first; secondary has a copy if unavailable. [W2]

### Packets / packet switching
"ensuring data packets get to their destination on time and as free of errors as possible … even if sent out of sequence." Each packet has source address, destination address, sequence number. [W2]

### Protocols & Ports
| Protocol | Port | Use |
|---|---|---|
| HTTP | 80 | General websites |
| HTTPS | 443 | Banking/secure sites |
| FTP | 21 | File transfer |
| SMTP | 25 | Sends mail |
| POP | — | Collects email |
| DNS | 53 | Name resolution |
| SSH | 22 | Secure shell (cloud/enterprise) |
| SSL | — | Encrypts connections |

"Closing unnecessary ports helps prevent attacks." Local dev servers often use `localhost:3000`; APIs front-end 3000 / back-end 5000; manage CORS. [MAIN]

### Browser↔Server request lifecycle [MAIN]
1. User enters URL → 2. DNS lookup → 3. HTTP/HTTPS request via resolved IP → 4. Server responds with files (HTML/CSS/JS/images) → 5. Browser renders (DOM interpreter, CSS interpreter, JS engine with JIT).

### `tcpdump`
Command-line packet capture (shows IPs, ports, protocols); used for debugging traffic, checking ports 80/443, diagnosing SSL/TLS, performance. [MAIN]

---

## 3. Big Data (W4 + MAIN)

### The 6 V's
"velocity, volume, value, variety, veracity and variability — the six main and innate characteristics of big data." [MAIN]

### Data hierarchy [W4]
- **Data:** "Raw facts or values with no context" (log-in timestamps).
- **Information:** "Data that has been processed to make meaning" (chart of peak log-in hours).
- **Knowledge:** "Insights formed by analysing information" (users log in after school).
- **Understanding:** "Ability to apply knowledge to make decisions" (adjust server load).
- **Data mining:** "Automatically analysing large data sets to detect trends or patterns."
- **Metadata:** "'Data about data' — descriptive details" (file size, date created, author).

### Web mining [MAIN]
- **Content mining:** text/images/audio/video; text mining/ML/NLP.
- **Structure mining:** how pages link (nodes/edges); Google ranking uses it.
- **Usage mining (log mining):** clicks, time, navigation paths.

### Social media collects [W4]
Location, device info, contacts, search history, messages metadata, likes/comments/shares, browsing history, ad interactions, time spent, uploaded media, age & account details, biometric info (face patterns).

### Social/ethical issues [W4]
Data privacy, data security, data validation, data accuracy, data sanitisation.

### Effect on web architecture [MAIN]
Facebook (500 TB/day), YouTube (300 hrs video/min), Amazon (up to 2.5M price changes/day; 35% sales from recommendations), Netflix, Starbucks. Needs data warehouses + analytics servers; CDNs; real-time protocols (HLS, DASH); ML + metadata. Example app "TuneMatch": data mining (listen/skip/playlist), metadata (artist/album/genre/mood/year), streaming (small chunks).

---

## 4. W3C Standards (W5 + MAIN)

- **W3C:** "develop open, consistent standards so the World Wide Web stays accessible, reliable, and works the same across all browsers, devices, and countries." Works with governments, unis, companies, browser devs, accessibility groups. [W5]
- **Standards:** HTML, CSS, XML, SVG, WCAG (accessibility), Web APIs, browser & security specs.
- **Why standards matter:** "Ensures websites work consistently … reduces compatibility issues, improves accessibility, supports global languages, increases long-term stability."
- **WAI (Web Accessibility Initiative):** guidelines/tools for disabilities (visual, hearing, mobility, cognitive). Tools: Screen reader, Screen magnifier, Speech-to-text, Sticky Keys. [W5]
- **Internationalisation (i18n):** support different languages/scripts without redesign. Affects: UTF-8, ltr/rtl, language tags. Supports Arabic/Hebrew (RTL). [MAIN]
- **Privacy vs Security:** "Privacy is about rights … security provides the technical measures (e.g. encryption, authentication)." Standards: Threat Modelling, WebAuthn, Federated Identity, Web Payment Security. [W5]
- **Validation:** `validator.w3.org` checks HTML/CSS against standards. [MAIN]

---

## 5. Version Control & Open-Source Dev Tools (W6 + MAIN)

- **Version control:** "keeps track of changes made to files over time … return to a previous version if something goes wrong." Saves snapshots called **commits**. [W6]
- **Git/GitHub terms:** Fork (copy in your account), Repository (folder + history), README, Commit (saved change w/ message), Push origin (upload to GitHub). [W6]
- **Other VCS:** GitLab/GitHub (distributed); SVN (centralised, needs server). [W6]
- **Open-source:** "Source code is publicly available. Anyone can: view, modify, improve, share, build tools on top of it." Examples: React, Vue, Angular, Svelte, Tailwind, Bootstrap (front-end); Node, Express, Django, Flask, Rails, PHP/Laravel (back-end); MySQL, PostgreSQL, MongoDB, SQLite (DB); Linux, Docker, Nginx, Apache (infra). [MAIN]
- **"Missing Feature Disaster" scenario** shows why VCS matters: USB-stick version confusion, merge chaos, accidental deletion, no backup. [MAIN]

---

## 6. Server-Side Programming & CMSes (W7)

- **Web server:** "a giant computer that holds all the website's content … dynamic behaviour handled by server-side programming." Languages: Python, PHP, Java — "interact with the database … generate the HTML the browser sees." [W7]
- **MVC:** Model (data/logic), View (what user sees), Controller (handling requests). [W7]
- **CMS:** "Like a website builder … templates, tools, features to add pages, images, text." WordPress, Drupal, Joomla. Advantage: "easier to create and manage content, even without extensive programming experience." [W7]
- **Framework PMI:**
  - React (JS, Meta): component-based, Virtual DOM; steep curve, "just a library," paired with Next.js.
  - Angular (JS/TS, Google): strong typing; steep, verbose, enterprise.
  - Express.js (JS, Node): minimalist/flexible, fast; unopinionated, callback hell; "E" in MEAN/MERN.
  - Django (Python): rapid, secure, scalable; steep, monolithic, not ideal real-time; has ORM.
  - Flask (Python): lightweight, easy; not ideal complex projects, lacks built-in DB/auth.
  - WordPress: easy, large community; security concerns, not ideal complex apps.
  - Joomla: secure, scalable, multi-language; steep, fewer themes.
- **DB connectivity:** Node + Express + MySQL example: `mysql.createConnection`, route `app.get('/')`, `SELECT name, address FROM customers`, render via EJS. [W7]

---

## 7. Secure Web Services (W3 + MAIN)

- **SSL** (Netscape, 1995) encrypts data between site & user; verifies identity via **handshake** ("digital signature"); replaced by **TLS** (more secure). "Websites that use SSL or TLS have 'HTTPS'." [W3]
- **TLS handshake:** (1) TCP connection; (2) client "client hello" (cipher suites + TLS version), server "server hello" + SSL certificate (public key, hostname, expiry), client validates; (3) client generates session key, encrypts with public key, server decrypts with private key; (4) both hold symmetric session key → encrypted channel. [MAIN]
- **Encryption types [W3]:** Hash functions (no key; integrity, digital signatures; MD5), Symmetric-key (same key; fast; AES "gold standard" 128-bit), Asymmetric/public-key (public + private; secure comms + signatures).
- **Authentication vs Authorisation [W3]:** Authentication = "checking access credentials against a database/list." Authorisation = "permits certain usernames/passwords access to connect." "You can have authentication without authorisation, but you cannot have authorisation without authentication."
- **Digital signatures [W3 + MAIN]:** hash message → encrypt hash with **private key** (the signature) → send + signature → receiver decrypts with **public key**; if it matches message hash, confirms **integrity** + **authenticity**.
- **Cryptography [STUDENT]:** science of securing by encrypting/decrypting. Asymmetric = public+private; symmetric = same key.

---

## 8. Need for Standards (Starter 5)

Scenario: design a new web-based robot-control language for other planets with **no standards** — anyone invents arbitrary syntax → interoperability impossible. Motivates W3C/standardisation. Required keywords: `detectObstacle`, `moveForward`, `moveBackward`, `moveLeft`, `moveRight`, `stopRobot`, `startRobot`, `armForward`, `armBackward`, `armGrab`, `armPlaceInTray`. [Starter5]

---

## 9. JavaScript / Web Algorithm Description (JS1.2/1.3/1.5 + MAIN)

- **IPO model:** Input (keyboard/mouse/files), Process (math, decisions), Output (pictures/graphs/changed data). IPSO for PWAs adds Storage. [JS1.2/MAIN]
- **Methods of algorithm description:** Structured English (numbered steps), Flowcharts (Start/Stop, Process, Decision, I/O, Flow line). [JS1.2/1.5]
- **Control structures [JS1.3 + MAIN]:**
  - **Sequence:** logical steps one after another.
  - **Selection:** binary (two options) / multiway (more than two) — in JS `if / else if / else`, operators `== < > <= >= != ! && ||`.
  - **Repetition:** pre-test (condition at top) / post-test (condition at bottom) — in JS `for` (fixed count), `while` (while true).
- **JS data & storage [MAIN]:** variables (`let`, constants, arrays); types String/Integer/Float. Web Storage: `localStorage` (small text/numbers), `IndexedDB` (large structured, offline), `Cache API` (resources, offline), `sessionStorage` (until tab closed).
- **Output types [MAIN]:** Text (`console.log`, `alert`), Visual (`textContent`), Sound (`new Audio().play()`), Haptic (`navigator.vibrate`), Notification, Data (API).

---

## 10. Caesar Cipher & Terminology (Starter 2 — FLAGGED "WRITTEN WRONG")

### Doc's stated definition
"A Caesar cipher … a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions **down the alphabet**. For example, with a **left shift of 3**, D would be replaced by A, E would become B." [Starter2]

### ⚠️ Flagged inconsistency (as warned in Software Links.txt)
The text calls it a "**left shift of 3**" and the example (D→A, E→B) is correct for a *left/backward* shift, but describes substitution as moving "**down the alphabet**" — "down" normally means forward toward Z (D→G), the opposite direction. The word "**down**" should read "**up/back**." Reproduced as written. [Starter2]

### Decryption rule used (left shift of 1)
Python `decrypt_left_shift_1` does `chr((ord(ch) - ord('a') - 1) % 26 + ord('a'))`. Decryption table (left shift 1): Ivc→Hub, Txjudi→Switch, Spvufs→Router, Csjehf→Bridge, Hbufxbz→Gateway, Tubs→Star, Sjoh→Ring, Cvt→Bus, Xjsfmftt→Wireless, Upqpmphz→topology, Qbdlfu txjudijoh→Packet Switching, Ifbe→Head, Cpez→Body, Gppufs→Footer, Ubjm→Tail, IUUQT→HTTPS, GUQ→FTP, TNUQ→SMTP, QPQ→POP, TTM→SSL. (Note: one row "Python→Tail" is misaligned in the source; reproduced as written.) [Starter2]

### Consistency note
W3's Caesar activities also use left-shift-of-1 / shift-of-3 convention: `Uifsf jt b tfdsfu dpef!` → "There is a secure code!" (shift 1); `Khoor Zruog!` → "Hello World!" (shift 3). [W3/Starter2]

### Terminology reinforced
Decrypted words are networking terms: Hub, Switch, Router, Bridge, Gateway, Star, Ring, Bus, Wireless, topology, Packet Switching, Head, Body, Footer, Tail, HTTPS, FTP, SMTP, POP, SSL. [Starter2]

---

> **See also:** [[SE_Software_Automation]] | [[SE_Secure_Software_Architecture]] | [[SE_Software_Dev_Process]] | [[SE_Algorithms_and_Desk_Checks]] | [[SE_Object_Oriented_Programming]]
