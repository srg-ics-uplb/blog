Research Proposal Part 6: Evaluation and Validation
###################################################

:date: 2025-07-25 15:00 
:category: Research Proposal
:author: Joseph Anthony C. Hermocilla
:summary: This post discusses how to evaluate and validate the artifact(usually software implementation) of the research. It describes what to include in the evaluation and validation plan. This is an expanded discussion for the Methods section of the research proposal. 
 
This post discusses how to evaluate and validate the artifact(usually software implementation) of the research. It describes what to include in the evaluation and validation plan. This is an expanded discussion for the Methods section of the research proposal. This discussion outlines the principles, methodologies, and best practices for evaluating and validating a new system in the context of computer system. Again, we use the Kubernetes scheduler as the example.

1. **Define Clear Evaluation Metrics**
--------------------------------------

**Purpose**: Metrics quantify the system’s performance and align with the research objectives (e.g., optimizing ML workloads on heterogeneous clusters, Objective 3 in the previous posts) .

**Systems-Specific Metrics**:

- **Performance**: Throughput (tasks completed per second), latency (task completion time).
- **Efficiency**: Resource utilization (CPU, GPU, TPU usage), energy consumption.
- **Scalability**: Performance under varying cluster sizes or workloads.
- **Robustness**: Behavior under failures (e.g., node crashes, network delays).

**Example Relevance**: For the scheduler, metrics should measure improvements in ML workload performance and resource efficiency compared to the default Kubernetes scheduler or alternatives like Volcano.

2. **Select Appropriate Baselines**
-----------------------------------

**Purpose**: Compare the proposed system against state-of-the-art or widely used systems to highlight its novelty and improvements.

**Choices**: Include the default Kubernetes scheduler, advanced schedulers like Volcano or Firmament, and possibly domain-specific solutions like Tiresias for GPU clusters.

**Example Relevance**: Comparing against the default Kubernetes scheduler shows practical improvements, while comparing against Volcano highlights advantages in heterogeneous ML environments.

3. **Design Realistic Experimental Scenarios**
----------------------------------------------

**Purpose**: Test the system under conditions that reflect real-world use cases.

**Workloads**: Use standard ML benchmarks (e.g., MLPerf for training/inference tasks like ResNet, BERT) to simulate realistic ML workloads.

**Environment**: Deploy on a heterogeneous cluster (e.g., CPUs, NVIDIA GPUs, Google TPUs) using a cloud platform like Google Kubernetes Engine (GKE) or a local testbed.

**Variations**: Test diverse scenarios, such as small vs. large clusters, high vs. low workload intensity, and failure conditions (e.g., node failures).

**Example Relevance**: The scheduler must handle dynamic ML workloads on mixed hardware, so experiments should include varied cluster configurations and failure scenarios.

4. **Implement a Controlled Experimental Setup**
------------------------------------------------

**Purpose**: Ensure experiments are reproducible, fair, and isolate the impact of the proposed system.

**Steps**:

- **Hardware Specification**: Use consistent hardware (e.g., Intel Xeon CPUs, NVIDIA A100 GPUs, Google TPU v4).
- **Software Stack**: Standardize Kubernetes version (e.g., v1.30) and dependencies.
- **Control Variables**: Fix parameters like network bandwidth or storage to isolate scheduling effects.

**Example Relevance**: The setup should replicate a production-like Kubernetes cluster to validate the scheduler’s performance in realistic ML deployments.

5. **Validate Correctness and Robustness**
------------------------------------------

**Purpose**: Ensure the system works as intended and handles edge cases.

**Correctness**: Verify that pods are placed according to the scheduler’s logic (e.g., hardware-aware placement) using logs or tracing.

**Robustness**: Test under stress conditions (e.g., node failures, network partitions) to ensure the scheduler maintains stability.

**Example Relevance**: Validate that the scheduler correctly prioritizes GPU/TPU nodes for ML tasks and doesn’t crash under high load or failures.

6. **Analyze and Compare Results**
-----------------------------------

**Purpose**: Quantify improvements and draw meaningful conclusions.

**Statistical Analysis**: Use averages, medians, and standard deviations for metrics like latency and throughput. Apply statistical tests (e.g., t-tests) if needed to confirm significance.

**Visualization**: Use charts (e.g., bar charts for throughput, line charts for scalability) to present results clearly.

**Example Relevance**: Compare the proposed scheduler’s performance against baselines to show, for instance, a 20% reduction in latency or 30% better GPU utilization.

7. **Ensure Reproducibility and Transparency**
----------------------------------------------

**Purpose**: Allow others to verify and build on your results, a hallmark of systems research.

**Steps**:

- Share code and configurations (e.g., via GitHub).
- Document the experimental setup (hardware, software, workloads).
- Publish datasets or workload traces if possible.

**Example Relevance**: Provide the scheduler’s source code and ML workload configurations to enable replication on other Kubernetes clusters.

8. **Address Limitations**
--------------------------

**Purpose**: Acknowledge boundaries of the evaluation to maintain credibility.

**Examples**: Note if the evaluation is limited to specific ML models, cluster sizes, or hardware types.

**Example Relevance**: Highlight that the scheduler is optimized for ML workloads and may need adaptation for other workload types (e.g., HPC).

9. **Align with Systems Research Standards**
--------------------------------------------

**Conferences**: Follow evaluation rigor seen in top venues like OSDI, SOSP, or NSDI, where systems are tested under diverse workloads and failure modes.

