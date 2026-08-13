# SentinelRAG — Literature Review

| # | Paper | Year | Attack Type | Method | Dataset/Benchmark | Main Finding | Limitation | SentinelRAG Relevance |
|---|---|---:|---|---|---|---|---|---|
| 1 | PromptShield: Deployable Detection for Prompt Injection Attacks | 2025 | Direct / Prompt injection | Prompt injection detector | PromptShield benchmark | Shows practical prompt-injection detection is possible | Detection performance/generalization remain important concerns | Establishes a baseline for detection |
| 2 | InjecAgent | 2024 | Indirect injection | Benchmark for LLM agents | InjecAgent | Demonstrates vulnerability to malicious instructions from external/tool content | Focuses heavily on agent settings | Important foundation for indirect/RAG attacks |
| 3 | Can Indirect Prompt Injection Attacks Be Detected and Removed? | 2025 | Indirect injection | Detection + removal | Indirect injection benchmark | Shows defenses can detect and sanitize malicious content | Leaves room for robustness/generalization questions | Very close to SentinelRAG |
| 4 | InstructDetector | 2025 | Indirect injection | Hidden states + gradients | BIPIA | Shows internal LLM representations can provide strong detection signals | Potential computational complexity | Alternative to simple text classifiers |
| 5 | BIPIA | 2024 | Indirect injection | Benchmark | BIPIA | Provides a benchmark for evaluating indirect prompt injection | Benchmark limitations and attack coverage | Candidate benchmark for our experiments |
| 6 | Defenses Against Prompt Attacks Learn Surface Heuristics | 2026 | Prompt attacks | Robustness analysis | Multiple evaluations | Shows defenses may learn superficial attack patterns | Highlights unresolved robustness issues | Strong evidence for studying generalization |
| 7 | Adaptive Attacks Against Indirect Prompt-Injection Defenses | 2025 | Adaptive indirect injection | Adaptive attack evaluation | Multiple defenses | Shows attackers can adapt to bypass defenses | Defense robustness remains difficult | Important for SentinelRAG evaluation |
| 8 | PIArena | 2026 | Direct + indirect | Unified evaluation framework | Multiple benchmarks | Shows evaluation methodology strongly affects apparent defense performance | Unified evaluation is still evolving | Useful for designing rigorous experiments |
