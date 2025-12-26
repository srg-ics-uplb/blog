A Reading Guide for Systems Researchers
#######################################

:date: 2025-12-24 12:02 
:category: Research
:author: Joseph Anthony C. Hermocilla
:summary: This is a layered reading guide for researchers(beginner to senior) interested in computer systems. A little bit of structure will prevent the beginner from being overwhelmed with too much information.

This is a layered reading guide for researchers (beginner to senior) interested in computer systems. A little bit of structure will prevent the beginner from being overwhelmed with too much information. Keeping up with the recent advances in a field can be very overwheling because of the large volume of papers to read. 


This reading stack is not a checklist to complete but a framework for continuous learning. Adjust the balance between layers based on your current research phase:

.. list-table::
   :widths: 30 70
   :header-rows: 1

   * - Research Phase
     - Focus Distribution
   * - Senior undergrad/First year MS student?
     - Spend 70% of time on Layers 0–2
   * - Early PhD student?
     - Balance Layers 2–4 evenly
   * - Preparing for publication?
     - Focus on Layer 6 with deep dives into Layer 2
   * - Senior researcher?
     - Maintain Layer 5 continuously while mentoring others through earlier layers


The goal is not to read everything, but to develop intuition for what matters 
and the ability to learn what you need, when you need it.


===============================================================================
Layer 0 — Mental Models (Read Once, Revisit Often)
===============================================================================

*Goal: Develop core systems intuition and reasoning.*

Core Textbooks
-------------------------------------------------------------------------------

* Computer Systems: A Programmer's Perspective (CS:APP)

  Focus: Performance, memory hierarchy, hardware–software interface

* Operating Systems: Three Easy Pieces (OSTEP) — Arpaci-Dusseau
  
  Focus: Abstractions, invariants, resource management, failure reasoning

