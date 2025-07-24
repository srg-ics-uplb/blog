Research Proposal Part 1: Finding and Identifying Research Gaps
###############################################################

:date: 2025-07-21
:modified: 2025-07-24
:category: Research Proposal
:author: Joseph Anthony C. Hermocilla
:summary: The first part of a series of posts to help students come up with a research proposal for their CMSC 190/200/300 or for publication in conferences and journals. I used AI tools to create these posts, Grok in particular. Although this is tailored for systems research, the ideas apply to other fields also. 

.. image:: ./images/jach/008_gaps.png
      :width: 50%
      :align: center

The first part of a series of posts to help students come up with a research proposal for their CMSC 190/200/300 or for publication in conferences and journals. I used AI tools to create these posts, Grok in particular. Although this is tailored for systems research, the ideas apply to other fields also. 

A research endeavor usually starts by identifying research gaps. A research gap is 'something' (question, concept, approach) 
within a research area that has not been answered or addressed yet and thus have limited discussion in the 
literature. In this post, some approaches (with techniques and examples) to find and identify research gaps in computer systems research are presented.  


1. Conduct a Comprehensive Literature Review
============================================

**Purpose**: Understand the state-of-the-art and identify areas that are underexplored or unresolved.

**Techniques**:

- **Systematic Search**: Use academic databases like IEEE Xplore, ACM Digital Library, Springer, arXiv, and Google Scholar to search for recent papers, surveys, and reviews in your subfield (e.g., cloud computing, storage systems, or machine learning systems).

  - Use specific keywords (e.g., “energy-efficient computing,” “scalable distributed systems”) and combine them with Boolean operators (AND, OR, NOT) to refine results.
  - Filter for recent publications (last 3–5 years) to focus on current trends.

- **Read Survey Papers and Reviews**: Surveys often summarize open challenges and future directions explicitly. For example, look for “Open Problems” or “Future Work” sections in journals like *ACM Computing Surveys* or *IEEE Transactions*.

- **Analyze Highly Cited Papers**: Identify foundational papers and check their “Future Work” sections or limitations to uncover unresolved issues.

- **Track Emerging Topics**: Monitor proceedings of top conferences (e.g., OSDI, SOSP, ASPLOS, ISCA, USENIX ATC) to spot new trends or areas with limited follow-up work.


**Example**: While reviewing IEEE Xplore for papers on distributed storage systems, you find a 2024 survey in ACM Computing Surveys on “Next-Generation Storage Systems.” The survey highlights that current systems like Ceph and HDFS are optimized for large-scale cloud environments but lack efficient support for geo-distributed edge storage with intermittent connectivity. The “Future Work” section suggests exploring decentralized storage protocols for edge environments, but no follow-up papers address this. *Gap*: Designing a distributed storage system tailored for edge devices with unreliable network conditions.


**Tip for Computer Systems**: Pay attention to performance bottlenecks, scalability limitations, or security vulnerabilities mentioned in system evaluations, as these often point to gaps.


2. Identify Limitations in Existing Work
========================================

**Purpose**: Pinpoint weaknesses or constraints in current systems or methodologies that your research can address.

**Techniques**:

- **Scrutinize Evaluation Sections**: Look at how systems are evaluated (e.g., benchmarks, workloads, or metrics). Are there scenarios where the system underperforms?

- **Examine Assumptions**: Many systems papers make simplifying assumptions (e.g., homogeneous hardware, idealized network conditions). Gaps often exist where these assumptions don’t hold.

- **Check Scalability and Applicability**: Investigate if current solutions scale to emerging technologies or fail under new constraints.

- **Look for Trade-offs**: Gaps may lie in optimizing trade-offs or mitigating their downsides.

**Example**: A 2023 OSDI paper on a new memory management system for cloud servers assumes homogeneous memory latency across NUMA nodes. Its evaluation shows performance degradation when applied to disaggregated memory systems (e.g., where memory is accessed over a network). *Gap*: Developing memory management techniques that optimize for disaggregated memory architectures with variable latency.

**Tip for Computer Systems**: Focus on practical deployment gaps—e.g., systems that work well in labs but not in real-world environments.


3. Engage with the Research Community
=====================================

**Purpose**: Leverage discussions and feedback from experts to uncover less-visible gaps.

**Techniques**:

- Attend conferences and workshops (e.g., NSDI, EuroSys, HotOS).
- Join mailing lists and forums (e.g., ACM SIGOPS or SIGARCH).
- Collaborate and network with peers or practitioners.
- Follow posts from researchers or organizations on platforms like X.

**Example**: At SOSP 2025, during a panel on “Systems for AI Workloads,” a researcher mentions that current GPU scheduling frameworks (e.g., NVIDIA’s MPS) struggle with dynamic multi-tenant AI workloads due to poor isolation and resource contention. No solutions are proposed in the discussion. *Gap*: Creating a GPU scheduling framework that ensures strong isolation and fairness for multi-tenant AI inference in data centers.


**Tip for Computer Systems**: Collaborate with industry to find real-world deployment gaps.


4. Explore Interdisciplinary and Emerging Areas
===============================================

**Purpose**: Identify gaps at the intersection of systems and other domains or new trends.

**Techniques**:

- Analyze cross-disciplinary interactions (e.g., with ML, IoT, or crypto).
- Monitor emerging technologies (e.g., TPUs, serverless, disaggregated memory).
- Examine application domains (e.g., AR/VR, autonomous vehicles).

