---
title: "Career"
---

[Download as PDF](/resume.pdf)

Thornhill, ON, Canada · <amar.al-zubaidi@proton.me>

[github.com/amarz45](https://github.com/amarz45) · [linkedin.com/in/amar-al](https://www.linkedin.com/in/amar-al)

## Education

### York University

_Computer Science, BSc, Hons_ · Toronto, ON, Canada · September 2024 – June 2028

- **Cumulative GPA:** 3.7/4.0 (7.9/9.0 institutional scale)
- **Courses:** Data Structures and Algorithms, Probability; in progress: Numerical Methods I & II, Network Protocols

## Work Experience

### Sobeys

_Cybersecurity Analyst (Co-op)_ · Mississauga, ON, Canada · May 2026 – August 2026

- Developed REST API scripts for CrowdStrike Falcon to automate vulnerability tracking and asset filtering by OS lifecycle status, eliminating a recurring **5+ hour** manual reporting task
- Built automated network scanning using Nmap that classifies devices by combining port, service/version, and OS information, replacing manual per-host identification and enabling fleet-wide EDR sensor rollout
- Correlated 3 months of endpoint detection and email delivery data using Copilot, surfacing shifts in threat trends and coordinated campaigns earlier than manual review

### DataAnnotation

_AI Trainer (Code Reviewer)_ · _Remote_ · June 2025 – September 2025

- Reviewed and rewrote AI-generated code in Python, C++, TypeScript, Java, and Rust, implementing requirements the model had silently skipped or left partially complete
- Debugged and fixed defects in unfamiliar open-source codebases containing **50+ files**, tracing behaviour through undocumented code paths to locate root causes
- Authored unit tests covering edge cases (off-by-one errors, boundary conditions) and evaluation rubrics defining pass criteria for code-correctness tasks, both used by other reviewers to grade submissions consistently

## Projects

### Comicpress

[github.com/amarz45/comicpress](https://github.com/amarz45/comicpress)  
Cross-platform C++ GUI application, built with Qt, that converts and compresses digital comic book files for e-readers. The libvips-based image processing pipeline uses multiple processes rather than threads, working around PDFium's lack of thread safety and giving workers isolation without locking overhead; throughput scales linearly with job count. Shrinks file sizes by **up to 80%** while improving visual fidelity.

### Termtile

[github.com/amarz45/termtile](https://github.com/amarz45/termtile)  
Web-based university timetable planner. A Python scraper parses the course catalogue into a normalized dataset. A TypeScript solver runs entirely in the browser, enumerating every conflict-free schedule and filtering by constraints such as instructor, earliest start time, and length of each day, with results rendered as a browsable weekly calendar.

## Skills

- **Programming languages:** Python, C, C++, Java, TypeScript/JavaScript, Bash, PowerShell, SQL
- **Software & tools:** Git, Docker, Linux, REST APIs, Copilot, Claude Code
- **Areas:** systems programming, web development, scripting, security, networking (TCP/IP, DNS, HTTP)
- **Spoken languages:** English (native), Arabic (native), French (intermediate)