**Real-World Relevance**: Emphasize practical impact, such as deployment feasibility in production Kubernetes clusters.

**Example Relevance**: The evaluation should mirror industry needs (e.g., efficient ML deployment) to appeal to both academic and practitioner audiences.

----

Evaluation and Validation Plan Example
======================================

To evaluate and validate the proposed Kubernetes scheduler extension for optimizing pod placement for machine learning workloads on heterogeneous CPU/GPU/TPU clusters, the following methodology will be employed:

**1. Metrics**:

- **Throughput**: ML tasks completed per second.
- **Latency**: Average and tail latency for task completion.
- **Resource Utilization**: Percentage usage of CPU, GPU, and TPU resources.
- **Scheduling Overhead**: Time taken to make scheduling decisions.
- **Robustness**: System stability under node failures or network delays.

**2. Baselines**:

- Default Kubernetes scheduler (v1.30).
- Volcano scheduler for batch ML workloads.
- Tiresias (adapted for Kubernetes, if feasible) for GPU-specific scheduling.

**3. Experimental Setup**:

- **Testbed**: A cluster with 8 nodes (4 Intel Xeon CPUs, 2 NVIDIA A100 GPUs, 2 Google TPU v4) on Google Kubernetes Engine (GKE).
- **Workloads**: MLPerf benchmarks (ResNet-50 for training, BERT for inference) with varying batch sizes and data parallelism levels.
- **Scenarios**:
  - Small cluster (4 nodes) vs. large cluster (16 nodes).
  - Low-intensity (10 tasks) vs. high-intensity (100 tasks) workloads.
  - Failure scenarios: Simulate 1–2 node crashes and 100ms network delays.

**4. Implementation**:

- Deploy the scheduler extension as a custom Kubernetes scheduler using Go, integrated with the Kubernetes API.
- Use kube-scheduler’s pluggable architecture to ensure compatibility.
- Log scheduling decisions and resource allocations for correctness validation.

**5. Validation**:

- **Correctness**: Verify that pods are placed on appropriate hardware (e.g., GPUs/TPUs for compute-intensive tasks) using Kubernetes logs and tracing tools (e.g., Jaeger).
- **Robustness**: Test scheduler stability under failures, ensuring no crashes and minimal performance degradation (e.g., <10% latency increase).

**6. Analysis**:

- Collect metrics over 10 runs per scenario to compute averages and standard deviations.
- Compare against baselines to quantify improvements (e.g., 20% lower latency, 30% higher GPU utilization).
- Use statistical tests (e.g., t-test) to confirm significance of results.

**7. Visualization**:

Create charts and tables that compare the schedulers based on throughput and latency. For example: 

+------------------------+---------------------+---------+---------+
| Metric                 | Scheduler           | Value   | Unit    |
+========================+=====================+=========+=========+
| Throughput             | Default Scheduler   | 50      | Tasks/s |
+                        +---------------------+---------+---------+
|                        | Volcano             | 60      | Tasks/s |
+                        +---------------------+---------+---------+
|                        | Tiresias            | 65      | Tasks/s |
+                        +---------------------+---------+---------+
|                        | Proposed Scheduler  | 80      | Tasks/s |
+------------------------+---------------------+---------+---------+
| Latency                | Default Scheduler   | 200     | ms      |
+                        +---------------------+---------+---------+
|                        | Volcano             | 180     | ms      |
+                        +---------------------+---------+---------+
|                        | Tiresias            | 170     | ms      |
+                        +---------------------+---------+---------+
|                        | Proposed Scheduler  | 140     | ms      |
+------------------------+---------------------+---------+---------+


**8. Reproducibility**:

- Share the scheduler’s source code and configuration scripts on GitHub.
- Provide detailed documentation of the testbed setup, workload parameters, and failure scenarios.
- Publish MLPerf workload traces for replication.

**9. Limitations**:

- Evaluation is focused on ML workloads (ResNet, BERT) and may require adaptation for other workloads (e.g., HPC).
- Limited to specific hardware (A100 GPUs, TPU v4); results may vary with other accelerators.

Discussion of the Evaluation and Validation Plan Example
========================================================

- **Metrics**: The chosen metrics align with Computer Systems priorities and the research objectives, directly addressing the gap in performance and efficiency for ML workloads.
- **Baselines**: Comparing against the default Kubernetes scheduler, Volcano, and Tiresias ensures a comprehensive assessment against general-purpose and ML-specific schedulers.
- **Experimental Setup**: The use of MLPerf benchmarks and a heterogeneous GKE cluster reflects real-world ML deployments.
- **Validation**: Correctness checks and robustness tests ensure the scheduler works as intended and handles edge cases.
- **Analysis and Visualization**: Bar charts compare key metrics across schedulers, making results clear and compelling.
- **Reproducibility**: Sharing code and documentation aligns with systems research standards.
- **Limitations**: Acknowledging the focus on ML workloads and specific hardware maintains transparency and suggests future work.

----


Additional Tips for Computer Systems Evaluation
===============================================

- **Real-World Relevance**: Use industry-standard tools (e.g., Kubernetes, MLPerf) to appeal to practitioners.
- **Stress Testing**: Include failure scenarios (e.g., node crashes) to mimic production environments.
- **Quantitative Rigor**: Provide precise measurements and statistical analysis to meet the expectations of top-tier conferences.
- **Open-Source Contribution**: Sharing code and traces enhances impact, especially for Kubernetes-related research.


Acknowledgement
===============
This article was made with the help of Grok (accessed 2025-07-25)
