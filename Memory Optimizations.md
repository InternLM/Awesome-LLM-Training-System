# Memory Optimizations

To address memory constraints of LLM training, various memory-efficient techniques have been proposed. These include activation recomputation strategies, which trade increased computation for reduced memory usage; redundancy reduction methods that minimize data duplication across training processes; defragmentation techniques that optimize memory allocation and deallocation to reduce fragmentation and improve memory utilization; and swap and offload approaches that leverage CPU memory and NVMe SSDs to supplement GPU memory. 

## Activation Recomputation

### *Dynamic Evicting*
- Dynamic tensor rematerialization [[Paper]](https://arxiv.org/abs/2006.09616) [[Code]](https://github.com/uwsampl/dtr-prototype)
    - M. Kirisame et al.
    - ICLR 2021
- Megtaichi: Dynamic tensor-based memory management optimization for dnn training  [[Paper]](https://dl.acm.org/doi/10.1145/3524059.3532394)
    - ICS 2022
- Coop: Memory is not a commodity [[Paper]](https://arxiv.org/pdf/2311.00591)
    - J. Zhang et al.
    - NeurIPS 2023

### *Static Evicting*
- Checkmate: Breaking the memory wall with optimal tensor rematerialization [[Paper]](https://arxiv.org/pdf/1910.02653) [[Code]](https://github.com/parasj/checkmate)
    - P. Jain et al.
    - MLSys 2020
- Loongtrain: Efficient training of long-sequence llms with head-context parallelism [[Paper]](https://arxiv.org/pdf/2406.18485) 
    - D. Gu et al.
- Accelerating the Training of Large Language Models using Efficient Activation Rematerialization and Optimal Hybrid Parallelism [[Paper]](https://www.usenix.org/system/files/atc24-yuan.pdf)
    - T. Yuan et al. 
    - USENIX 2024
- Reducing activation recomputation in large transformer models [[Paper]](https://arxiv.org/pdf/2205.05198) [[Code]](https://github.com/NVIDIA/Megatron-LM)
    - V. A. Korthikanti et al.
    - MLSys 2023
- DISTFLASHATTN: Distributed Memory-efficient Attention for Long-context LLMs Training [[Paper]](https://arxiv.org/pdf/2310.03294) [[Code]](https://github.com/RulinShao/LightSeq)
    -  D. Li et al.


## Redundancy Reduction

### *Fully Sharding*

ZeRO [145], FSDP [146]

- ZeRO: Memory optimizations Toward Training Trillion Parameter Models [[Paper]](https://ieeexplore.ieee.org/abstract/document/9355301) [[Code]](https://github.com/microsoft/DeepSpeed)
    - S. Rajbhandari et al.
    - SC 2020

- PyTorch FSDP: Experiences on Scaling Fully Sharded Data Parallel [[Paper]](https://arxiv.org/pdf/2304.11277) [[Code]](https://github.com/pytorch)
    - Y. Zhao et al.
    - VLDB 2023

### *Partially Sharding*

- ZeRO++: Extremely Efficient Collective Communication for Giant Model Training [[Paper]](https://arxiv.org/pdf/2306.10209)
    - G. Wang et al.
    - ICLR 24 Poster
- MiCS: Near-linear Scaling for Training Gigantic Model on Public Cloud [[Paper]](https://arxiv.org/pdf/2205.00119)
    - Z. Zhang et al.
    - VLDB 2022
- Rethinking Memory and Communication Cost for Efficient Large Language Model Training [[Paper]](http://arxiv.org/abs/2310.06003)
    - C. Wu et al.
- RTP: Rethinking Tensor Parallelism with Memory Deduplication [[Paper]](http://arxiv.org/abs/2311.01635)
    - C. Luo et al.
- AMSP: Reducing Communication Overhead of ZeRO for Efficient LLM Training [[Paper]](https://arxiv.org/abs/2406.18485)
    - Q. Chen et al.

## Defragmentation

### *Tensor-based Defragmentation*

- ROAM: memory-efficient large DNN training via optimized operator ordering and memory layout [[Paper]](http://arxiv.org/abs/2310.19295)
    - H. Shu et al.
- ZeRO: Memory optimizations Toward Training Trillion Parameter Models [[Paper]](https://ieeexplore.ieee.org/abstract/document/9355301) [[Code]](https://github.com/microsoft/DeepSpeed)
    - S. Rajbhandari et al.
    - SC 2020
- A Heuristic for Periodic Memory Allocation with Little Fragmentation to Train Neural Networks [[Paper]](https://dl.acm.org/doi/10.1145/3652024.3665508)
    - A. Imanishi et al.
    - ISMM 2024
- Megtaichi: Dynamic tensor-based memory management optimization for dnn training  [[Paper]](https://dl.acm.org/doi/10.1145/3524059.3532394)
    - ICS 2022
- Coop: Memory is not a commodity [[Paper]](https://arxiv.org/pdf/2311.00591)
    - J. Zhang et al.
    - NeurIPS 2023

### *VMM-based Defragmentation*

- GMLake: Efficient and Transparent GPU Memory Defragmentation for Large-scale DNN Training with Virtual Memory Stitching [[Paper]](https://dl.acm.org/doi/10.1145/3620665.3640423) [[Code]](https://github.com/intelligent-machine-learning/glake/tree/main/GMLake)
    - C. Guo et al.
    - ASPLOS 2024
- Expandable Segments [[Code]](https://github.com/pytorch/pytorch/pull/96995)

## Offloading


### *CPU Offloading*

- **Static Offloading**
    - Training Large Neural Networks with Constant Memory using a New Execution Algorithm [[Paper]](https://arxiv.org/pdf/2002.05645)
        - B. Pudipeddi et al.
    - ZeRO-Offload: Democratizing Billion-Scale Model Training [[Paper]](https://www.usenix.org/system/files/atc21-ren-jie.pdf)
        - J. Ren et al.
        - USENIX ATC 21
    - Elixir: Train a Large Language Model on a Small GPU Cluster [[Paper]](https://arxiv.org/pdf/2212.05339) [[Code]](https://github.com/hpcaitech/ColossalAI/tree/feature/elixir)
        - H. Huang et al.
    - Accelerating the Training of Large Language Models using Efficient Activation Rematerialization and Optimal Hybrid Parallelism [[Paper]](https://www.usenix.org/system/files/atc24-yuan.pdf)
        - T. Yuan et al. 
        - USENIX 2024
- **Dynamic Offloading**
    - TSPLIT: Fine-grained GPU Memory Management for Efficient DNN Training via Tensor Splitting [[Paper]](https://ieeexplore.ieee.org/document/9835178)
        - X. Nie et al.
        - ICDE 2022
    - PatrickStar: Parallel Training of Large Language Models via a Chunk-based Memory Management [[Paper]](https://arxiv.org/abs/2108.05818) [[Code]](https://github.com/Tencent/PatrickStar)
        - J. Fang
        - TPDS 2023
    - Mobius: Fine Tuning Large-Scale Models on Commodity GPU Servers [[Paper]](https://dl.acm.org/doi/10.1145/3575693.3575703)
        - Y. Feng
        - ASPLOS 2023
    - Harmony: Overcoming the Hurdles of GPU Memory Capacity to Train Massive DNN Models on Commodity Servers [[Paper]](https://arxiv.org/abs/2202.01306) 
        - Y. Li et al.
        - VLDB 2022
    - Tensor Movement Orchestration in Multi-GPU Training Systems [[Paper]](https://ieeexplore.ieee.org/document/10071043)
        - S. Lin et al.
        - HPCA 2023
    - STRONGHOLD: Fast and Affordable Billion-Scale Deep Learning Model Training [[Paper]](https://ieeexplore.ieee.org/document/10046110)
        - X. Sun et al.
        - SC 2022

### *SSD Offloading*

- ZeRO-Infinity: Breaking the GPU Memory Wall for Extreme Scale Deep Learning [[Paper]](https://arxiv.org/abs/2104.07857) [[Code]](https://github.com/microsoft/DeepSpeed)
    - S. Rajbhandari et al.
    - SC 2021
- Angel-PTM: A Scalable and Economical Large-scale Pre-training System in Tencent [[Paper]](https://arxiv.org/abs/2303.02868)
    - X Nie et al.
    - VLDB 2023
- Smart-Infinity: Fast Large Language Model Training using Near-Storage Processing on a Real System [[Paper]](https://arxiv.org/abs/2403.06664)
    - H. Jang et al.
    - HPCA 2024
- Adding NVMe SSDs to Enable and Accelerate 100B Model Fine-tuning on a Single GPU [[Paper]](https://arxiv.org/abs/2403.06504)
    - C. Liao et al.
- MoESys: A Distributed and Efficient Mixture-of-Experts Training and Inference System for Internet Services [[Paper]](https://ieeexplore.ieee.org/document/10528887)
    - D. Yu et al.
    - ICS 2024