# Adaptive-Load-Balancing-with-Queue-Partitioning-in-Cloud-Systems

**Authors:**
Bhumi Chauhan (E22CSEU0585)
Dron Rawat (E22CSEU0652)

---

## Abstract

The ambitious nature of the present digital era demands IT industries to increase their return on investment and achieve better results. One such emerging technology is cloud computing, which benefits businesses by saving resources, time, investment, and maintenance costs. However, excessive workload on cloud servers results in performance issues. This paper addresses load balancing among servers to improve Quality of Service (QoS). A "Queue Partitioning Technique" is proposed where incoming tasks are partitioned and distributed to virtual machines using a quick sort technique. This algorithm, evaluated using CloudSim simulator, shows improved waiting time and load distribution compared to existing methods.

---

## Table of Contents

* [Abstract](#abstract)
* [1. Introduction](#1-introduction)
* [2. Related Work](#2-related-work)
* [3. Proposed Algorithm](#3-proposed-algorithm)
* [4. Results and Discussion](#4-results-and-discussion)
* [5. Conclusion](#5-conclusion)
* [6. References](#6-references)

---

## 1. Introduction

Cloud computing is the practice of using a network of remote servers on the internet to store, manage, and process data. It is offered as:

* **SaaS**: Software available over the internet on a pay-per-use basis.
* **IaaS**: Server and storage managed by providers.
* **PaaS**: Resources to build applications provided by the cloud provider.

**Benefits of cloud computing:**

* Easy integration
* Cost savings
* Ease of access
* Pay-as-you-go
* Ideal for start-ups

However, challenges like security, QoS, and workload distribution remain. An intelligent load balancing method ensures resources are utilized properly, response times are improved, and SLAs (Service Level Agreements) are met. This paper proposes a framework using queue partitioning and quick sort for better load distribution and response time.

## 2. Related Work

Previous algorithms include:

* **Opportunistic Load Balancing (OLB)** and **Load Balance Min-Min (LBMM)** by Shu Ching Wang et al.
* **Best Task Order (BTO)**, **Enhanced OLB (EOLB)**, and **Enhanced Min-Min (EMM)** algorithms.
* **Throttled Load Balancer** by Meenakshi Sharma et al.
* **Round Robin algorithm** (simple but ineffective in task execution time consideration).
* **Weighted Active Monitoring Load Balancing (WALB)** by Jasmin James et al.
* **Priority-based resource allocation** by K C Gouda et al.
* **Effective VM Load Balancing algorithm** that allocates tasks based on expected response time.

## 3. Proposed Algorithm

Incoming tasks are sorted by expected execution time. Using two pointers `i` and `j`, tasks are partitioned and distributed across virtual machines (VMs) using a quick sort approach.

### Algorithm Steps:

* Compute expected execution time for each task.
* Sort tasks in increasing order.
* Partition sorted tasks into `M` sets (where `M` is number of VMs).
* Assign tasks using pointers `i` (start) and `j` (end).

```pseudo
QTask: Incoming Tasks
For each task in QTask:
  Calculate Expected Execution Time
Sort QTask by Execution Time
Partition into M sets
Initialize i = 0, j = N-1
While i < j:
  For each VM:
    Assign task[i] and task[j] to VM
    i++, j--
Repeat for next batch
```

## 4. Results and Discussion

Simulation was done using CloudSim 3.0.3 on Windows 11, AMD Ryzen 5, 16GB RAM.

### Load Distribution

The proposed algorithm distributed load equally among VMs compared to Round Robin and Effective VM Load Balancing algorithms.

### Waiting Time Comparison

| Algorithm              | Avg. Waiting Time (sec) |
| ---------------------- | ----------------------- |
| Round Robin            | 2.3                     |
| Effective VM Load Bal. | 2.2                     |
| **Queue Partitioning** | **1.6**                 |

### Task Execution Time

| Task ID | Round Robin (sec) | Effective VM (sec) | Queue Partitioning (sec) |
| ------- | ----------------- | ------------------ | ------------------------ |
| T1      | 2.5               | 2.2                | 1.7                      |
| T2      | 2.4               | 2.1                | 1.6                      |
| T3      | 2.6               | 2.3                | 1.5                      |

### Resource Utilization

| Algorithm              | CPU (%)  | Memory (%) |
| ---------------------- | -------- | ---------- |
| Round Robin            | 63.5     | 58.3       |
| Effective VM Load Bal. | 68.2     | 64.1       |
| **Queue Partitioning** | **78.9** | **70.4**   |

### Throughput Analysis

| Number of Tasks | Round Robin (tasks/sec) | Effective VM (tasks/sec) | Queue Partitioning (tasks/sec) |
| --------------- | ----------------------- | ------------------------ | ------------------------------ |
| 50              | 17                      | 21                       | 29                             |
| 100             | 15                      | 20                       | 28                             |
| 150             | 13                      | 18                       | 27                             |

## 5. Conclusion

This paper proposed the **Queue Partitioning Algorithm** for load balancing in cloud servers. It effectively balances loads and reduces average waiting time, outperforming Round Robin and Effective VM Load Balancing algorithms. Graphical results confirmed better response time and resource utilization.

## 6. References

1. K.Soniya, Dr.A.Senthil Kumar, “A Basic study on Cloud Computing,” IOSR Journal of Computer Engineering (IOSR-JCE).
2. Raj Kumar Buyya, J.Broberg, A.Goscinst, "Cloud Computing: Principles and paradigms", Wiley, 2011.
3. Rajeshwari B S, Dr. M Oakshayini, "Comprehensive Study on Load Balancing Techniques in Cloud".
4. Shu Ching Wang et al., "Towards Load Balancing in a Three Level Cloud Network", ICCSIT 2010.
5. Shu Ching Wang et al., "Three Phase Scheduling in a Hierarchical Cloud", CMC 2011.
6. Meenakshi Sharma et al., "Performance Evaluation of Adaptive VM Load Balancing", IJACSA 2012.
7. Meenakshi Sharma et al., "Efficient Load Balancing Algorithm in VM Cloud Environment", IJACSA 2012.
8. Shanti Swaroop Moharana et al., "Analysis of Load Balancers in Cloud Computing", IJCS\&E 2013.
9. Demystifying\_the\_cloud\_ebook.pdf.
10. Anthony Velte et al., "Cloud Computing: A Practical Approach", Tata McGraw Hill, 2009.

---

## 📂 Repository Structure

```bash
├── data/          # Raw datasets
├── src/           # Source code files
├── results/       # Output results (charts, models)
├── README.md      # Project documentation
└── ...
```
