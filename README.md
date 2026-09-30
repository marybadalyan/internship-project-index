# Mary Badalyan — Project Index

A curated map of my public work in **C++ and low-level systems programming**. Most repositories are self-contained experiments built to understand how software behaves on real hardware — memory, caches, the compiler, the CPU pipeline, and concurrency — each with its own benchmarks, build scripts, and write-up.

---

## ⚙️ Memory & Cache Performance

| Project | Description |
|---|---|
| [Memory_Fragmentation_and_Cache_Efficiency](https://github.com/marybadalyan/Memory_Fragmentation_and_Cache_Efficiency) | Implements and benchmarks three custom allocators — pool, arena, and slab — against standard `malloc`/`new`, measuring allocation speed, fragmentation, and cache locality. Cross-platform CMake (GCC/Clang/MSVC). |
| [Cache_Oblivious_vs_Aware_MatMul](https://github.com/marybadalyan/Cache_Oblivious_vs_Aware_MatMul) | Compares naive, recursive divide-and-conquer, and blocked matrix multiplication in C++20, with block size derived from the detected L1 cache. Recursive and blocked run ~4–5× faster than naive on large matrices. |
| [Cache_Aware_Oblivious_Merge_Sort](https://github.com/marybadalyan/Cache_Aware_Oblivious_Merge_Sort) | Merge sort with cache-line-sized chunking and an in-place gap-based merge. Shows a CPUID-based cache-aware variant yields <0.1% over the cache-oblivious default — validating the oblivious design. |
| [Mat_Trans_with_Cache_Associativity](https://github.com/marybadalyan/Mat_Trans_with_Cache_Associativity) | Matrix transposition tuned around cache associativity: naive vs blocked, with block size chosen to fit the cache and avoid set eviction. |
| [Measuring_Fragmentation](https://github.com/marybadalyan/Measuring_Fragmentation) | Simulates a memory-intensive workload and measures internal and external heap fragmentation over time (Windows and Linux), exporting to CSV with a Python visualizer. |
| [Heap_Fragmentation](https://github.com/marybadalyan/Heap_Fragmentation) | Focused study of how the heap breaks into non-contiguous free blocks, covering internal and external fragmentation. |
| [Memory_Leaks](https://github.com/marybadalyan/Memory_Leaks) | Demonstrates how memory leaks affect usage and allocation performance, with before/after benchmarks. |
| [Virtual_Memory_Simulation](https://github.com/marybadalyan/Virtual_Memory_Simulation) | Explains and simulates the relationship between virtual and physical memory. |
| [Memory_Segments](https://github.com/marybadalyan/Memory_Segments) | Walkthrough of a program's memory layout — stack, heap, data, BSS, text — and what each segment holds. |
| [Aligned_vs_Unaligned_Memory_Access](https://github.com/marybadalyan/Aligned_vs_Unaligned_Memory_Access) | Benchmarks aligned vs unaligned AVX SIMD loads when summing doubles, showing the cost of misalignment. |
| [BandwidthTest](https://github.com/marybadalyan/BandwidthTest) | Multi-threaded memory bandwidth stress test using AVX2 over a 1 GB buffer, reporting throughput in GB/s. |
| [cache_latency](https://github.com/marybadalyan/cache_latency) | Measures memory access latency across stride sizes in a linked list to reveal cache-hierarchy effects. |
| [row_column_access](https://github.com/marybadalyan/row_column_access) | Benchmarks row-major vs column-major access over a 2D matrix to show the impact of locality. |
| [falseSharing](https://github.com/marybadalyan/falseSharing) | Demonstrates the performance hit of false sharing between threads and how to avoid it. |

## 🧩 Compiler & Low-Level Optimization

| Project | Description |
|---|---|
| [Register_Usage_Opt](https://github.com/marybadalyan/Register_Usage_Opt) | Compares pointer dereferencing vs direct indexing in nested loops, inspecting the generated assembly and how aliasing assumptions affect SIMD optimization. |
| [Inlining_Demonstration](https://github.com/marybadalyan/Inlining_Demonstration) | Explores function-call overhead in tight loops and how inlining changes performance. |
| [Short-String_Optimization](https://github.com/marybadalyan/Short-String_Optimization) | Explains and demonstrates Short String Optimization (SSO) in `std::string` and why avoiding heap allocation matters. |
| [Modularity_Efficiency](https://github.com/marybadalyan/Modularity_Efficiency) | Benchmarks whether splitting arithmetic into helper functions hurts the compiler's ability to auto-vectorize. |
| [Instruction_Reordering_Experiment](https://github.com/marybadalyan/Instruction_Reordering_Experiment) | Models a CPU Reorder Buffer (ROB) to illustrate out-of-order execution with in-order commit. |

## 🧵 Concurrency & Multithreading

| Project | Description |
|---|---|
| [Multithreading-Multyasyncing](https://github.com/marybadalyan/Multithreading-Multyasyncing) | A modern C++17 thread pool: thread-safe task submission, graceful shutdown, live stats reporting, and a dynamic task producer for stress testing. |
| [Thread-Safe_Counter](https://github.com/marybadalyan/Thread-Safe_Counter) | Compares atomic memory-ordering models (`seq_cst`, `relaxed`, `acquire`, `release`) against a non-atomic counter for correctness and performance. |
| [Parallel_Summation](https://github.com/marybadalyan/Parallel_Summation) | Parallel array summation via non-atomic reduce, atomic, and mutex approaches, weighing correctness vs speed. |
| [Deadlock_experiment](https://github.com/marybadalyan/Deadlock_experiment) | Creates a classic two-mutex deadlock, then fixes it with consistent lock ordering and `std::scoped_lock`. |
| [Priority_Inversion_-Mars_Pathfinder-](https://github.com/marybadalyan/Priority_Inversion_-Mars_Pathfinder-) | Recreates the Mars Pathfinder priority-inversion bug and its priority-inheritance fix, wrapped in a cross-platform GitHub Actions CI pipeline (MSVC/GCC/Clang with `ctest`). |

## 🔐 Systems Security (educational)

| Project | Description |
|---|---|
| [Buffer_Overflow](https://github.com/marybadalyan/Buffer_Overflow) | Educational demonstration of how an unbounded input can overrun a fixed-size stack buffer. |
| [Stack_Smashing-](https://github.com/marybadalyan/Stack_Smashing-) | Companion demo showing stack-corruption behavior and the compiler protections that detect it. |
| [Detecting_Stack_Overflow](https://github.com/marybadalyan/Detecting_Stack_Overflow) | Techniques for detecting stack overflow conditions at runtime. |
| [ROP_gadgets](https://github.com/marybadalyan/ROP_gadgets) | Educational look at Return-Oriented Programming: how control flow can be redirected, and why stack protections and PIE exist. |
| [Execute_Heap](https://github.com/marybadalyan/Execute_Heap) | Explores executable memory permissions (JIT-style) with `mmap`/`VirtualAlloc`, and the DEP/NX and W^X protections that restrict it. |
| [Kernel_Space_Access](https://github.com/marybadalyan/Kernel_Space_Access) | Demonstrates the user/kernel memory boundary and why user space can't reach kernel space. |

## 🌳 Data Structures & Algorithms

| Project | Description |
|---|---|
| [STLContainerImplementations](https://github.com/marybadalyan/STLContainerImplementations) | From-scratch C++ binary search tree with a full set of recursive and iterative operations (traversals, height, counts, width). |
| [ContainerPerformanceAnalysis](https://github.com/marybadalyan/ContainerPerformanceAnalysis) | Benchmarks middle-insertion performance of `std::vector` vs `std::list`. |

## 🛠️ Tools & Other

| Project | Description |
|---|---|
| [Curl_Wrapper](https://github.com/marybadalyan/Curl_Wrapper) | Modern RAII C++ wrapper around libcurl's easy interface — safe handle/global-state management, exception-based errors, cross-platform CMake with CI. |

---

*Contributions and experiments are ongoing — this list is regenerated as new projects land.*
