# void0x14

**Systems Architect | Low-Level Research | High-Performance Computing**

Dismantling system constraints through bare-metal optimization and deep-layer reverse engineering. Absolute control is the only metric.

`Status: Architecture implies intent. Nomenclature subject to mutation.`

---

### [ Active Research & Development ]

<details>
<summary><b>1. Project: Void-Ecosystem (The 0x14 OS)</b></summary>
<br>
An experimental, minimalist operating system architecture designed to unify disparate hardware into a single computational organism without external dependencies.

* **Public Scope:** A highly optimized Void Linux fork focusing on sub-100MB RAM usage and glibc-to-musl migration strategies.
* **Architecture:**
    * **Distributed Shared Memory (DSM):** Research into RDMA and custom Network Block Device (NBD) protocols to pool memory across 3+ physical devices (42GB Unified Virtual Memory).
    * **Evolutionary Kernel:** A conceptual "Polymorphic Kernel" utilizing local LLMs to read hardware datasheets and generate optimized drivers (C/ASM) via hot-patching.
    * **Self-Refactoring:** Nightly static analysis pipelines allowing the system to refactor its own codebase for latency reduction based on usage patterns.
</details>

<details>
<summary><b>2. Project: Ring-Neg3 (Hardware & Telemetry Bypass)</b></summary>
<br>
Research into the deepest layers of processor execution and hardware interruptions to eliminate silicon-level monitoring.

* **Public Scope:** Kernel-mode driver development and research into x86 interrupt handling mechanics.
* **Technical Depth:**
    * **Telemetry Neutralization:** Implementing custom interrupt handlers to intercept and drop hardware-level telemetry packets (Intel ME / AMD PSP) before they reach the OS.
    * **Neural Interrupt Handling:** A dynamic IRQ balancing daemon using inference to prioritize system interrupts (Network vs. GPU) in real-time.
</details>

<details>
<summary><b>3. Project: <a href="https://github.com/void0x14/google-knockout">Google-Knockout (VM Deobfuscation)</b></summary>
<br>
Advanced analysis of client-side protection mechanisms and dynamic JavaScript virtual machines. **Language Agnostic / Target Defined.**

* **Public Scope:** Research on browser fingerprinting and anti-bot detection systems.
* **Technical Depth:**
    * **Runtime Emulation (Node.js/V8):** Utilizing native V8 contexts to sandbox and execute obfuscated bytecode (`base.js`) without a full browser stack.
    * **Polymorphic Mapping:** Automated AST parsing via Babel to map dynamic opcodes to static instructions, neutralizing "Opcode Rolling" techniques.
    * **Concurrency (Go):** High-throughput API architecture designed to handle massive token generation requests with minimal latency.
</details>

<details>
<summary><b>4. Project: <a href="https://github.com/void0x14/echo-core">Echo-Core (Surgical AI)</b></summary>
<br>
Optimization techniques for running SOTA Large Language Models on constrained consumer hardware.

* **Public Scope:** Local RAG implementation and hardware-aware inference scripts.
* **Technical Depth:**
    * **BitNet Integration:** Research into 1.58-bit quantization to shift the bottleneck from VRAM bandwidth to CPU compute.
    * **AVX-512 Handlers:** Custom compute kernels written to maximize i5-13500H throughput for CPU-bound inference.
    * **Context Paging:** A virtual memory manager for LLM context windows, swapping KV-cache to NVMe to exceed physical RAM limits.
</details>

<details>
<summary><b>5. Project: Neural-Gate (The Filter)</b></summary>
<br>
A browser architecture stripped of commercial telemetry, utilizing kernel-level filtering.

* **Public Scope:** A minimalist fork of Chromium Content Shell.
* **Technical Depth:**
    * **eBPF Filtering:** Moving ad-blocking and script analysis from the browser extension layer directly to the network interface card via eBPF (XDP).
    * **Memory Arbitrage:** A shared memory page architecture to reduce RAM overhead per tab by 60%.
</details>

<details>
<summary><b>6. Project: <a href="https://github.com/void0x14/fettanego.net">Fettanego.net (Adversary Intelligence & Deception)</b></summary>
<br>
An offensive deception environment designed to trap, analyze, and exploit the resources of automated botnets and human threat actors.

