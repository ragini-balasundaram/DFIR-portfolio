# The Forensic Process & Objectivity

This module covers the operational mechanics of executing an investigation, the critical importance of reporting with absolute scientific objectivity, and how forensic methodologies map to real-world adversary behavior.

---

## 🔍 Investigation vs. Examination

While often used interchangeably in casual tech talk, digital forensics maintains a strict operational boundary between these two concepts:

* **Investigation:** The macroscopic "big picture" effort. It encompasses the entire strategy to discover who, what, when, where, and why an incident occurred across an organization.
* **Examination:** A microscopic, specific technical task within that broader investigation. It focuses on analyzing a single isolated piece of evidence to extract factual data.

> 🛠️ **In Practice:** *"I am currently **examining** this isolated laptop hard drive as part of a larger corporate **investigation** into how the adversary initially compromised our internal network."*

---

## ⚖️ Findings and Objectivity: The Golden Rule

The most critical realization of this module is that digital forensics is deeply rooted in science, not speculation. As an analyst, you are not a detective writing a dramatic narrative; you are a scientist reporting precisely what the data reflects. 

When you uncover an interesting artifact, you record it as a **finding**. However, the way you articulate that finding matters immensely. Your language must be strictly objective, never subjective.

### The Artifact Trait Matrix
Consider an analysis where you uncover a malicious binary named `abc.exe` with a file creation timestamp of `May 17, 2024 08:09:20 AM`. Here is how varying statements measure up to forensic standards:

| Option | Statement | Forensic Assessment | Operational Reason |
| :---: | :--- | :--- | :--- |
| **A** | *"The attacker created abc.exe at 08:09 on May 17."* | ❌ **Incorrect / Unprofessional** | You cannot definitively prove *who* sat at the keyboard. Furthermore, it assumes the timestamp is completely untampered with. |
| **B** | *"The file abc.exe was created at 08:09 on May 17."* | ⚠️ **Marginal / Speculative** | Better, but it still implicitly trusts that the operating system's timestamp artifact is accurate without verification. |
| **C** | *"The File Created timestamp for abc.exe was found to be May 17, 2024 at 08:09:20 AM."* | ✅ **Correct / Forensic Grade** | **Perfect.** You are stating exactly what the data shows, not your personal interpretation of it. |

### The Core Lesson
Timestamps can be spoofed by attackers. File extensions can be falsified. As a forensic analyst, your primary responsibility is to describe the artifact exactly as it exists. Interpretation and hypothesis testing come later—and always with clear, data-backed caveats.

---

## 🔄 The Digital Forensics Lifecycle

The Interpol definition of digital forensics maps into a structured, five-step lifecycle. Crucially, this process is **cyclical, not linear**. Findings uncovered during analysis will frequently force you to loop back to identify and acquire entirely new data sources.

```text
 🕵️ Identify ➔ 📥 Acquire ➔ ⚙️ Process ➔ 🔬 Analyze ➔ 📊 Report
  ▲                                            │
  └────────────────── Cyclical Pivot ──────────┘