* Computer Networks: A Systems Approach — Larry Peterson & Bruce Davie

  Focus: Protocol design, end-to-end principle, layering
  
  (Though I recommend to read Fourozan's book first)

* Distributed Systems — Maarten van Steen & Andrew Tanenbaum (3rd edition)
  
  Focus: Coordination, replication protocols, fault models

Additional Foundational Texts
-------------------------------------------------------------------------------

* Transaction Processing: Concepts and Techniques — Gray & Reuter
  
  Focus: ACID properties, concurrency control, recovery (essential for 
  database systems and distributed transactions)

* Designing Data-Intensive Applications — Martin Kleppmann
  
  Focus: Distributed systems models, consistency, replication

* Data Communications and Networking - Behrouz A. Forouzan
 
  Focus: Bottom-up approach with lots of technical details

* The Art of Computer Systems Performance Analysis: Techniques for Experimental Design, Measurement, Simulation, and Modeling - Raj Jain

  Focus: How to measure performance of computer systems

.. note::
   These texts form the implicit knowledge base assumed by most systems papers.

===============================================================================
Layer 1 — Canonical Systems Papers (Shared Vocabulary)
===============================================================================

*Goal: Learn foundational ideas that reappear across decades of systems research.*

Operating Systems
-------------------------------------------------------------------------------

* The UNIX Time-Sharing System (Ritchie & Thompson)
* Multics - The first seven years
* Exokernel: An Operating System Architecture for Application-Level Resource Management
* Scheduler Activations
* The Design and Implementation of a Log-Structured File System
* Hints for Computer System Design (Butler Lampson)

`OS Papers <https://github.com/srg-ics-uplb/systems-track-primer/tree/main/readings/os>`_

Distributed Systems
-------------------------------------------------------------------------------

* Time, Clocks, and the Ordering of Events in a Distributed System (Lamport)
* Paxos Made Simple
* Raft: In Search of an Understandable Consensus Algorithm
* MapReduce: Simplified Data Processing on Large Clusters
* Dynamo: Amazon's Highly Available Key-Value Store
* Chain Replication for Supporting High Throughput and Availability
* The Byzantine Generals Problem
* Harvest, Yield, and Scalable Tolerant Systems

`DistSys Papers <https://github.com/srg-ics-uplb/systems-track-primer/tree/main/readings/distsys>`_

Performance and Architecture
-------------------------------------------------------------------------------

* Amdahl's Law
* Memory Consistency Models
* Formal Requirements for Virtualizable Third Generation Architectures
* C10K Problem and Modern Variants (C10M)


`Perf/Arch Papers <https://github.com/srg-ics-uplb/systems-track-primer/tree/main/readings/perf_arch>`_

Networked Systems
-------------------------------------------------------------------------------

* End-to-End Arguments in System Design (Saltzer, Reed, Clark)
* The Design Philosophy of the DARPA Internet Protocols

`Networks Papers <https://github.com/srg-ics-uplb/systems-track-primer/tree/main/readings/networks>`_

===============================================================================
Layer 2 — Conference "Greatest Hits" (Last 10–15 Years)
===============================================================================

*Goal: Understand how classical ideas evolved under modern constraints.*

Reading Strategy
-------------------------------------------------------------------------------

Start with Best Paper and Distinguished Paper awards. Prioritize papers that:

* Introduce new abstractions
* Remove long-standing assumptions
* Provide reusable systems designs
* Include open-source artifacts (reproducibility matters)


Core Venues (Tier 1)
-------------------------------------------------------------------------------

* SOSP — Symposium on Operating Systems Principles
* OSDI — Operating Systems Design and Implementation
* ASPLOS — Architectural Support for Programming Languages and Operating Systems
* EuroSys — European Conference on Computer Systems
* NSDI — Networked Systems Design and Implementation
* USENIX ATC — Annual Technical Conference

Additional Important Venues
-------------------------------------------------------------------------------

* SIGCOMM — Data communication and networks
* SIGMOD/VLDB — Database systems (increasingly systems-relevant)
* HotOS/HotNets — Early-stage ideas and position papers
* FAST — File and Storage Technologies

Common Contemporary Topics
-------------------------------------------------------------------------------

* Kernel bypass and user-space networking (DPDK, io_uring)
* eBPF-based observability and sandboxing
* Modern microkernel architectures
* Storage disaggregation and CXL
* Serverless and cloud runtimes
* Hardware-software co-design for ML systems
* SmartNICs and programmable networking
* Persistent memory systems
* Confidential computing and TEEs

===============================================================================
Layer 3 — Systems and Security Intersection
===============================================================================

*Goal: Understand how security constraints influence systems design.*

Key Venues
-------------------------------------------------------------------------------

* USENIX Security Symposium
* IEEE Symposium on Security and Privacy (Oakland)
* ACM CCS — Computer and Communications Security
* NDSS — Network and Distributed System Security

Core Themes
-------------------------------------------------------------------------------

* Memory safety (e.g., CHERI, Rust-based kernels)
* Trusted Execution Environments (SGX, SEV, TrustZone)
* Microarchitectural side channels (Spectre, Meltdown lineage)
* OS isolation mechanisms (VMs, containers, WebAssembly)
* Secure boot, firmware, and hardware roots of trust
* Supply chain security for systems software
* Verified systems (formal methods in practice)

Essential Security Papers for Systems Researchers
-------------------------------------------------------------------------------

* seL4: Formal Verification of an OS Kernel
* Native Client: A Sandbox for Portable, Untrusted x86 Native Code
* Spectre Attacks: Exploiting Speculative Execution

.. important::
   Security-aware design is increasingly a baseline requirement for systems research.

===============================================================================
Layer 4 — Artifacts and Code (Mandatory)
===============================================================================

*Goal: Understand what is feasible in practice.*

Systems to Study
-------------------------------------------------------------------------------

* Linux kernel (selected subsystems: scheduler, memory management, VFS)
* xv6 teaching operating system — read the entire codebase
* seL4 microkernel (papers and code)
* Kubernetes architecture and design documents
* eBPF documentation and tooling
* Redis and RocksDB internals
* DPDK and SPDK for high-performance I/O
* Firecracker — microVM implementation
* etcd or Consul — production consensus systems

Code Reading Practice
-------------------------------------------------------------------------------

* Trace a syscall from userspace to hardware
* Follow a network packet through the stack
* Understand one scheduler policy completely
* Read commit messages and design docs, not just code — they explain why

.. note::
   A systems idea is incomplete without understanding its implementation constraints.

===============================================================================
Layer 5 — Live Research Feed (Continuous Update)
===============================================================================

*Goal: Track emerging ideas without information overload.*

Weekly
-------------------------------------------------------------------------------

arXiv categories:

* cs.OS (Operating Systems)
* cs.DC (Distributed Computing)
* cs.NI (Networking)
* cs.CR (Cryptography and Security, selective)
* cs.AR (Hardware Architecture, selective)

Conference Twitter/Mastodon feeds during major events

Systems research blogs:

* The Morning Paper (archive)
* Adrian Colyer's blog
* Murat Demirbas's blog

Monthly
-------------------------------------------------------------------------------

* Scan newly released conference proceedings
* Review Best Paper announcements
* Browse recent conference talk titles and recorded presentations
* Check workshop proceedings (often contain exploratory work)

Bi-Annual
-------------------------------------------------------------------------------

* Read "Systems We Love" retrospectives
* Survey papers in ACM Computing Surveys or IEEE Computer

Representative Research Groups
-------------------------------------------------------------------------------

* MIT PDOS
* Stanford Systems Group
* Berkeley RISELab / Sky Computing Lab
* University of Washington Systems Group
* Microsoft Research (Systems, Security, Networking)
* VMware Research
* Google Research (Systems Infrastructure)
* ETH Zurich Systems Group
* MPI-SWS
* EPFL LABOS

===============================================================================
Layer 6 — Personal Research Track (Deep Dive)
===============================================================================

*Goal: Transition from consumer to producer of research.*

Choose One Focus Area
-------------------------------------------------------------------------------

* File systems and storage
* Scheduling and runtimes
* Distributed storage systems
* Systems for machine learning
* Operating system security
* Cloud operating systems and serverless platforms
* Network function virtualization
* Memory systems and persistent memory

For the Chosen Area
-------------------------------------------------------------------------------

* Read all relevant papers from the last 5–7 years
* Build a taxonomy of approaches
* Identify recurring assumptions and limitations
* Track benchmark reuse and evaluation gaps
* Maintain a literature review document with annotations
* Identify "citation classics" — heavily cited recent work
* Run experiments with existing systems to understand trade-offs
* Engage with the research community (workshops, reading groups)

.. note::
   This layer is where publishable research directions emerge.

===============================================================================
Layer 7 — Cross-Cutting Concerns
===============================================================================

*Goal: Develop skills beyond paper reading.*

Writing and Communication
-------------------------------------------------------------------------------

* Read well-written papers for structure (e.g., papers by Eddie Kohler, 
  Michael Walfish, Nickolai Zeldovich)
* Study how figures and tables convey key insights
* Practice writing technical summaries (one paragraph per paper)

Experimental Methodology
-------------------------------------------------------------------------------

* The Art of Computer Systems Performance Analysis — Raj Jain
* Understand statistical significance and experimental design
* Learn common pitfalls in systems benchmarking
* Replication studies reveal what papers omit

Peer Review Skills
-------------------------------------------------------------------------------

* Volunteer for shadow PC programs (SOSP, OSDI often run these)
* Read reviewer guidelines from major conferences
* Practice writing reviews for papers you read

Broader Context
-------------------------------------------------------------------------------

* Technology trends: Moore's Law end, memory wall, power wall, datacenter scale
* Industry systems: Read engineering blogs from hyperscalers 
  (Google, Meta, Amazon, Microsoft)
* Standards and specifications: POSIX, ACPI, PCIe, RDMA

===============================================================================
How to Read a Systems Paper
===============================================================================

For each paper, be able to answer:

1. What assumption does this work challenge?
2. What is the true technical contribution? (Often hidden in Section 3-4, 
   not the abstract)
3. What is missing from the evaluation? (Workloads, baselines, failure scenarios)
4. What fails if the environment or scale changes?
5. Would this design survive an order-of-magnitude increase in scale?
6. What would you do differently? (Always have an opinion)
7. How does this relate to three other papers you've read? (Build connections)

Critical Reading Checklist
-------------------------------------------------------------------------------

* Are the threat model / failure model / consistency model explicit?
* Are performance claims backed by microbenchmarks?
* Is there a comparison to prior work under the same conditions?
* Are negative results or limitations discussed honestly?
* Is the artifact available and does it match the paper's claims?

===============================================================================
Minimal Weekly Study Plan (6–8 Hours)
===============================================================================

Session 1 (2.5 hours): Deep read one paper with notes
-------------------------------------------------------------------------------

* Read twice: once for understanding, once for critique
* Sketch alternative designs

Session 2 (1.5 hours): Skim 5–8 papers and maintain reading log
-------------------------------------------------------------------------------

Track: problem, approach, key insight, limitations

Session 3 (2 hours): Study code, artifacts, or attempt replication
-------------------------------------------------------------------------------

* Run experiments, modify parameters, break things intentionally

Long-Term Habits
-------------------------------------------------------------------------------

* Maintain a "research ideas" document — jot down half-baked ideas immediately
* Participate in reading groups — explaining papers solidifies understanding
* Write blog posts or notes — teaching forces clarity

===============================================================================
Indicators of Systems Fluency
===============================================================================

You can:

* Anticipate reviewer criticisms before reading the evaluation
* Propose alternative designs with concrete trade-offs
* Explain trade-offs concisely (performance vs. complexity vs. generality)
* Connect new work to historical systems ideas
* Estimate orders of magnitude (latency, throughput, memory overhead)
* Identify when a problem is harder than the paper admits
* Recognize when a paper is solving the wrong problem
* Engage in technical arguments without ego

Red Flags You've Developed Good Taste
-------------------------------------------------------------------------------

* You get annoyed by papers that don't release code
* You instinctively ask "what if it fails here?"
* You notice when evaluation sections bury important details
* You can predict which papers will be influential in 5 years

===============================================================================
Meta-Advice for Sustainable Research Practice
===============================================================================

1. Quality over quantity: Five deeply understood papers > 50 skimmed papers
2. Take breaks: Systems research is cumulative; understanding compounds over time
3. Build, don't just read: Implementation forces confrontation with reality
4. Find your people: Research is a social activity; isolation kills momentum
5. Embrace confusion: The best research questions emerge from things that 
   "don't quite make sense"
6. Version control your notes: Git-tracked markdown files are surprisingly effective
7. Revisit old papers: Your understanding evolves; re-reading reveals new layers

===============================================================================
Resources Beyond Papers
===============================================================================

* Conference recordings: YouTube channels for USENIX, ACM, etc.
* Open-source OS courses: MIT 6.S081, Berkeley CS 162
* Systems podcasts: "Software Engineering Daily" (systems episodes)
* Mailing lists: USENIX OSDI announcements, LWN.net kernel coverage
* Discord/Slack communities: Many systems projects have active communities

===============
Acknowledgement
===============
This article was made with the help of ChatGPT and Claude (accessed 2025-12-24)
