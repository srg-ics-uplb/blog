Research Proposal Part 2: Writing the Problem Statement
#######################################################

:date: 2025-07-22
:category: Research, Proposal
:author: Joseph Anthony C. Hermocilla


Once a research gap has been identified, a Problem Statement can be created. Below is a short discussion on how to write the Problem Statement for a research proposal based on the example from `Approach        5: Analyzing real-world systems and industry needs <{filename}/articles/jach/jach_008.rst>`_. The example identified a research gap in *developing a Kubernetes scheduler extension that optimizes for heterogeneous hardware in ML-hea       vy clusters*, inspired by unresolved issues in the Kubernetes GitHub tracker about inefficient pod scheduling on mixed CPU/GPU/TPU nodes.

1. Define the Problem Clearly
-----------------------------

- **What is the issue?** Specify the core limitation or deficiency in existing systems (e.g., inefficient scheduling for heterogeneous ML clusters).
- **Context**: Provide enough background to make the problem understandable to both experts and non-experts in Computer Systems.
- **Scope**: Narrow the focus to the specific domain (Kubernetes, heterogeneous clusters, ML workloads) to avoid being overly broad.

2. Highlight the Impact
-----------------------

- **Why is it significant?** Explain the consequences of the gap (e.g., poor performance, wasted resources, limited scalability).
- **Who is affected?** Identify stakeholders (e.g., cloud providers, ML practitioners, DevOps engineers).
- **Real-world relevance**: Connect to practical scenarios, such as deploying ML models in production environments.

3. Justify the Need for a Solution
----------------------------------

- **Why hasn't it been solved?** Reference limitations in existing work (e.g., lack of hardware-aware scheduling, poor integration with Kubernetes).
- **Why now?** Emphasize current trends (e.g., increasing adoption of heterogeneous accelerators, growing demand for ML in cloud environments).
- **Feasibility**: Suggest that the problem is tractable with current tools and expertise.

4. Frame as a Research Problem
------------------------------

- **Structure**: Combine the issue, its impact, and the need for a solution into a concise statement (1-2 sentences).
- **Tone**: Use precise, formal language suitable for a research proposal, avoiding vague terms like "better" or "improved" without context.
- **Alignment**: Ensure the statement directly ties to the research gap and sets up the aim and objectives of your study.

5. Validate the Statement
-------------------------

- **Specificity**: Does it clearly address the gap (heterogeneous ML scheduling in Kubernetes)?
- **Relevance**: Does it connect to current challenges in Computer Systems?
- **Actionability**: Does it suggest a research direction (e.g., designing a new scheduler)?

Example Problem Statement
=========================

*"The default Kubernetes scheduler and existing alternatives, such as Volcano, lack fine-grained support for optimizing pod placement on heterogeneous clusters comprising CPUs, GPUs, and TPUs, resulting in suboptimal performance, resource underutilization, and limited scalability for machine learning workloads. As the adoption of heterogeneous accelerators and ML-driven applications grows in cloud environments, there is an urgent need for a Kubernetes-native scheduling solution that effectively leverages diverse hardware to meet the performance and efficiency demands of modern ML workflows."*

Discussion of the Example
==========================

- **Clarity**: The problem statement specifies the issue (lack of fine-grained scheduling support for heterogeneous clusters) and the context (Kubernetes, ML workloads).
- **Impact**: It highlights consequences (suboptimal performance, resource underutilization, limited scalability) and stakeholders (cloud providers, ML practitioners).
- **Need**: It underscores the urgency due to trends (growing use of heterogeneous accelerators, ML adoption) and implies the gap is unaddressed by referencing limitations in existing schedulers.
- **Alignment with Gap**: The statement directly reflects the research gap, focusing on the need for a Kubernetes-native, hardware-aware scheduler for ML workloads.
- **Research Framing**: It sets up the proposed research (a new scheduler) without prescribing the solution, leaving room for the aim and objectives to elaborate.

Tips for Computer Systems Context
=================================

- **Emphasize Systems Metrics**: Include terms like "performance," "resource utilization," or "scalability" to align with systems research priorities.
- **Ground in Practicality**: Reference real-world platforms (e.g., Kubernetes) and workloads (e.g., ML) to make the problem relevant to industry and academia.
- **Leverage Trends**: Tie the problem to current technological shifts, such as the rise of TPUs or edge computing, to justify timeliness.
- **Be Concise**: Aim for 1-2 sentences to maintain focus, as seen in the example.


Acknowledgement
===============
This article was made with the help of Grok (accessed 2025-07-222)
