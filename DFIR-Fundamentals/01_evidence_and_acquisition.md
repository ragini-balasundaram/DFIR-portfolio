# Evidence Handling & Acquisition

This module establishes the baseline definitions of digital evidence and details the strict methodologies required to interact with, capture, and preserve data without compromising its integrity.

---

## 🏛️ What is Digital Evidence?

At its simplest, **digital evidence** is any information stored or transmitted in binary form that could be used to support an investigation. While different institutional frameworks define it with slight variations, two core criteria must always be met:

1. **The data exists in digital/binary form.**
2. **It has probative value** — meaning it is legally or logically useful for proving or disproving a specific hypothesis.

### The Incident Response Context
In corporate cybersecurity and incident response (IR), the primary goal shifts slightly away from strict courtroom presentation. Instead, the focus is on **organizational risk management** and reconstructing an event to determine exactly what occurred on a system. Therefore, the "binary data utilized to understand an event" takes operational precedence over pure legal technicalities.

---

## 🔄 The Triad: Collection, Acquisition, and Preservation

While often used interchangeably in casual conversation, these three terms represent distinct, sequential phases in a forensic workflow.

* **Collection:** The physical or logical act of taking a device or data stream into your possession (e.g., physically removing a hard drive from a server).
* **Acquisition:** The process of extracting the actual data from that evidence container (e.g., creating a bit-for-bit duplicate image of the storage media).
* **Preservation:** The overarching practice of maintaining evidence in the exact state in which it was uncovered—ensuring zero alterations and preventing contamination.

> 🏢 **Real-World Scenario: The Ransomware Response**
> 
> Imagine arriving at the scene of a live ransomware deployment where an administrative machine has already been powered down by a well-meaning employee. 
> 
> 1. **Collection:** You physically pull the internal hard drive from the chassis, place it inside an anti-static ESD bag, and log it into tracking as `Item-001`.
> 2. **Acquisition & Preservation:** Back at the lab, you connect `Item-001` to a forensic workstation through a **hardware write-blocker** (which physically blocks inbound write commands). You then use a tool to create an exact bit-for-bit duplicate clone file, `Item-001.dd`. The write-blocker ensures *preservation*, while the clone file represents the completed *acquisition*.

---

## 📋 Core Principles of Forensic Acquisition

To ensure forensic data remains untainted and admissible for analysis, three immutable rules must guide every interaction:

* **Zero Alteration:** Do not modify the original evidence or any subsequent working copies.
* **Comprehensive Documentation:** Log every interaction with the evidence. Record exactly **what** action was taken, **when** it occurred, and **why** it was necessary.
* **Chain of Custody:** Maintain a continuous, unbroken paper or digital trail documenting every individual who took possession of the item, along with precise timestamps of custody transfer.

### ⚠️ The Volatile Memory Exception
Volatile memory (RAM) presents a critical exception to the "zero alteration" principle. It is impossible to acquire RAM on a live system without altering it. Running a memory acquisition tool inherently loads code into RAM, overwriting a small footprint of the very data you are trying to capture. 

Because some data alteration is unavoidable here, **meticulous documentation** becomes paramount. The analyst must record the exact tools used, execution timestamps, and the expected architectural impact on the target system's memory space.
