Research Proposal Part 4: Writing the Review of Releated Literature
###################################################################

:date: 2025-07-24
:category: Research Proposal
:author: Joseph Anthony C. Hermocilla
:summary: The purpose of the review of related literature is to position your research, highlight the gap, demonstrate expertise, and provide context to your research.

Purpose of the Review of Related Literature Section
====================================================

The review of related literature section serves to:

- **Position your research**: Show how your work builds on or differs from existing studies.
- **Highlight the gap**: Clearly articulate how existing solutions fall short, justifying your proposed research.
- **Demonstrate expertise**: Prove your familiarity with the state-of-the-art in Computer Systems, particularly in Kubernetes, scheduling, and ML workloads for our running example.
- **Provide context**: For our running example, help readers understand the landscape of scheduling in heterogeneous systems.

Guidelines for Writing the Review
==================================

Specifics are for our running example.

1. **Organize by Themes or Categories**: Group related work into logical categories (e.g., general Kubernetes scheduling, heterogeneous systems, ML workload optimization) to make the review structured and easy to follow.
2. **Focus on Relevance**: Prioritize papers directly related to Kubernetes scheduling, heterogeneous hardware, and ML workloads. Include seminal works and recent advancements (within the last 3-5 years, i.e., 2020-2025).
3. **Critically Analyze**: For each work, summarize its contributions, strengths, and limitations, *explicitly linking limitations to your research gap*.
4. **Use Authoritative Sources**: Cite top-tier conference and journal papers (e.g., OSDI, SOSP, NSDI, EuroSys, ASPLOS) and relevant industry whitepapers or open-source documentation.
5. **Be Concise and Targeted**: Aim for 1-2 paragraphs per category, focusing on key works (6-10 papers total) to avoid overwhelming the reader.
6. **Highlight Your Contribution**: Conclude by summarizing how your work addresses the gaps identified in the literature.
7. **Use Clear Citations**: Follow a consistent citation style (e.g., IEEE, ACM) and include DOIs or URLs for accessibility.

Practical Steps for Writing
============================

