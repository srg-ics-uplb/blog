Lock–Unlock: Is That All? A Pragmatic Analysis of Locking in Software Systems
###############################################################################

:date: 2019-4-14
:category: Paper Review
:author: Joseph Anthony C. Hermocilla

Most processors nowadays are multi-core processors to take advantage of parallel processing. 
Associated with parallel processing is the synchronization problem wherein locks are extensively 
used. This paper [GUERRAOUI2019]_ argues that despite the large amount of available choices for 
lock algorithms, developers do not have a comprehensive guide to select an algorithm. The paper also 
asserts that most research on lock algorithms are limited to mutex locks and rarely consider other 
techniques like trylocks and condition variables. In addition, most evaluation of lock algorithms 
use workload that are specific to the design of the lock. Lastly, evaluation is focused only on throughput 
neglecting energy efficiency and tail latency.

The main contribution of this paper is a broad performance study of lock algorithms. Specifically, 
28 state-of-the-art algorithms were studied and applied to 40 applications. The experiments where 
conducted of 4 different multi-core machines. As mentioned, this study considered energy efficiency and 
tail latency, in addition to throughtput, as metrics in the evaluation. In the paper, the authors 
claimed that it is really difficult to choose a well-performing lock for an application because of 
several factors: workload, hardware, degree of parallelism, number of locks, how they are used, interaction 
between the application and the CPU scheduler, and metric. The authors also developed a library called LiTL 
used for testing the applications. 

The authors have the following observations as a result of their study

 - Trylocks and condition variables should also be considered
 - Memory footprint of lock algorithms affect performance
 - Interaction between locks and scheduling affects performance
 - Lock tail latency may not affect application tail latency
 - No single lock is systematically the best
 - Choosing the best lock is difficult
 - Energy efficiency and throughput go hand-in-hand in lock algorithms

The figure below is a guide for developers in selecting the appropriate lock considering 
the findings of the the study.

.. image:: ./images/jach/locks.png
   :width: 40%



.. [GUERRAOUI2019] Guerraoui, R., Guiroux, H., Lachaize, R., Quéma, V., & Trigonakis, V. (2019). Lock–Unlock: Is That All? A Pragmatic Analysis of Locking in Software Systems. ACM Transactions on Computer Systems, 36(1), 1–149. https://doi.org/10.1145/3301501