* **Public Scope:** Deployment of high-interaction honeypots (HIH) for global threat intelligence gathering and malware archiving.
* **Technical Depth:**
    * **Payload Harvesting & Sandbox Orchestration:** Automated exfiltration of dropped binaries (ELF/PE) from SSH/Telnet and HTTP traps, followed by isolated execution for behavioral analysis.
    * **C2 Infrastructure Mapping:** Heuristic-based analysis of outbound telemetry to identify and map Command & Control (C2) nodes, enabling proactive counter-intelligence.
    * **Credential Siphoning:** Real-time capture of private "combo" lists and wordlists used by attackers during brute-force attempts to build proprietary security databases.
    * **Active Deception (Canary Logic):** Implementation of "Canary Tokens" and fake database assets to induce self-de-anonymization of attackers upon data exfiltration.
</details>

<details>
<summary><b>7. Project: <a href="https://github.com/void0x14/project-Oculus-OSS">Project-Oculus-OSS (Ophthalmic Hardware Liberation)</b></summary>
<br>
A strategic reverse-engineering initiative focused on liberating corneal diagnostic data from closed-loop, proprietary medical hardware through advanced computer vision.

* **Public Scope:** Research on sub-pixel biometric tracking and open-source diagnostic alternatives for corneal topography.
* **Technical Depth:**
    * **Sub-Pixel Biometric Extraction:** Real-time pupil and limbus detection using custom Hough transforms and edge-cascading algorithms for high-precision centration.
    * **Optical Wavefront Reconstruction:** Implementation of Zernike polynomials to model high-order aberrations and refractive power distribution from raw corneal reflections.
    * **Hardware Protocol Decoupling:** Reverse-engineering proprietary USB/Serial data streams and DICOM-hacker modules to bypass vendor-locked medical ecosystems.
    * **Neural Diagnostic Intelligence:** Geometric deep learning architectures designed for early-stage Keratoconus detection and irregular surface mapping.
    * **Void-Protocol Integrity:** Military-grade biometric security utilizing AES-256-GCM and Shamir’s Secret Sharing (SSS) for sensitive diagnostic log protection.
</details>

<details>
<summary><b>8. Project: <a href="https://github.com/void0x14/PROJECT_REFINERY">PROJECT_REFINERY (Video Deduplication Engine)</b></summary>
<br>
An archival-grade video deduplication engine built to separate true duplicates from near-matches without reckless file loss.

* **Public Scope:** Research and development of a safety-first duplicate detection system for video archives, covering exact matching, visual similarity analysis, and automated organization.
* **Technical Depth:**
    * **Hash Pipeline:** SHA-256 indexing for exact duplicate elimination across large datasets.
    * **Visual Similarity Core:** Strict multi-point pHash comparison with average-distance and max-distance rejection rules.
    * **False Positive Hardening:** Match logic explicitly biased toward rejecting uncertain candidates rather than over-merging distinct footage.
    * **Operational Safety:** Reversible visual duplicate handling through trash-bin routing, broken-file quarantine, and resumable SQLite state tracking.
</details>
---

### [ Technical Arsenal ]

**Core & Systems**
* **Languages:** Zig,C, Rust (Memory Safety), x86_64 Assembly, Go (Concurrency).
* **Kernel:** Linux From Scratch (LFS), eBPF (XDP), Custom IRQ Handlers, Ring-0/Ring-3 Interfacing.
* **Optimization:** AVX-512 Intrinsics, SIMD, Manual Memory Paging (mmap), Zero-Copy Networking,RDMA.

**Reverse Engineering & Security**
* **Analysis:** AST Parsing (Babel), Symbolic Execution (Z3), Deobfuscation, Dynamic Binary Instrumentation (Frida).
* **Network Warfare:** Traffic Analysis (Mitmproxy), Protocol Reversing (L7-to-L3 Ambiguity), TLS Fingerprinting.
* **OpSec:** Tux, Qubes OS Isolation.

**Artificial Intelligence & Cognitive Architecture**
* **Inference:** BitNet (1.58-bit), MoE Routing, KV-Cache Paging, Local RAG.
* **Multimodal:** Wav2Vec2 (Audio Intelligence), DeepFace (Vision), LlamaIndex.

> "Talk is cheap. Show me the code." — **Linus Torvalds**
