---
layout: project
permalink: /projects/os-virtual-machine/
image: /assets/images/os-vm.png
title: Operating Systems Virtual Machine
description: Python-based VM simulating CPU scheduling, paging, and process management.
tech: [Python, Systems Programming]
type: academic
educational: false
featured: false
priority: 6
link: https://github.com/isaiahcat
date: 2025-04-01
date_range: "Mar 2025 - Apr 2025"
---
Designed and implemented a Python-based virtual machine that simulates OS-level process execution, CPU scheduling, and memory management. The VM executes custom assembly-like programs at instruction-level granularity and supports multiple scheduling algorithms with detailed performance visualization.

Key Contributions:
 - Implemented a virtual CPU executing one instruction per tick with full instruction decode and execution pipeline.
 - Designed a flat byte-addressable memory model and extended it with a paging-based MMU.
 - Built full process management using PCBs tracking PID, state, registers, program counter, execution time, and wait time.
 - Implemented and validated multiple CPU scheduling algorithms:
 --- First-Come First-Serve (FCFS)
 --- Round Robin (preemptive, configurable quantum)
 --- Multi-Level Feedback Queue (MFQ) with aging, promotion, and demotion
 - Implemented paging and page-fault tracking, including logical address spaces, frame allocation, eviction, and MMU integration.
 - Generated Gantt charts and performance visualizations to analyze scheduling behavior, wait times, and page fault trends across workloads.
 - Built a shell interface for loading programs, running simulations, and debugging execution (core dumps, error dumps).
 