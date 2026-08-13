# SentinelRAG — Day 1 Literature Review

## Project

**Project Name:** SentinelRAG

**Research Area:** Prompt-Injection Detection and Defense for Retrieval-Augmented Generation (RAG)

**Current Phase:** Literature Review / Research Discovery

**Day 1 Status:** Complete

---

## 1. Project Motivation

Large Language Model (LLM) applications can be vulnerable to prompt-injection attacks, where malicious instructions manipulate the model into ignoring its intended task or following attacker-controlled instructions.

Retrieval-Augmented Generation (RAG) introduces an additional attack surface because external content retrieved by the system may contain malicious instructions.

The goal of SentinelRAG is to investigate robust and practical methods for detecting and defending against prompt-injection attacks in RAG systems.

---

## 2. Literature Studied

### Paper 1 — PromptShield

**Main contribution:** Prompt-injection detection and benchmarking.

**Key lesson:** Prompt-injection detection is already an established research area. Practical deployment requires attention to false positives, detection quality, data quality, and computational cost.

**Implication for SentinelRAG:** A simple "train a classifier and report accuracy" approach would not be sufficiently novel.

---

### Paper 2 — InjecAgent

**Main contribution:** Benchmarking indirect prompt-injection attacks against LLM agents.

**Key lesson:** Malicious instructions do not have to come directly from the user. They can originate from external content or tool outputs.

**Implication for SentinelRAG:** RAG-specific and indirect prompt injection should be treated as a major attack surface.

---

### Paper 3 — Detection and Removal of Indirect Prompt Injection Attacks

**Main contribution:** Studying both detection and removal/sanitization of indirect prompt injections.

**Key lesson:** Detection alone may not be sufficient. A defense can also attempt to isolate or remove malicious instructions before the content reaches the LLM.

**Implication for SentinelRAG:** Potentially investigate detection together with safe content handling/sanitization.

---

### Paper 4 — InstructDetector

**Main contribution:** Detecting injected instructions using information from the LLM's internal representations.

**Key lesson:** Prompt-injection detection does not have to rely solely on surface-level text classification.

**Implication for SentinelRAG:** Internal model signals may provide strong detection capabilities, but they may also introduce computational and implementation complexity.

---

### Paper 5 — BIPIA

**Main contribution:** Benchmarking indirect prompt-injection attacks.

**Key lesson:** Standardized benchmarks are important for measuring the vulnerability of LLM systems to indirect attacks.

**Implication for SentinelRAG:** Existing benchmarks can provide a foundation for future experiments.

---

### Paper 6 — Defenses Against Prompt Attacks Learn Surface Heuristics

**Main contribution:** Investigating whether defenses learn genuine malicious intent or superficial attack-related patterns.

**Key lesson:** A detector can achieve strong benchmark performance while relying on surface heuristics, leading to poor robustness under distribution shifts and false positives.

**Implication for SentinelRAG:** Generalization and false-positive behavior are important research dimensions.

---

### Paper 7 — Adaptive Attacks Against Indirect Prompt-Injection Defenses

**Main contribution:** Evaluating defenses against attackers who deliberately modify attacks to bypass the defense.

**Key lesson:** Defenses that perform well against fixed/static attacks may be vulnerable to adaptive attackers.

**Implication for SentinelRAG:** Adaptive attack evaluation should be considered when designing a serious defense.

---

### Paper 8 — PIArena

**Main contribution:** A unified evaluation framework for prompt-injection attacks and defenses, including adaptive evaluation.

**Key lesson:** Results from different papers are difficult to compare when evaluation settings differ. Adaptive and unseen attacks can reveal weaknesses hidden by static benchmarks.

**Implication for SentinelRAG:** Robust evaluation methodology is as important as the detector itself.

---

## 3. Major Themes Identified

### A. Direct vs Indirect Injection

Direct injection originates from user input.

Indirect injection originates from external or retrieved content.

SentinelRAG is particularly interested in indirect/RAG-based attacks.

### B. Detection vs Defense

Detection asks:

> Is this content malicious?

Defense can additionally ask:

> What should the system do after detecting malicious content?

Possible actions include blocking, sanitization, isolation, or controlled processing.

### C. Known vs Unseen Attacks

A model may perform well on attack patterns represented in its training data but fail on previously unseen attack families.

### D. Static vs Adaptive Attacks

A static benchmark uses predefined attacks.

An adaptive attacker deliberately changes attacks based on the behavior of the defense.

### E. False Positives

A good defense must avoid incorrectly blocking legitimate user requests and legitimate documents.

### F. Practicality

Strong security is not sufficient if the defense introduces excessive latency, computational cost, or requires unrealistic access to model internals.

---

## 4. Potential Research Directions

These are hypotheses, not finalized research questions.

1. Robust detection of unseen indirect prompt injections.
2. Detection under distribution and topic shifts.
3. Resistance to adaptive attackers.
4. Detection plus sanitization of malicious retrieved content.
5. Reducing false positives while maintaining strong security.
6. Improving security while keeping latency and computational cost practical.

---

## 5. Current Research Hypothesis

A promising direction identified during Day 1 is:

> Existing prompt-injection defenses may perform strongly on static benchmarks while degrading on unseen, distribution-shifted, or adaptive indirect attacks.

This hypothesis requires further literature review and experimental validation.

---

## 6. What We Have NOT Decided

We have not yet finalized:

* The exact research gap
* The final research question
* The dataset
* The ML/AI models
* The proposed method
* The experimental protocol
* The final paper title

These decisions will be made after additional research and gap analysis.

---

## 7. Next Phase

**Day 2 — Research Gap Analysis**

The next phase will compare the identified methods systematically and determine whether there is a specific, realistic research gap that SentinelRAG can investigate.

Only after the research question is sufficiently defined should implementation begin.

