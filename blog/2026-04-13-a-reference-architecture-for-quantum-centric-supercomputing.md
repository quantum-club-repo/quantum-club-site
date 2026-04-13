---
title: A reference architecture for quantum-centric supercomputing
author: Tej Muralidharan Nambiar
date: 2026-04-14T01:56:00.000+05:30
thumbnail: /assets/images/uploads/qcsc_architecture_v12_1920x1080_d8216f00a9.png
---



Quantum is now a tool capable of performing useful scientific work as part of a quantum-centric supercomputing workflow. But how can computational scientists begin to forge similar paths on their own? What if you have an interesting chemistry or optimization problem and hope to explore the potential of quantum algorithms and quantum hardware in these spaces? How do quantum and HPC centers scale together?

Performing quantum simulations beyond leading classical methods requires a few things: access to a quantum computer, access to classical computing, and an architecture governing how the two communicate. Today, IBM has released **[a reference architecture for quantum-centric computing.](https://arxiv.org/abs/2603.10970)**

This document is a blueprint for computation centers with computational scientists excited to explore quantum in their workflows. At the same time, it’s also a roadmap for how these hybrid systems will scale up and out as quantum and classical mature. But we’re not re-inventing the wheel. With this architecture, we intend to complement and co-design with today’s high-performance computers so computational scientists can easily pull quantum into their existing HPC workflows.

At the highest level, the architecture considers quantum-centric applications, programs that incorporate both quantum and classical libraries for workflows like simulation, optimization, or differential equation solving. As we go down a layer, these libraries map problems to appropriate data structures including tensors and quantum circuits, the core units of computation. In turn, the middleware layer prepares these structures to run on the appropriate hardware, with tools like OpenMP, MPI, and SHMEM prepare data to process on GPUs using CUDA, Triton, and PyTorch, while quantum SDKs like Qiskit, TKET, and CirQ prepare circuits to run on QPUs.

Below the middleware are the workflow and resource management tools that perform orchestration and allocate resources across the appropriate hardware. The [quantum resource management interface (QRMI)](https://arxiv.org/pdf/2506.10052) is one such open tool, a vendor-agnostic library for high-performance compute (HPC) systems to access, control, and monitor the behavior of quantum computational resources.

And finally comes the actual processing and post processing—the workflow and resource management systems that orchestrate the problem across hardware. We use five use case categories to guide the orchestration at this lowest layer, incorporating QPUs and interconnects to scale up and scale out systems of CPUs and GPUs. For example, algorithms like SKQD require scale-out and closed loops, yielding temporal and spatial coupling considerations. Meanwhile, error mitigation requires high-throughput CPU and GPU resources, while users would explore error correction by having low-latency classical systems more closely integrated.

With this reference architecture, computational centers can now bring quantum computing to their own CPU and GPU clusters and fit them into an overarching quantum-centric workflow. Further, they can plan for and anticipate how quantum and classical will continue to grow as quantum matures and new applications arise.

The architecture shows computational scientists with interest in quantum computing and access to HPC how they can take the steps required to explore Feynman’s vision today. Given our ever-maturing AI infrastructure, we’re building and investing into a future reliant on these ever-growing GPU clusters, which we’re ready to augment with quantum.

Feynman presented a vision for the future of simulation—and that future is emerging now. IBM is committed to helping you realize that future yourself.
