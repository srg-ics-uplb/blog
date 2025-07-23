Research Proposal Part 3: Writing the Aim, Objectives, and Methods
##################################################################

:date: 2025-07-23
:category: Research, Proposal
:author: Joseph Anthony C. Hermocilla

Once a research gap has been identified and Problem Statement has been drafted, the Aim, Objectives, and Methods can now be written. Below is a short discussion on how to write the Aim, Objectives, and Methods for a research proposal based on the example from `Approach 5: Analyzing real-world systems and industry needs <{filename}/articles/jach/jach_008.rst>`_. The example identified a research gap in *developing a Kubernetes scheduler extension that optimizes for heterogeneous hardware in ML-heavy clusters*, inspired by unresolved issues in the Kubernetes GitHub tracker about inefficient pod scheduling on mixed CPU/GPU/TPU nodes.

When crafting a research proposal for this gap, the Aim, Objectives, and Methods sections should clearly articulate the purpose, specific goals, and approach to addressing the problem. These sections must be concise, focused, and aligned with the identified gap, ensuring the research is feasible and impactful in the context of Computer Systems.

1. Aim (aka General Objective)
------------------------------

The Aim is a single, high-level statement that captures the overall purpose of the research. It should directly address the research gap and highlight the intended contribution to the field.

**Guidelines**:

- Be specific about the problem (inefficient scheduling in Kubernetes for heterogeneous ML clusters).
- Emphasize the desired outcome (improved performance, resource utilization, or fairness).
- Keep it concise (1–2 sentences) and avoid technical jargon to ensure clarity.
- Align with the gap’s real-world relevance (e.g., supporting machine learning workloads).

**Example Aim**:

*The aim of this research is to develop a Kubernetes scheduler extension that optimizes pod placement for machine learning workloads on heterogeneous clusters, enhancing performance and resource utilization.*

2. (Specific) Objectives
------------------------

The Objectives break down the aim into specific, measurable, and achievable goals. They should outline the key steps or outcomes needed to address the research gap.

**Guidelines**:

- Use actionable verbs (e.g., design, evaluate, implement) to describe what will be achieved.
- Ensure objectives are SMART (Specific, Measurable, Achievable, Relevant, Time-bound).
- Cover both technical (e.g., algorithm design) and evaluative (e.g., performance analysis) aspects.
- Typically, include 3–5 objectives to keep the scope manageable.
- Reflect the systems-specific context (e.g., handling GPUs/TPUs, improving ML workload efficiency).

**Example Objectives**:

#. *To design a scheduling algorithm that accounts for heterogeneous hardware (CPU, GPU, TPU) characteristics in Kubernetes clusters.*
#. *To implement the proposed scheduler extension as a pluggable module in the Kubernetes framework.*
#. *To evaluate the scheduler’s performance in terms of throughput, latency, and resource utilization for ML workloads compared to the default Kubernetes scheduler.*
#. *To assess the scheduler’s scalability and robustness under diverse ML workloads and cluster configurations.*

3. Methods
----------

The Methods section describes the technical approach to achieving the objectives. It should provide a clear, logical plan for designing, implementing, and evaluating the solution, tailored to the Computer Systems domain.

**Guidelines**:

- Outline the key steps: algorithm design, implementation, experimentation, and evaluation.
- Specify tools, platforms, or frameworks (e.g., Kubernetes, ML benchmarks like MLPerf).
- Describe the experimental setup, including hardware (e.g., heterogeneous clusters) and metrics (e.g., throughput, latency).
- Address how the methods tackle the gap (e.g., optimizing for heterogeneous hardware).
- Ensure feasibility by leveraging existing tools and datasets where possible.
- Include validation or comparison against baselines (e.g., default Kubernetes scheduler).

**Example Methods**:

To address the identified gap, the research will proceed as follows:


#. *Algorithm Design: Develop a scheduling algorithm that incorporates hardware-specific metrics (e.g., GPU memory bandwidth, TPU compute capacity) and ML workload requirements (e.g., data parallelism, model size). The algorithm will use a weighted scoring model to prioritize pod placement based on resource compatibility and workload demands.*

#. *Implementation: Implement the scheduler as a custom Kubernetes scheduler extension using Go, integrated with the Kubernetes API. The extension will leverage kube-scheduler’s pluggable architecture to ensure compatibility with existing clusters.*

#. *Experimental Setup: Deploy a testbed cluster with mixed CPU (Intel Xeon), GPU (NVIDIA A100), and TPU (Google Cloud TPU v4) nodes using a cloud provider like Google Kubernetes Engine (GKE). Use ML workloads from MLPerf (e.g., ResNet, BERT) to simulate real-world scenarios.*

#. *Evaluation: Compare the proposed scheduler against the default Kubernetes scheduler and state-of-the-art alternatives (e.g., Volcano). Measure key metrics: (a) throughput (tasks completed per second), (b) latency (task completion time), (c) resource utilization (CPU/GPU/TPU usage), and (d) scheduling overhead. Conduct experiments under varying cluster sizes (4–16 nodes) and workload intensities.*

#. *Validation: Analyze results to confirm improvements in performance and scalability, and validate robustness by introducing synthetic failures (e.g., node crashes) to test fault tolerance.*


Discussion
==========

- **Aim**: The example aim is concise and directly targets the gap by focusing on optimizing Kubernetes scheduling for heterogeneous ML clusters. It emphasizes practical impact (performance, resource utilization), which is critical for industry adoption.

- **Objectives**: The objectives break the aim into actionable steps, covering design, implementation, and evaluation. They are specific (e.g., handling CPU/GPU/TPU) and measurable (e.g., throughput, latency), ensuring the research is focused and achievable within a typical systems project timeline.

- **Methods**: The methods provide a clear roadmap, leveraging existing tools (Kubernetes, MLPerf, GKE) to ensure feasibility. The experimental setup reflects real-world ML cluster scenarios, and the comparison with baselines (default scheduler, Volcano) strengthens the evaluation. The inclusion of fault tolerance testing aligns with systems research priorities like robustness.


Acknowledgement
===============
This article was made with the help of Grok (accessed 2025-07-23)