1. **Gather Sources**:
   
   - Search IEEE Xplore, ACM Digital Library, and arXiv for papers on Kubernetes scheduling, heterogeneous systems, and ML workloads (2020-2025).
   - Check Kubernetes GitHub issues and documentation for practical insights.
   - Monitor X for recent discussions (e.g., #Kubernetes, #MLSystems) to identify preprints or community critiques.

2. **Organize and Summarize**:
   
   - Create a table or spreadsheet to track papers, their contributions, and limitations.
   - Group papers into the three categories above (or adjust based on findings).
   - Summarize each paper in 2-3 sentences, focusing on relevance to your gap.

3. **Draft Critically**:
   
   - For each category, write a paragraph summarizing 2-3 key works, emphasizing their limitations.
   - Use transitions to connect categories (e.g., "While Kubernetes schedulers address general workloads, they fall short in heterogeneous settings…").

4. **Synthesize and Conclude**:
   
   - Write a final paragraph that ties the limitations to your research gap and briefly previews your solution.

5. **Revise for Clarity**:
   
   - Ensure technical terms (e.g., pod, accelerator) are defined or clear from context.
   - Verify citations are complete and follow the required style (e.g., [Author, Conference Year]).


Review of Related Literature Example
====================================

For our running example, the review can be structured into three main subsections, each addressing a relevant aspect of the research gap, followed by a synthesis that ties the discussion to your proposed work. Shown below is a possible structure for the RRL.

*1. Kubernetes Scheduling Frameworks*
-------------------------------------

**Objective**: Review existing Kubernetes scheduling mechanisms and their limitations for heterogeneous ML workloads.

**Example Discussion**:
   *Kubernetes, a widely adopted container orchestration platform, uses a default scheduler that employs a two-phase approach: filtering and scoring [Kubernetes Documentation, 2025]. The default scheduler prioritizes general-purpose metrics like CPU and memory availability but does not account for specialized hardware (e.g., GPUs, TPUs) or ML workload characteristics (e.g., data parallelism). Recent work, such as Firmament [Gog et al., SOSP 2019], integrates flow-based scheduling into Kubernetes, improving throughput for general workloads but lacking specific optimizations for heterogeneous accelerators. Similarly, Volcano [Volcano, 2024] supports batch scheduling for ML tasks but struggles with dynamic resource allocation in mixed CPU/GPU/TPU clusters, as noted in its GitHub issue tracker. These limitations highlight the need for a scheduler tailored to heterogeneous ML environments.*

*2. Scheduling for Heterogeneous Systems*
-----------------------------------------

**Objective**: Analyze scheduling approaches in heterogeneous computing environments beyond Kubernetes.

**Example Discussion**:
   *Scheduling for heterogeneous systems has been explored in contexts like cloud computing and HPC. For instance, Tiresias [Gu et al., NSDI 2020] proposes a GPU cluster scheduler that optimizes for ML training jobs by predicting job duration and prioritizing short tasks. However, Tiresias assumes uniform GPU types and does not address TPU or mixed-accelerator scenarios. Another work, Themis [Mahajan et al., ASPLOS 2021], introduces fairness-aware scheduling for GPU clusters but incurs high overhead in multi-tenant settings with diverse hardware. These approaches, while effective for specific accelerators, do not generalize to Kubernetes clusters with mixed CPU/GPU/TPU nodes, leaving a gap in flexible, hardware-aware scheduling.*

*3. Optimization for ML Workloads*
----------------------------------

**Objective**: Examine systems designed for ML workload optimization, focusing on their scheduling limitations.

**Example Discussion**:
   *ML workloads, such as deep learning training and inference, impose unique demands on system resources. Systems like Allox [Kaur et al., EuroSys 2023] optimize resource allocation for ML jobs in cloud environments by modeling workload dependencies but are not integrated with Kubernetes. Similarly, Google's Borg scheduler [Verma et al., EuroSys 2015] supports large-scale ML workloads but is proprietary and not optimized for open-source platforms like Kubernetes. Recent studies [Wang et al., OSDI 2024] highlight that ML workloads on heterogeneous clusters suffer from resource contention and suboptimal placement due to a lack of hardware-aware scheduling policies. This underscores the need for a Kubernetes-native solution tailored to ML workload demands.*

*4. Synthesis and Gap Identification*
-------------------------------------

**Objective**: Summarize the limitations of existing work and position your research as a solution.

**Example Discussion**:
   *Existing Kubernetes schedulers, such as the default scheduler and Volcano, are designed for general-purpose or batch workloads but lack fine-grained support for heterogeneous hardware and ML-specific requirements. While systems like Tiresias and Themis address GPU scheduling, they do not generalize to mixed CPU/GPU/TPU clusters or integrate with Kubernetes. Furthermore, ML workload optimizations, as seen in Allox, are not designed for containerized environments. Our work addresses these gaps by proposing a Kubernetes scheduler extension that optimizes pod placement for ML workloads on heterogeneous clusters, improving performance, resource utilization, and scalability.*

Tips for Computer Systems Context
=================================

- **Emphasize Systems Metrics**: Discuss how existing works measure performance (e.g., throughput, latency, resource utilization) and where they fall short for ML workloads.
- **Address Practicality**: Highlight gaps in real-world applicability, especially for open-source platforms like Kubernetes.
- **Consider Scalability and Robustness**: Note limitations in handling large-scale or failure-prone clusters, as these are critical in systems research.
- **Stay Current**: Use recent papers (2020-2025) and check preprints on arXiv or discussions on X to ensure your review reflects the latest trends.


The next post will focus on the `Title <{filename}/articles/jach/jach_012.rst>`_.

Acknowledgement
===============
This article was made with the help of Grok (accessed 2025-07-24)
