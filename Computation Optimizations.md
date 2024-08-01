# Computation Optimizations

## Introduction
Today’s AI accelerators offer unprecedented computational capabilities in terms of FLOPs. However, effectively utilizing these FLOPs to their full potential requires sophisticated optimization techniques. A brief summary of current research results on computing optimization is listed below.

## Content
- Systems and techniques of computation optimizations:
  - Operator Optimizations
    - Manually Optimizations
    - Automatic Optimizations
  - Mixed-precision Training
    - 16-Bit Floating Point
    - Sub-8-Bit Floating Point
    - Low-Bit Fixed Point

### Manually Optimizations
- FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness [[Paper]](https://arxiv.org/abs/2205.14135) [[GitHub]](https://github.com/Dao-AILab/flash-attention)
  - Tri Dao, Daniel Y. Fu, Stefano Ermon, Atri Rudra, Christopher Ré.
  - Advances in Neural Information Processing Systems, vol. 35, pp. 16 344–16 359, 2022.
- FlashAttention-2: Faster Attention with Better Parallelism and Work Partitioning [[Paper]](https://arxiv.org/abs/2307.08691) [[GitHub]](https://github.com/Dao-AILab/flash-attention)
  - Tri Dao 
  - arxiv:2307.08691, 2023.
- FlashAttention-3: Fast and Accurate Attention with Asynchrony and Low-precision [[Paper]](https://arxiv.org/abs/2407.08608) [[GitHub]](https://github.com/Dao-AILab/flash-attention)
  - Jay Shah, Ganesh Bikshandi, Ying Zhang, Vijay Thakkar, Pradeep Ramani, Tri Dao
  - arXiv preprint arXiv:2407.08608, 2024.
- Blockwise Parallel Transformer for Large Context Models [[Paper]](https://dl.acm.org/doi/abs/10.1007/s11227-024-05890-8) [[GitHub]](https://github.com/forhaoliu/ringattention)
  - Hao Liu, Pieter Abbeel
  - Advances in Neural Information Processing Systems, vol. 36, 2024.
- SWattention: designing fast and memory-efficient attention for a new Sunway Supercomputer [[Paper]](https://arxiv.org/abs/2407.08608) [[GitHub]](https://github.com/Dao-AILab/flash-attention)
  - Ruohan Wu, Xianyu Zhu, Junshi Chen, Sha Liu, Tianyu Zheng, Xin Liu, Hong An
  - The Journal of Supercomputing, pp. 1–24, 2024.
- A Case Study in CUDA Kernel Fusion: Implementing FlashAttention-2 on NVIDIA Hopper Architecture using the CUTLASS Library [[Paper]](https://arxiv.org/abs/2312.11918) [[GitHub]](https://github.com/ColfaxResearch/cutlass-kernels/tree/master/src/fmha)
  - Ganesh Bikshandi, Jay Shah
  - arXiv preprint arXiv:2312.11918, 2023.
- Bytetransformer: A high-performance transformer boosted for variable-length inputs [[Paper]](https://arxiv.org/abs/2210.03052) [[GitHub]](https://github.com/bytedance/ByteTransformer)
  - Yujia Zhai, Chengquan Jiang, Leyuan Wang, Xiaoying Jia, Shang Zhang, Zizhong Chen, Xin Liu, Yibo Zhu
  - 2023 IEEE International Parallel and Distributed Processing Symposium (IPDPS). IEEE, 2023, pp. 344–355.

### Automatic Optimizations
- Halide: a language and compiler for optimizing parallelism, locality, and recomputation in image processing pipelines [[Paper]](https://dl.acm.org/doi/10.1145/2491956.2462176)
  - Jonathan Ragan-Kelley, Connelly Barnes, Andrew Adams, Sylvain Paris, Frédo Durand, Saman Amarasinghe.
  - Acm Sigplan Notices, vol. 48, no. 6, pp. 519–530, 2013.
- TVM: An Automated End-to-End Optimizing Compiler for Deep Learning
 [[Paper]](https://arxiv.org/abs/1802.04799)
  - Tianqi Chen, Thierry Moreau, Ziheng Jiang, Lianmin Zheng, Eddie Yan, Meghan Cowan, Haichen Shen, Leyuan Wang, Yuwei Hu, Luis Ceze, Carlos Guestrin, Arvind Krishnamurthy
  - 13th USENIX Symposium on Operating Systems Design and Implementation (OSDI 18), 2018, pp. 578–594.
- ROLLER: Fast and Efficient Tensor Compilation for Deep Learning [[Paper]](https://www.usenix.org/system/files/osdi22-zhu.pdf)
  - H. Zhu, R. Wu, Y. Diao, S. Ke, H. Li, C. Zhang, J. Xue, L. Ma, Y. Xia, W. Cui et al.
  - 16th USENIX Symposium on Operating Systems Design and Implementation (OSDI 22), 2022, pp. 233–248.
- Triton: an intermediate language and compiler for tiled neural network computations [[Paper]](https://www.eecs.harvard.edu/~htk/publication/2019-mapl-tillet-kung-cox.pdf)
  - P. Tillet, H.-T. Kung, and D. Cox
  - in Proceedings of the 3rd ACM SIGPLAN International Workshop on Machine Learning and Programming Languages, 2019, pp. 10–19.
- Alcop: Automatic load-compute pipelining in deep learning compiler for ai-gpus [[Paper]](https://arxiv.org/abs/2210.16691)[[Github]](https://github.com/hgyhungry/alcop-artifact)
  - G. Huang, Y. Bai, L. Liu, Y. Wang, B. Yu, Y. Ding, and Y. Xie
  - Proceedings of Machine Learning and Systems, vol. 5, 2023.
- Chimera: An analytical optimizing framework for effective compute-intensive operators fusion [[Paper]](https://ieeexplore.ieee.org/abstract/document/10071018)
  - S. Zheng, S. Chen, P. Song, R. Chen, X. Li, S. Yan, D. Lin, J. Leng, and Y. Liang
  - 2023 IEEE International Symposium on High-Performance Computer Architecture (HPCA). IEEE, 2023, pp. 1113–1126.
- Welder: Scheduling deep learning memory access via tile-graph [[Paper]](https://www.usenix.org/system/files/osdi23-shi.pdf)[[Github]](https://github.com/microsoft/nnfusion/tree/osdi2023welder)
  - Y. Shi, Z. Yang, J. Xue, L. Ma, Y. Xia, Z. Miao, Y. Guo, F. Yang, and L. Zhou
  - 17th USENIX Symposium on Operating Systems Design and Implementation (OSDI 23), 2023, pp. 701–718.
- Pytorch 2: Faster machine learning through dynamic python bytecode transformation and graph compilation [[Paper]](https://dl.acm.org/doi/pdf/10.1145/3620665.3640366)[[Github]](https://github.com/pytorch/pytorch/)
  - J. Ansel, E. Yang, H. He, N. Gimelshein, A. Jain, M. Voznesensky, B. Bao, P. Bell, D. Berard, E. Burovski et al.
  - in Proceedings of the 29th ACM International Conference on Architectural Support for Programming Languages and Operating Systems, Volume 2, 2024, pp. 929–947.
- Jit-q: Justin-time quantization with processing-in-memory for efficient ml training [[Paper]](https://arxiv.org/pdf/2311.05034)
  - M. Ibrahim, S. Aga, A. Li, S. Pati, and M. Islam
  - Proceedings of Machine Learning and Systems, vol. 6, pp. 46–59, 2024.

### 16-Bit Floating Point
- Mixed Precision Training
 [[Paper]](https://arxiv.org/abs/1710.03740)
  - P. Micikevicius, S. Narang, J. Alben, G. Diamos, E. Elsen, D. Garcia, B. Ginsburg, M. Houston, O. Kuchaiev, G. Venkatesh et al.
  - arXiv preprint arXiv:1710.03740, 2017.
- Campo:Cost-Aware performance optimization for Mixed-Precision neural network training [[Paper]](https://www.usenix.org/system/files/atc22-he.pdf)
  - X. He, J. Sun, H. Chen, and D. Li
  - 2022 USENIX Annual Technical Conference (USENIX ATC 22), 2022, pp. 505–518.
- A study of bfloat16 for deep learning training [[Paper]](https://arxiv.org/abs/1905.12322)
  - D. Kalamkar, D. Mudigere, N. Mellempudi, D. Das, K. Banerjee, S. Avancha, D. T. Vooturi, N. Jammalamadaka, J. Huang, H. Yuen et al.
  - arXiv preprint arXiv:1905.12322, 2019.
- THC: Accelerating distributed deep learning using tensor homomorphic compression [[Paper]](https://arxiv.org/abs/2302.08545)[[Github]](https://github.com/SophiaLi06/BytePS_THC)
  - M. Li, R. B. Basat, S. Vargaftik, C. Lao, K. Xu, M. Mitzenmacher, and M. Yu
  - 21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24), 2024,

### Sub-8-Bit Floating Point
- Training deep neural networks with 8-bit floating point numbers [[Paper]](https://arxiv.org/abs/1812.08011)
  - N. Wang, J. Choi, D. Brand, C.-Y. Chen, and K. Gopalakrishnan
  - Advances in neural information processing systems, vol. 31, 2018.
- Hybrid 8-bit floating point (hfp8) training and inference for deep neural networks [[Paper]](https://dl.acm.org/doi/pdf/10.5555/3454287.3454728)
  - X. Sun, J. Choi, C.-Y. Chen, N. Wang, S. Venkataramani, V. V. Srinivasan, X. Cui, W. Zhang, and K. Gopalakrishnan
  - Advances in neural information processing systems, vol. 32, 2019.
- Fp8-lm: Training fp8 large language models [[Paper]](https://arxiv.org/abs/2310.18313)
  - H. Peng, K. Wu, Y. Wei, G. Zhao, Y. Yang, Z. Liu, Y. Xiong, Z. Yang, B. Ni, J. Hu et al.
  - arXiv preprint arXiv:2310.18313, 2023.
  
### Low-Bit Fixed Point
- Jetfire: Efficient and accurate transformer pretraining with int8 data flow and per-block quantization [[Paper]](https://arxiv.org/abs/2403.12422)[[Github]](https://github.com/thu-ml/Jetfire-INT8Training)
  - H. Xi, Y. Chen, K. Zhao, K. Zheng, J. Chen, and J. Zhu
  - arXiv preprint arXiv:2403.12422, 2024.
- Training transformers with 4-bit integers [[Paper]](https://arxiv.org/pdf/2306.11987)[[Github]](https://github.com/xijiu9/Train_Transformers_with_INT4)
  - H. Xi, C. Li, J. Chen, and J. Zhu
  - Advances in Neural Information Processing Systems, vol. 36, pp. 49 146–49 168, 2023.
- Bitnet: Scaling 1-bit transformers for large language models [[Paper]](https://arxiv.org/pdf/2310.11453)
  - H. Wang, S. Ma, L. Dong, S. Huang, H. Wang, L. Ma, F. Yang, R. Wang, Y. Wu, and F. Wei
  - arXiv preprint arXiv:2310.11453, 2023.
- The era of 1-bit llms: All large language models are in 1.58 bits [[Paper]](https://arxiv.org/abs/2402.17764)
  - S. Ma, H. Wang, L. Ma, L. Wang, W. Wang, S. Huang, L. Dong, R. Wang, J. Xue, and F. Wei
  - arXiv preprint arXiv:2402.17764, 2024.