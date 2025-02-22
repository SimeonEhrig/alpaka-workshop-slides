# Links

- **Time Table for alpaka and OpenPMD Workshop on 23-25 October 2024**
  - [TimeTable](https://events.hifis.net/event/1657/timetable/#all)

- **Presentations**
  - [Introduction to Parallel Programming using alpaka](https://github.com/alpaka-group/alpaka-workshop-slides/blob/oct2024_workshop/presentations/UsingAlpakaWorkshopOctober2024.pdf)
  - [alpaka Features by 2D Heat Equation Solution](https://github.com/alpaka-group/alpaka-workshop-slides/blob/oct2024_workshop/presentations/AlpakaFeaturesByHeatEquationOctober2024.pdf)
  - [OpenPMD: Open Standard for Particle Mesh Data](https://github.com/alpaka-group/alpaka-workshop-slides/blob/oct2024_workshop/presentations/UsingOpenPMDWorkshopOctober2024.pdf)
  - [PIConGPU:Introduction, Concepts and use of Libraries](https://github.com/alpaka-group/alpaka-workshop-slides/blob/oct2024_workshop/presentations/Plasma-PEPSC_workshop_PIConGPU_2024_10_25.pdf)
  - [PIConGPU:Designing an application](https://github.com/alpaka-group/alpaka-workshop-slides/blob/oct2024_workshop/presentations/2024-10-25_pic-plasma-pepsc.pdf)

- **Repository for hands-on exercises and presentations**
  - [All documents of Workshop Alpaka and OpenPMD Section, October 2024](https://github.com/alpaka-group/alpaka-workshop-slides/tree/oct2024_workshop)
  - [Preparation and Alpaka Hands-On1: Connecting to LUMI and Installing Alpaka (Day1 Hands-On 1)](https://github.com/alpaka-group/alpaka-workshop-slides/blob/oct2024_workshop/Day_1/alpaka_install_run_example.md)
  - [OpenMPD First Hands-On (Day2 Hands-On 9)](https://github.com/alpaka-group/alpaka-workshop-slides/tree/oct2024_workshop/Day_2/09_openpmd_basic_object_model)

- **Repositories:**
  - [https://github.com/alpaka-group/alpaka](https://github.com/alpaka-group/alpaka)
  - [https://github.com/openPMD](https://github.com/openPMD)
  - [https://github.com/openPMD/openPMD-api/](https://github.com/openPMD/openPMD-api/)
  - [https://github.com/ComputationalRadiationPhysics/picongpu](https://github.com/ComputationalRadiationPhysics/picongpu)

- **alpaka Documentation:**
  - Main Page: [https://alpaka.readthedocs.io/en/latest/index.html](https://alpaka.readthedocs.io/en/latest/index.html)
  - [Installation Guide](https://alpaka.readthedocs.io/en/latest/)
  - [Cheat Sheet](https://alpaka.readthedocs.io/en/latest/basic/cheatsheet.html)
  - [CMake Variables](https://alpaka.readthedocs.io/en/latest/advanced/cmake.html)
  - [API Docs](https://alpaka-group.github.io/alpaka/)

- **OpenPMD Documentation**
  - [OpenPMD Landing Page](https://www.openpmd.org/#/start)
  - [Main Documentation](https://openpmd-api.readthedocs.io/en/0.16.0/index.html)
  - [First Write](https://openpmd-api.readthedocs.io/en/0.16.0/usage/firstwrite.html)
  - [First Read](https://openpmd-api.readthedocs.io/en/0.16.0/usage/firstread.html)
  - [OpenPMD Projects](https://github.com/openPMD/openPMD-projects)
  - [API Documentation](https://openpmd-api.readthedocs.io/en/0.16.0/_static/doxyhtml/index.html)

- **Others**
  - [Webinar May 2024: alpaka concepts and usage (pdf)](https://github.com/alpaka-group/alpaka-workshop-slides/blob/d40c44081c53041ce618205167c130c973c9b41e/slides-2024/UsingAlpakaForPlasmaPepscWebinar28May2024.pdf)

# The outline of the alpaka and openPMD hands-ons

# Section I: Introduction to Alpaka

## 1. Introduction: What is alpaka, where it is used?
- Support for **heterogeneous architectures** (e.g., CPUs, GPUs, FPGAs).
- Write once, run anywhere—alpaka abstracts hardware specifics for parallel computing.

## 2. Hands-on 1: Installing alpaka and running an example (LUMI)
- Install alpaka with correct cmake backend options
- Compile and run an alpaka example from the repository.
- Verify it runs on the available hardware (CPU, GPU, etc.).

## 3. Parallel programming concepts and portable parallelization by alpaka
- Grid Structure and WorkDivision
- Data Parallelism
- Indexing

## 4. Hands-on 2: HelloIndex kernel which prints indexes

# Section II: Alpaka Features in Action - 2D Heat Equation

## 1. Memory management for 1D and 2D data
- Memory Allocation, Padding and Pitch

## 2. Filling buffers in parallel
- Use indexing to match thread to data

## 3. Hands-on 3: Kernel to fill initial conditions of heat equation

## 4. Heat Equation
- Double accelerator-buffers method to solve Heat Equation
## 5. Preparing stencil kernel
- Difference Equation as a stencil operation

## 6. Hands-on 4: Heat Equation stencil kernel

## 7. alpaka programming features and data-structures
- Accelerator, Device, Queue, Task
- Buffers and Views: Managing memory across devices
- alpaka mdspan
- Setting work division manually

## 8. Usability and optimization
- Hands-on 5: Using alpaka mdspan for easier indexing
- Hands-on 6: Domain Decomposition, chunking or tiling (Day 2)
- Hands-on 7: Using multiple Queues to increase performance. Explore overlap between computation and data transfer (Day 2)
- Hands-on 8: Using Shared Memory for chunksExplore overlap between computation and data transfer (Day 2)

## Timing Runs
- Measure the performance of your kernels and analyze the timing with and without shared memory

# Section III:  OpenPMD

This session will introduce the participants to the scientific metadata format openPMD.
The practical sessions and exercises will include the basic modeling of scientific data via the openPMD-api, possibilities for visualizing openPMD data, streaming I/O workflows, data compression, parallel I/O and more.

## 9. Hands-On 9: OpenPMD Basic Object Model
- First write with openPMD
- Modeling the heatEquation image as openPMD data

## 10. Hands-On 10: Metadata
- Extending the heatEquation output with self-descriptive metadata
- Include: Physical units, grid geometry, timing information, author identification

## 11. Hands-On 11: OpenPMD Visualisation and Json-Toml
- Use matplotlib to load the written file from disk and visualize the HeatEquation as it progresses
- Setup for Jupyter Notebook on LUMI
- Specification for I/O backend and their options (here: compression) from a JSON/TOML-formatted configuration file

## 12. Hands-On 12: Streaming IO
- Visualizing the HeatEquation data again, this time without using the filesystem
- Instead: Read streamed data from the simulation as it progresses
- All that without changing more than one line of code (the filename), I/O options are otherwise steered via the JSON/TOML config

## 13. Solution for Day 1

## 14. Hands-On 14: Interacting with real simulation data created by PIConGPU
- Use the openPMD-viewer to view particle-mesh data produced by PIConGPU
- Post-hoc compression of uncompressed simulation data with `openpmd-pipe`
- Optionally: Inspecting the same data with Paraview

## 15. Hands-On 15: Span API (Advanced)
- Memory-optimized API for workflows that require data preparation from custom internal data structures before output

## 16. Solution for Span API

## 17. Hands-On 17: Constant Components Python Example
- Extended modeling for openPMD data: constant components, particle patches

## 18. Hands-On 18: Parallel Python Example
- Parallel filesystems
- Parallel I/O with ADIOS2: Aggregation strategies
- Parallel I/O with HDF5: Subfiling

## 19. Solution for Day 2