**Example**: While exploring the intersection of Computer Systems and quantum computing, you notice that existing operating systems lack support for scheduling hybrid classical-quantum workloads. Papers on quantum computing focus on algorithms but not on system-level integration with classical hardware. *Gap*: Designing an operating system scheduler that optimizes resource allocation for hybrid quantum-classical computing environments.

**Tip for Computer Systems**: Gaps often arise when adapting systems to new use cases or hardware.


5. Analyze Real-World Systems and Industry Needs
================================================

**Purpose**: Ground your research in real-world issues.

**Techniques**:

- Study open-source systems and issues (e.g., Linux, Kubernetes).
- Read technical industry reports (e.g., Spanner, DynamoDB).
- Monitor news or posts about outages, bugs, or breaches.

**Example**: Analyzing the Kubernetes GitHub issue tracker, you find multiple unresolved issues about inefficient pod scheduling on heterogeneous clusters with mixed CPU/GPU/TPU nodes. Users report suboptimal performance for machine learning workloads. *Gap*: Developing a Kubernetes scheduler extension that optimizes for heterogeneous hardware in ML-heavy clusters.

**Tip for Computer Systems**: Look for practical challenges like energy, cost, and maintainability.


6. Leverage Quantitative and Qualitative Analysis
=================================================

**Purpose**: Use structured methods to find gaps.

**Techniques**:

- Use SWOT or other gap analysis frameworks.
- Build taxonomies of existing work.
- Benchmark current systems.
- Survey experts.

**Example**: You create a taxonomy of existing fault-tolerance mechanisms in distributed systems (e.g., checkpointing, replication, erasure coding). You notice that most mechanisms are designed for crash failures but not for Byzantine failures in large-scale systems. A benchmark you run on Apache Spark reveals high overhead when handling Byzantine faults. *Gap*: Designing lightweight Byzantine fault-tolerant protocols for large-scale distributed data processing systems.

**Tip for Computer Systems**: Quantitative analysis of metrics (e.g., latency, energy) can highlight performance gaps.


7. Focus on “Future Work” and Open Questions
============================================

**Purpose**: Mine existing research for explicitly stated gaps.

**Techniques**:

- Collect “Future Work” sections across papers.
- Look for speculative or abandoned ideas.
- Find threads in older papers that remain unresolved.

**Example**: A 2024 ASPLOS paper on serverless computing platforms notes that current platforms (e.g., AWS Lambda) struggle with cold-start latency for latency-sensitive applications like real-time video processing. The “Future Work” section suggests exploring predictive pre-warming but lacks implementation details. *Gap*: Developing a predictive pre-warming mechanism to reduce cold-start latency in serverless platforms for real-time applications.

**Tip for Computer Systems**: Common themes include scalability and portability issues.


8. Experiment and Prototype
===========================

**Purpose**: Use experimentation to uncover practical gaps.

**Techniques**:

- Build proof-of-concepts.
- Stress-test existing systems.
- Simulate future scenarios.
- Reproduce prior work.

**Example**: You prototype a distributed file system based on a recent NSDI paper and test it under high-latency network conditions (e.g., simulating 5G edge networks). The system exhibits significant performance degradation due to its reliance on synchronous replication. *Gap*: Designing an asynchronous replication protocol that maintains consistency in high-latency edge environments.

**Tip for Computer Systems**: Prototyping reveals practical limitations (e.g., complexity, compatibility).


9. Stay Updated with Real-Time Information
==========================================

**Purpose**: Ensure your gap analysis is current.

**Techniques**:

- Search X for discussions or trending research hashtags.
- Monitor arXiv or preprint platforms.
- Watch funding agency calls (e.g., NSF, DARPA).

**Example**: On X, a systems researcher (@SysProf2025) posts about a recent arXiv preprint on secure enclaves (e.g., Intel SGX, AMD SEV). The discussion highlights that enclaves are vulnerable to side-channel attacks in multi-tenant cloud environments, with no robust mitigation for dynamic workloads. *Gap*: Developing a secure enclave framework that mitigates side-channel attacks in multi-tenant cloud settings.

**Tip for Computer Systems**: Real-time debates can signal overhyped or unworkable approaches.


10. Reflect on Your Own Expertise and Interests
===============================================

**Purpose**: Match research gaps to your skills and interests.

**Techniques**:

- Map your expertise and look for domain-specific gaps.
- Brainstorm new applications for familiar techniques.
- Revisit your own past work for extensions or limitations.

**Example**: As an expert in computer architecture, you revisit your prior work on cache coherence protocols for multi-core CPUs. You realize that existing protocols are not optimized for emerging chiplet-based architectures, where cores are physically disaggregated. *Gap*: Designing a cache coherence protocol tailored for chiplet-based processors to improve performance and energy efficiency.

**Tip for Computer Systems**: Your unique viewpoint can spot overlooked gaps.


Practical Steps to Validate a Research Gap
==========================================

Once you identify a potential gap:

1. **Novelty Check**: Ensure no recent work has addressed it.
2. **Impact Assessment**: Evaluate real-world or academic importance.
3. **Feasibility Analysis**: Check tools, data, and time constraints.
4. **Community Feedback**: Get input from your adviser, peers, and mentors.

Final Tips
==========

- **Document Your Process**: Maintain a gap-tracking notebook or database.
- **Iterate Continuously**: Revisit gaps as literature and tech evolve.
- **Balance Novelty and Feasibility**: Choose problems that are new *and* solvable.


`Part 2 <{filename}/articles/jach/jach_009.rst>`_ will focus on the Problem Statement.

Acknowledgement
===============
This article was made with the help of Grok (accessed 2025-07-21)
