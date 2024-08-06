# INFRASTRUCTURE FOR LLM TRAINING

## Introduction
We explore the infrastructure design for training LLMs, encompassing accelerators, networks, storage, and scheduling systems.

## Content 

- AI Accelerators
    - NVIDIA GPUs
    - Other AI Accelerators
- Network Infrastructure
    - Chip-to-Chip
    - Node-to-Node 
    - Network Topology
    - Load Balancing & Congestion Control (CC)
- Storage Systems
    - Checkpoint Storage
    - Training Data Storage
- Scheduling Systems
    - Workload Scheduling
    - Resource Scheduling

### AI Accelerators
#### NVIDIA GPUs

-  NVIDIA Ampere Architecture. [[Website](https://www.nvidia.com/en-us/data-center/ampere-architecture/)]

-  NVIDIA Hopper Architecture. [[Website](https://www.nvidia.com/en-us/data-center/technologies/hopper-architecture)]

- NVIDIA Blackwell Architecture. [[pdf](https://www.nvidia.com/en-us/data-center/technologies/blackwell-architecture)]

#### Other AI Accelerators

- Amd instinct tm mi250x accelerator enabled by elevated fanout bridge advanced packaging architecture [[pdf](https://ieeexplore.ieee.org/document/10185224)]
    - 2023 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits).
    - R. Swaminathan, M. J. Schulte, B. Wilkerson, G. H. Loh, A. Smith, N. James

- Gaudi training platform white paper [[White paper](https://www.intel.com/content/www/us/en/content-details/784830/gaudi-training-platform-white-paper.html)]
    - Habana

- Tpu v4: An optically reconfigurable supercomputer for machine learning with hardware support for embeddings [[pdf](https://dl.acm.org/doi/pdf/10.1145/3579371.3589350)]
    - Proceedings of the 50th Annual International Symposium on Computer Architecture, 2023
    - N. Jouppi, G. Kurian, S. Li, P. Ma, R. Nagarajan, L. Nai, N. Patil, S. Subramanian, A. Swing, B. Towles et al.

- A comprehensive performance study of large language models on novel ai accelerators [[pdf](https://arxiv.org/pdf/2310.04607)]
    - arXiv preprint arXiv:2310.04607, 2023
    - M. Emani, S. Foreman, V. Sastry, Z. Xie, S. Raskar, W. Arnold, R. Thakur, V. Vishwanath, and M. E. Papka

- The cerebras cs-2: Designing an ai accelerator around the world’s largest 2.6 trillion transistor chip [[pdf](https://dl.acm.org/doi/10.1145/3505170.3511036)]
    - Proceedings of the 2022 International Symposium on Physical Design, 2022
    - J.-P. Fricker

### Network Infrastructure
#### Chip-to-Chip

- Nvidia dgx-1 system architecture white paper [[White paper](https://images.nvidia.com/content/pdf/dgx1-system-architecture-whitepaper1.pdf)]

- 3.2 the a100 datacenter gpu and ampere architecture [[pdf](https://ieeexplore.ieee.org/document/9365803)]
    - 2021 IEEE International Solid-State Circuits Conference (ISSCC)
    - J. Choquette, E. Lee, R. Krashinsky, V. Balan, and B. Khailany

- 2.2 amd chiplet architecture for high-performance server and desktop products [[pdf](https://ieeexplore.ieee.org/document/9063103)]
    - 2020 IEEE International Solid-State Circuits Conference-(ISSCC)
    - S. Naffziger, K. Lepak, M. Paraschou, and M. Subramony

- A domain-specific supercomputer for training deep neural networks [[pdf](https://dl.acm.org/doi/pdf/10.1145/3360307)]
    - Communications of the ACM, vol. 63, no. 7, pp. 67–78, 2020.
    - N. P. Jouppi, D. H. Yoon, G. Kurian, S. Li, N. Patil, J. Laudon, C. Young, and D. Patterson

- Google’s training chips revealed: Tpuv2 and tpuv3 [[pdf](https://ieeexplore.ieee.org/document/9220735)]
    - Hot Chips Symposium, 2020
    - T. Norrie, N. Patil, D. H. Yoon, G. Kurian, S. Li, J. Laudon, C. Young, N. P. Jouppi, and D. A. Patterson

#### Node-to-Node

- The development of mellanox/nvidia gpudirect over infiniband—a new model for gpu to gpu communications [[pdf](https://pdfs.semanticscholar.org/677f/55089039398ad9f23288fd89e77ff8380de3.pdf)]
    - Computer Science-Research and Development, vol. 26, pp. 267–273, 2011
    - G. Shainer, A. Ayoub, P. Lui, T. Liu, M. Kagan, C. R. Trott, G. Scantlen, and P. S. Crozier

- An introduction to the infiniband architecture [[pdf](https://ieeexplore.ieee.org/document/5264600)]
    - High performance mass storage and parallel I/O, vol. 42, no. 617-632, p. 10, 2001.
    - G. F. Pfister

- Supplement to infiniband architecture specification volume 1 release 1.2.2 annex a16 [[pdf](https://www.infinibandta.org/wp-content/uploads/2022/07/IBTA-Overview-of-IBTA-Volume-1-Release-1.6-2022-07-15.pdf)]
    - Infiniband Trade Association

- Architectural Specifications for RDMA over TCP/IP [[Website](http://www.rdmaconsortium.org/)]
    - RDMA Consortium

#### Network Topology

- A study of non-blocking switching networks [[pdf](https://ieeexplore.ieee.org/document/6770468)]
    - Bell System Technical Journa
    - C. Clos

- Bcube: a high performance, server-centric network architecture for modular data centers [[pdf](http://ccr.sigcomm.org/online/files/p63.pdf)]
    - Proceedings of the ACM SIGCOMM 2009 conference on Data communication, 2009
    - Chuanxiong Guo, Guohan Lu, Dan Li, Haitao Wu, Xuan Zhang, Yunfeng Shi, Chen Tian, Yongguang Zhang, Songwu Lu

- Dcell: a scalable and fault-tolerant network structure for data centers [[pdf](https://dl.acm.org/doi/pdf/10.1145/1402958.1402968)]
    - Proceedings of the ACM SIGCOMM 2008 conference on Data communication, 2008
    - Chuanxiong Guo, Haitao Wu, Kun Tan, Lei Shi, Yongguang Zhang, Songwu Lu

- Jellyfish: Networking data centers randomly [[pdf](https://arxiv.org/pdf/1110.1687)]
    - 9th USENIX Symposium on Networked Systems Design and Implementation (NSDI 12)
    - A. Singla, C.-Y. Hong, L. Popa, and P. B. Godfrey
  
- Technology-driven, highly-scalable dragonfly topology [[pdf](https://ieeexplore.ieee.org/document/4556717)]
    - ACM SIGARCH Computer Architecture News
    - J. Kim, W. J. Dally, S. Scott, and D. Abts
  
- Dragonfly+: Low cost topology for scaling datacenters [[pdf](https://ieeexplore.ieee.org/document/7885210)]
    - 2017 IEEE 3rd International Workshop on High-Performance Interconnection Networks in the Exascale and Big-Data Era (HiPINEB)
    - A. Shpiner, Z. Haramaty, S. Eliad, V. Zdornov, B. Gafni, and E. Zahavi
  
- Doubling all2all performance with nvidia collective communication library 2.12 [[pdf](https://developer.nvidia.com/blog/nvswitch-leveraging-nvlink-to-maximum-effect/)]
    - K. Mandakolathur and S. Jeaugey

- Alibaba hpn: A data center network for large language model training [[pdf](https://ennanzhai.github.io/pub/sigcomm24-hpn.pdf)]
    - Proceedings of the ACM SIGCOMM 2024 Conference, 2024
    - Kun Qian, Yongqing Xi, Jiamin Cao, Jiaqi Gao, Yichi Xu, Yu Guan, Binzhang Fu, Xuemei Shi, Fangbo Zhu, Rui Miao, Chao Wang, Peng Wang, Pengcheng Zhang, Xianlong Zeng, Eddie Ruan, Zhiping Yao, Ennan Zhai, Dennis Cai

- Optimized network architectures for large language model training with billions of parameters [[pdf](https://arxiv.org/pdf/2307.12169v2)]
    - arXiv preprint arXiv:2307.12169
    - Weiyang Wang, Manya Ghobadi, Kayvon Shakeri, Ying Zhang, Naader Hasani

- Hammingmesh: a network topology for large-scale deep learning [[pdf](https://dl.acm.org/doi/abs/10.5555/3571885.3571899)]
    - SC22: International Conference for High Performance Computing, Networking, Storage and Analysis.
    - T. Hoefler, T. Bonato, D. De Sensi, S. Di Girolamo, S. Li, M. Heddes, J. Belk, D. Goel, M. Castro, and S. Scott
  
- Sip-ml: highbandwidth optical network interconnects for machine learning
training [[pdf](https://dl.acm.org/doi/10.1145/3452296.3472900)]
    - Proceedings of the 2021 ACM SIGCOMM 2021 Conference, 2021
    - M. Khani, M. Ghobadi, M. Alizadeh, Z. Zhu, M. Glick, K. Bergman, A. Vahdat, B. Klenk, and E. Ebrahimi

- {TopoOpt}: Co-optimizing network topology and parallelization strategy for distributed training jobs [[pdf](https://www.usenix.org/conference/nsdi23/presentation/wang-weiyang)]
    - 20th USENIX Symposium on Networked Systems Design and Implementation (NSDI 23)
    - Weiyang Wang, Moein Khazraee, Zhizhen Zhong, Manya Ghobadi, Zhihao Jia, Dheevatsa Mudigere, Ying Zhang, Anthony Kewitsch

#### Load Balancing & Congestion Control (CC)

- Analysis of an equal-cost multi-path algorithm [[pdf](https://www.rfc-editor.org/rfc/rfc2992.html)]
    - C. Hopps

- On the impact of packet spraying in data center networks [[pdf](https://ieeexplore.ieee.org/document/6567015)]
    - 2013 proceedings ieee infocom
    - A. Dixit, P. Prakash, Y. C. Hu, and R. R. Kompella

- Challenging the need for packet spraying in large-scale distributed training [[pdf](https://arxiv.org/pdf/2407.00550)]
    - arXiv preprint arXiv:2407.00550, 2024.
    - V. Addanki, P. Goyal, and I. Marinos

- {MegaScale}: Scaling large language model training to more than 10,000 {GPUs} [[pdf](https://www.usenix.org/system/files/nsdi24-jiang-ziheng.pdf)]
    - 21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24), 2024
    - Ziheng Jiang, Haibin Lin, Yinmin Zhong, Qi Huang, Yangrui Chen, Zhi Zhang, Yanghua Peng, Xiang Li, Cong Xie, Shibiao Nong, Yulu Jia, Sun He, Hongmin Chen, Zhihao Bai, Qi Hou, Shipeng Yan, Ding Zhou, Yiyao Sheng, Zhuo Jiang, Haohan Xu, Haoran Wei, Zhang Zhang, Pengfei Nie, Leqi Zou, Sida Zhao, Liang Xiang, Zherui Liu, Zhe Li, Xiaoying Jia, Jianxi Ye, Xin Jin, Xin Liu

- IEEE. 802.1qbb – priority-based flow control [[pdf](https://1.ieee802.org/dcb/802-1qbb)]

- Timely: Rtt-based congestion control for the datacenter [[pdf](https://dl.acm.org/doi/pdf/10.1145/2829988.2787510)]
    - ACM SIGCOMM Computer Communication Review
    - R. Mittal, V. T. Lam, N. Dukkipati, E. Blem, H. Wassel, M. Ghobadi, A. Vahdat, Y. Wang, D. Wetherall, and D. Zats

- Swift: Delay is simple and effective for congestion control in the datacenter [[pdf](https://dl.acm.org/doi/pdf/10.1145/3387514.3406591)]
    - Proceedings of the Annual conference of the ACM Special Interest Group on Data Communication on the applications, technologies, architectures, and protocols for computer communication, 2020
    - G. Kumar, N. Dukkipati, K. Jang, H. M. Wassel, X. Wu, B. Montazeri, Y. Wang, K. Springborn, C. Alfeld, M. Ryan et al

- Congestion control for large-scale rdma deployments [[pdf](https://conferences.sigcomm.org/sigcomm/2015/pdf/papers/p523.pdf)]
    - ACM SIGCOMM Computer Communication Review
    - Y. Zhu, H. Eran, D. Firestone, C. Guo, M. Lipshteyn, Y. Liron, J. Padhye, S. Raindel, M. H. Yahia, and M. Zhang

- Ecn or delay: Lessons learnt from analysis of dcqcn and timely [[pdf](https://dl.acm.org/doi/pdf/10.1145/2999572.2999593)]
    - Proceedings of the 12th International on Conference on emerging Networking EXperiments and Technologies
    - Y. Zhu, M. Ghobadi, V. Misra, and J. Padhye

- Hpcc: High precision congestion control [[pdf](https://dl.acm.org/doi/pdf/10.1145/3341302.3342085#:~:text=%EE%80%80Congestion%EE%80%81%20%EE%80%80control%EE%80%81%20%EE%80%80(CC)%EE%80%81%20%EE%80%80is%EE%80%81%20%EE%80%80the%EE%80%81)]
    - Proceedings of the ACM special interest group on data communication, 2019
    - Y. Li, R. Miao, H. H. Liu, Y. Zhuang, F. Feng, L. Tang, Z. Cao, M. Zhang, F. Kelly, M. Alizadeh et al.

- An edge-queued datagram service for all datacenter traffic [[pdf](https://www.usenix.org/system/files/nsdi22-paper-olteanu.pdf)]
    - 19th USENIX Symposium on Networked Systems Design and Implementation (NSDI 22)
    - V. Olteanu, H. Eran, D. Dumitrescu, A. Popa, C. Baciu, M. Silberstein, G. Nikolaidis, M. Handley, and C. Raiciu

- Rocc: robust congestion control for rdma [[pdf](https://dl.acm.org/doi/10.1145/3386367.3431316)]
    - Proceedings of the 16th International conference on emerging networking experiments and technologies, 2020
    - P. Taheri, D. Menikkumbura, E. Vanini, S. Fahmy, P. Eugster, and T. Edsall

- Mltcp: Congestion control for dnn training [[pdf](https://arxiv.org/pdf/2402.09589)]
    - arXiv preprint arXiv:2402.09589, 2024
    - Sudarsanan Rajasekaran, Sanjoli Narang, Anton A. Zabreyko, Manya Ghobadi

- {CASSINI}:{Network-Aware} job scheduling in machine learning clusters [[pdf](https://www.usenix.org/system/files/nsdi24-rajasekaran.pdf)]
    - 21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24)
    - S. Rajasekaran, M. Ghobadi, and A. Akella

- Towards {Domain-Specific} network transport for distributed {DNN} training[[pdf](https://www.usenix.org/system/files/nsdi24-wang-hao.pdf)]
    - 21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24)
    - H. Wang, H. Tian, J. Chen, X. Wan, J. Xia, G. Zeng, W. Bai, J. Jiang, Y. Wang, and K. Chen

### Storage Systems
#### Checkpoint Storage

- Facebook’s tectonic filesystem: Efficiency from exascale [[pdf](https://www.usenix.org/system/files/fast21-pan.pdf)]
    - 21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24)
    - S. Pan, T. Stavrinos, Y. Zhang, A. Sikaria, P. Zakharov, A. Sharma, M. Shuey, R. Wareing, M. Gangapuram, G. Cao et al.

- The hadoop distributed file system [[pdf](https://www.usenix.org/system/files/nsdi24-rajasekaran.pdf)]
    - 2010 IEEE 26th symposium on mass storage systems and technologies (MSST).
    - K. Shvachko, H. Kuang, S. Radia, and R. Chansler

- Ceph: A scalable, high-performance distributed file system [[pdf](https://dl.acm.org/doi/10.5555/1298455.1298485)]
    - Proceedings of the 7th Conference on Operating Systems Design and Implementation (OSDI’06)
    - S. Weil, S. A. Brandt, E. L. Miller, D. D. Long, and C. Maltzahn

#### Training Data Storage

- Lustre: Building a file system for 1000-node clusters [[pdf](https://www.kernel.org/doc/ols/2003/ols2003-pages-380-386.pdf)]
    - Proceedings of the 2003 Linux symposium
    - P. Schwan et al.

- {GPFS}: A {Shared-Disk} file system for large computing clusters [[pdf](https://www.usenix.org/legacy/publications/library/proceedings/fast02/full_papers/schmuck/schmuck.pdf)]
    - Conference on file and storage technologies (FAST 02)
    - F. Schmuck and R. Haskin

- I/o characterization and performance evaluation of beegfs for deep learning [[pdf](https://dl.acm.org/doi/pdf/10.1145/3337821.3337902)]
    - Proceedings of the 48th International Conference on Parallel Processing, 2019
    - F. Chowdhury, Y. Zhu, T. Heer, S. Paredes, A. Moody, R. Goldstone, K. Mohror, and W. Yu

- Tachyon: Reliable, memory speed storage for cluster computing frameworks [[pdf](https://dl.acm.org/doi/10.1145/2670979.2670985)]
    - Proceedings of the ACM Symposium on Cloud Computing, 2014
    - H. Li, A. Ghodsi, M. Zaharia, S. Shenker, and I. Stoica

- Juicefs: A High-Performance, Cloud-Native, Distributed File System [[Github](https://github.com/juicedata/juicefs)]
    - JuiceFS

- Quiver: An informed storage cache for deep learning [[pdf](https://www.usenix.org/system/files/fast20-kumar.pdf)]
    - 18th USENIX Conference on File and Storage Technologies (FAST 20), 2020
    - A. V. Kumar and M. Sivathanu

- Fluid: Dataset abstraction and elastic acceleration for cloud-native deep learning training jobs [[pdf](https://www.usenix.org/system/files/nsdi24-rajasekaran.pdf)]
    - 2022 IEEE 38th International Conference on Data Engineering (ICDE).
    - Rong Gu, Kai Zhang, Zhihao Xu, et al.

### Scheduling Systems
#### Workload Scheduling

- Tiresias: A {GPU} cluster manager for distributed deep learning [[pdf](https://www.usenix.org/system/files/nsdi19-gu.pdf)]
    - 16th USENIX Symposium on Networked Systems Design and Implementation (NSDI 19), 2019
    - J. Gu, M. Chowdhury, K. G. Shin, Y. Zhu, M. Jeon, J. Qian, H. Liu, and C. Guo

- Themis: Fair and efficient {GPU} cluster scheduling [[pdf](https://www.usenix.org/system/files/nsdi20-paper-mahajan.pdf)]
    - 17th USENIX Symposium on Networked Systems Design and Implementation (NSDI 20), 2020
    - K. Mahajan, A. Balasubramanian, A. Singhvi, S. Venkataraman, A. Akella, A. Phanishayee, and S. Chawla

- Elasticflow: An elastic serverless training platform for distributed deep learning [[pdf](https://dl.acm.org/doi/10.1145/3575693.3575721)]
    - Proceedings of the 28th ACM International Conference on Architectural Support for Programming Languages and Operating Systems, Volume 2, 2023
    - D. Gu, Y. Zhao, Y. Zhong, Y. Xiong, Z. Han, P. Cheng, F. Yang, G. Huang, X. Jin, and X. Liu
  
- Heterogeneity-Aware Cluster Scheduling Policies for Deep Learning Workloads [[pdf](https://www.usenix.org/system/files/osdi20-narayanan_deepak.pdf)]
    - 14th USENIX Symposium on Operating Systems Design and Implementation, ser. OSDI ’20. USENIX Association, 2020
    - D. Narayanan, K. Santhanam, F. Kazhamiaka, A. Phanishayee, and M. Zaharia

- Balancing efficiency and fairness in heterogeneous gpu clusters for deep learning [[pdf](https://dl.acm.org/doi/abs/10.1145/3342195.3387555)]
    - Proceedings of the Fifteenth European Conference on Computer Systems, ser. EuroSys ’20
    - S. Chaudhary, R. Ramjee, M. Sivathanu, N. Kwatra, and S. Viswanatha

- Beware of fragmentation: Scheduling GPUSharing workloads with fragmentation gradient descent [[pdf](https://www.usenix.org/system/files/atc23-weng.pdf)]
    - 2023 USENIX Annual Technical Conference, ser. USENIX ATC ’23
    - Q. Weng, L. Yang, Y. Yu, W. Wang, X. Tang, G. Yang, and L. Zhang

- Lucid: A nonintrusive, scalable and interpretable scheduler for deep learning training jobs [[pdf](https://dl.acm.org/doi/pdf/10.1145/3575693.3575705)]
    - Proceedings of the 28th ACM International Conference on Architectural Support for Programming Languages and Operating Systems
    - Q. Hu, M. Zhang, P. Sun, Y. Wen, and T. Zhang

- Pollux: Co-adaptive cluster scheduling for goodput-optimized deep learning [[pdf](https://www.usenix.org/system/files/osdi21-qiao.pdf)]
    - 15th USENIX Symposium on Operating Systems Design and Implementation, ser. OSDI ’21
    - A. Qiao, S. K. Choe, S. J. Subramanya, W. Neiswanger, Q. Ho, H. Zhang, G. R. Ganger, and E. P. Xing

- Sia: Heterogeneity-aware, goodput-optimized mlcluster scheduling [[pdf](https://dl.acm.org/doi/pdf/10.1145/3600006.3613175)]
    - Proceedings of the 29th Symposium on Operating Systems Principles, 2023
    - S. Jayaram Subramanya, D. Arfeen, S. Lin, A. Qiao, Z. Jia, and G. R. Ganger

- A codesign of scheduling and parallelization for large model training in heterogeneous clusters [[pdf](https://arxiv.org/pdf/2403.16125)]
    - arXiv preprint arXiv:2403.16125, 2024
    - Chunyu Xue, Weihao Cui, Han Zhao, Quan Chen, Shulai Zhang, Pengyu Yang, Jing Yang, Shaobo Li, Minyi Guo

- Hydro: Surrogate-Based hyperparameter tuning service in datacenter [[pdf](https://www.usenix.org/system/files/osdi23-hu.pdf)]
    - 17th USENIX Symposium on Operating Systems Design and Implementation, ser. OSDI ’23
    - Q. Hu, Z. Ye, M. Zhang, Q. Chen, P. Sun, Y. Wen, and T. Zhang

- Characterization of large language model development in the datacenter [[pdf](https://www.usenix.org/system/files/nsdi24-hu.pdf)]
    - 21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24)
    - Q. Hu, Z. Ye, Z. Wang, G. Wang, M. Zhang, Q. Chen, P. Sun, D. Lin, X. Wang, Y. Luo et al.
  
#### Resource Scheduling

- Switches for hire: Resource scheduling for data center in-network computing [[pdf](https://dl.acm.org/doi/pdf/10.1145/3445814.3446760)]
    - Proceedings of the 26th ACM International Conference on Architectural Support for Programming Languages and Operating Systems, 2021
    - M. Blocher, L. Wang, P. Eugster, and M. Schmidt

- Silod: A co-design of caching and scheduling for deep learning clusters [[pdf](https://dl.acm.org/doi/10.1145/3552326.3567499)]
    - Proceedings of the Eighteenth European Conference on Computer Systems, 2023
    - H. Zhao, Z. Han, Z. Yang, Q. Zhang, M. Li, F. Yang, Q. Zhang, B. Li, Y. Yang, L. Qiu et al

- Looking beyond {GPUs} for {DNN} scheduling on {Multi-Tenant} clusters [[pdf](https://www.usenix.org/system/files/osdi22-mohan.pdf)]
    - 16th USENIX Symposium on Operating Systems Design and Implementation (OSDI 22), 2022
    - J. Mohan, A. Phanishayee, J. Kulkarni, and V. Chidambaram

- {EnvPipe}: Performance-preserving {DNN} training framework for saving energy [[pdf](https://www.usenix.org/system/files/atc23-choi.pdf)]
    - 2023 USENIX Annual Technical Conference (USENIX ATC 23), 2023
    - S. Choi, I. Koo, J. Ahn, M. Jeon, and Y. Kwon

- Zeus: Understanding and Optimizing GPU Energy Consumption of DNN Training [[pdf](https://www.usenix.org/system/files/nsdi23-you.pdf)]
    - USENIX NSDI, 2023.
    - J. You, J.-W. Chung, and M. Chowdhury
  
- Perseus: Removing energy bloat from large model training [[pdf](https://arxiv.org/pdf/2312.06902)]
    - arXiv preprint arXiv:2312.06902, 2023.
    - Jae-Won Chung, Yile Gu, Insu Jang, Luoxi Meng, Nikhil Bansal, Mosharaf Chowdhury
