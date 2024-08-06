# Fault Tolerance

## Introduction
LLM training involves extended periods and extensive GPU clusters, necessitating robust fault tolerance mechanisms due to the system's synchronous nature. A single point of failure can suspend the training process. Analyzing failure modes in LLM training is crucial, followed by investigating methods for rapid failure detection and recovery. Ensuring reliable training processes involves addressing both the underlying infrastructure and training system optimizations. The following is a summary of the literature on this subject.

## Content
- Anomaly Detection
    - Statistical Monitoring
    - Proactive Validation

- Checkpointing-Based Recovery
    - Persistent Checkpointing
    - In-Memory Checkpointing

- Checkpointing-Free Recovery
    - Live Migration
    - Module Redundancy

### Statistical Monitoring
- Resiliency at Scale: Managing Google’s TPUv4 Machine Learning Supercomputer [[Paper]](https://www.usenix.org/conference/nsdi24/presentation/zu)
    - Yazhou Zu, Alireza Ghaffarkhah, Hoang-Vu Dang, Brian Towles, Steven Hand, Safeen Huda, Adekunle Bello, Alexander Kolbasov, Arash Rezaei, Dayou Du, Steve Lacy, Hang Wang, Aaron Wisner, Chris Lewis, Henri Bahini
    - 21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24). 2024: 761-774.
- MegaScale: Scaling Large Language Model Training to More Than 10,000 GPUs [[Paper]](https://www.usenix.org/conference/nsdi24/presentation/jiang-ziheng)[[Github]](https://github.com/volcengine/veScale)
    - Ziheng Jiang and Haibin Lin, ByteDance; Yinmin Zhong, Peking University; Qi Huang, Yangrui Chen, Zhi Zhang, Yanghua Peng, Xiang Li, Cong Xie, Shibiao Nong, Yulu Jia, Sun He, Hongmin Chen, Zhihao Bai, Qi Hou, Shipeng Yan, Ding Zhou, Yiyao Sheng, Zhuo Jiang, Haohan Xu, Haoran Wei, Zhang Zhang, Pengfei Nie, Leqi Zou, Sida Zhao, Liang Xiang, Zherui Liu, Zhe Li, Xiaoying Jia, and Jianxi Ye, ByteDance; Xin Jin, Peking University; Xin Liu, ByteDance
    - 21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24). 2024: 745-760.
- Boosting Large-scale Parallel Training Efficiency with C4: A Communication-Driven Approach [[Paper]](https://arxiv.org/abs/2406.04594)
    - Jianbo Dong, Bin Luo, Jun Zhang, Pengcheng Zhang, Fei Feng, Yikai Zhu, Ang Liu, Zian Chen, Yi Shi, Hairong Jiao, Gang Lu, Yu Guan, Ennan Zhai, Wencong Xiao, Hanyu Zhao, Man Yuan, Siran Yang, Xiang Li, Jiamang Wang, Rui Men, Jianwei Zhang, Huang Zhong, Dennis Cai, Yuan Xie, Binzhang Fu
    - arXiv preprint arXiv:2406.04594, 2024.
- The infrastructure powering IBM's Gen AI model development [[Paper]](https://arxiv.org/abs/2407.05467)
    - T. Gershon, S. Seelam, B. Belgodere, M. Bonilla, L. Hoang, D. Barnett, I. Chung, A. Mohan, M.-H. Chen, L. Luo et al.
    - arXiv preprint arXiv:2407.05467, 2024.
- Unicron: Economizing Self-Healing LLM Training at Scale [[Paper]](https://arxiv.org/abs/2401.00134)
    - Tao He, Xue Li, Zhibin Wang, Kun Qian, Jingbo Xu, Wenyuan Yu, Jingren Zhou
    - arXiv preprint arXiv:2401.00134, 2023.
- TRANSOM: An Efficient Fault-Tolerant System for Training LLMs [[Paper]](https://arxiv.org/abs/2310.10046)
    - Baodong Wu, Lei Xia, Qingping Li, Kangyu Li, Xu Chen, Yongqiang Guo, Tieyao Xiang, Yuheng Chen, Shigang Li
    - arXiv preprint arXiv:2310.10046, 2023.
- The Llama 3 Herd of Models [[Paper]](https://ai.meta.com/research/publications/the-llama-3-herd-of-models/)[[Website]](https://llama.meta.com/)
    - Llama team
- Pytorch 2: Faster machine learning through dynamic python bytecode transformation and graph compilation [[Paper]](https://dl.acm.org/doi/abs/10.1145/3620665.3640366)[[Github]](https://github.com/pytorch/pytorch/)
    - Jason Ansel, Edward Yang, Horace He, Natalia Gimelshein, Animesh Jain, Michael Voznesensky, Bin Bao, Peter Bell, David Berard, Evgeni Burovski et al.
    - Proceedings of the 29th ACM International Conference on Architectural Support for Programming Languages and Operating Systems, Volume 2. 2024: 929-947.

### Proactive Validation
- MegaScale: Scaling Large Language Model Training to More Than 10,000 GPUs [[Paper]](https://www.usenix.org/conference/nsdi24/presentation/jiang-ziheng)[[Github]](https://github.com/volcengine/veScale)
    - Ziheng Jiang and Haibin Lin, ByteDance; Yinmin Zhong, Peking University; Qi Huang, Yangrui Chen, Zhi Zhang, Yanghua Peng, Xiang Li, Cong Xie, Shibiao Nong, Yulu Jia, Sun He, Hongmin Chen, Zhihao Bai, Qi Hou, Shipeng Yan, Ding Zhou, Yiyao Sheng, Zhuo Jiang, Haohan Xu, Haoran Wei, Zhang Zhang, Pengfei Nie, Leqi Zou, Sida Zhao, Liang Xiang, Zherui Liu, Zhe Li, Xiaoying Jia, and Jianxi Ye, ByteDance; Xin Jin, Peking University; Xin Liu, ByteDance
    - 21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24). 2024: 745-760.
- Superbench: Improving cloud ai infrastructure reliability with proactive validation [[Paper]](https://www.usenix.org/conference/atc24/presentation/xiong)[[Github]](https://github.com/microsoft/superbenchmark)
    - Yifan Xiong, Yuting Jiang, Ziyue Yang, and Lei Qu, Microsoft Research; Guoshuai Zhao, Shuguang Liu, Dong Zhong, Boris Pinzur, Jie Zhang, Yang Wang, Jithin Jose, Hossein Pourreza, Jeff Baxter, Kushal Datta, Prabhat Ram, Luke Melton, and Joe Chau, Microsoft; Peng Cheng, Yongqiang Xiong, and Lidong Zhou, Microsoft Research
    - 2024 USENIX Annual Technical Conference (USENIX ATC 24). 2024: 835-850.
- The infrastructure powering IBM's Gen AI model development [[Paper]](https://arxiv.org/abs/2407.05467)
    - T. Gershon, S. Seelam, B. Belgodere, M. Bonilla, L. Hoang, D. Barnett, I. Chung, A. Mohan, M.-H. Chen, L. Luo et al.
    - arXiv preprint arXiv:2407.05467, 2024.
- Resiliency at Scale: Managing Google’s TPUv4 Machine Learning Supercomputer [[Paper]](https://www.usenix.org/conference/nsdi24/presentation/zu)
    - Yazhou Zu, Alireza Ghaffarkhah, Hoang-Vu Dang, Brian Towles, Steven Hand, Safeen Huda, Adekunle Bello, Alexander Kolbasov, Arash Rezaei, Dayou Du, Steve Lacy, Hang Wang, Aaron Wisner, Chris Lewis, and Henri Bahini, Google
    - 21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24). 2024: 761-774.

### Persistent Checkpointing
#### Synchronous
- Deepspeed: System optimizations enable training deep learning models with over 100 billion parameters [[Paper]](https://dl.acm.org/doi/abs/10.1145/3394486.3406703)[[Github]](https://github.com/microsoft/DeepSpeed)
    - Jeff Rasley, Samyam Rajbhandari, Olatunji Ruwase, Yuxiong He
    - Proceedings of the 26th ACM SIGKDD International Conference on Knowledge Discovery & Data Mining. 2020: 3505-3506.
- Varuna: scalable, low-cost training of massive deep learning models [[Paper]](https://dl.acm.org/doi/abs/10.1145/3492321.3519584)[[Github]](https://github.com/microsoft/varuna)
    - Sanjith Athlur, Nitika Saran, Muthian Sivathanu, Ramachandran Ramjee, Nipun Kwatra
    - Proceedings of the Seventeenth European Conference on Computer Systems. 2022: 472-487.
- Just-in-time checkpointing: Low cost error recovery from deep learning training failures [[Paper]](https://dl.acm.org/doi/abs/10.1145/3627703.3650085)
    - Tanmaey Gupta, Sanjeev Krishnan, Rituraj Kumar, Abhishek Vijeev, Bhargav Gulavani, Nipun Kwatra, Ramachandran Ramjee, Muthian Sivathanu
    - Proceedings of the Nineteenth European Conference on Computer Systems. 2024: 1110-1125.
- DLRover-RM: Resource Optimization for Deep Recommendation Models Training in the Cloud [[Paper]](https://arxiv.org/abs/2304.01468)[[Github]](https://github.com/intelligent-machine-learning/dlrover)
    - Qinlong Wang, Tingfeng Lan, Yinghao Tang, Ziling Huang, Yiheng Du, Haitao Zhang, Jian Sha, Hui Lu, Yuanchun Zhou, Ke Zhang, Mingjie Tang
    - arXiv preprint arXiv:2304.01468, 2023.
- Universal checkpointing: Efficient and flexible checkpointing for large scale distributed training [[Paper]](https://arxiv.org/abs/2406.18820)[[Github]](https://github.com/microsoft/DeepSpeed)
    - Xinyu Lian, Sam Ade Jacobs, Lev Kurilenko, Masahiro Tanaka, Stas Bekman, Olatunji Ruwase, Minjia Zhang
    - arXiv preprint arXiv:2406.18820, 2024.
#### Snapshot-Stall
- Check-N-Run: a Checkpointing System for Training Deep Learning Recommendation Models [[Paper]](https://www.usenix.org/conference/nsdi22/presentation/eisenman)
    - Assaf Eisenman, Kiran Kumar Matam, Steven Ingram, Dheevatsa Mudigere, Raghuraman Krishnamoorthi, Krishnakumar Nair, and Misha Smelyanskiy, Facebook; Murali Annavaram, Facebook and USC
    - 19th USENIX Symposium on Networked Systems Design and Implementation (NSDI 22). 2022: 929-943.
- Torchsnapshor: A performant, memory-efficient checkpointing library for pytorch applications, designed with large, complex distributed workloads in mind [[Github]](https: //github.com/pytorch/torchsnapshot)
#### Asynchronous
- Deepfreeze: Towards scalable asynchronous checkpointing of deep learning models [[Paper]](https://ieeexplore.ieee.org/abstract/document/9139666)
    - Bogdan Nicolae, Jiali Li, Justin M Wozniak, George Bosilca, Matthieu Dorier, Franck Cappello
    - 2020 20th IEEE/ACM International Symposium on Cluster, Cloud and Internet Computing (CCGRID). IEEE, 2020: 172-181.
- CheckFreq: Frequent, Fine-Grained DNN Checkpointing [[Paper]](https://www.usenix.org/conference/fast21/presentation/mohan)
    - Jayashree Mohan, UT Austin; Amar Phanishayee, Microsoft Research; Vijay Chidambaram, UT Austin and VMware research
    - 19th USENIX Conference on File and Storage Technologies (FAST 21). 2021: 203-216.
- A Cost-Efficient Failure-Tolerant Scheme for Distributed DNN Training [[Paper]](https://ieeexplore.ieee.org/abstract/document/10361018)[[Github]]( https://github.com/LighT-chenml/LightCheck.git)
    - Menglei Chen, Yu Hua, Rong Bai, Jianming Huang
    - 2023 IEEE 41st International Conference on Computer Design (ICCD). IEEE, 2023: 150-157.
- Datastates-llm: Lazy asynchronous checkpointing for large language models [[Paper]](https://arxiv.org/abs/2406.10707)[[Github]](https://github.com/DataStates/datastates-llm)
    - Avinash Maurya, Robert Underwood, M. Mustafa Rafique, Franck Cappello, Bogdan Nicolae
    - arXiv preprint arXiv:2406.10707, 2024.
- Fastpersist: Accelerating model checkpointing in deep learning [[Paper]](https://arxiv.org/abs/2406.13768)
    - Guanhua Wang, Olatunji Ruwase, Bing Xie, Yuxiong He
    - arXiv preprint arXiv:2406.13768, 2024.
### In-Memory Checkpointing
- GEMINI: Fast Failure Recovery in Distributed Training with In-Memory Checkpoints [[Paper]](https://www.cs.rice.edu/~eugeneng/papers/SOSP23.pdf)
    - Zhuang Wang, Zhen Jia, Shuai Zheng, Zhen Zhang, Xinwei Fu, T. S. Eugene Ng, Yida Wang
    - Proceedings of the 29th Symposium on Operating Systems Principles. 2023: 364-381.
- Fault-Tolerant Hybrid-Parallel Training at Scale with Reliable and Efficient In-memory Checkpointing [[Paper]](https://arxiv.org/abs/2310.12670)
    - Yuxin Wang, Shaohuai Shi, Xin He, Zhenheng Tang, Xinglin Pan, Yang Zheng, Xiaoyu Wu, Amelie Chi Zhou, Bingsheng He, Xiaowen Chu
    - arXiv preprint arXiv:2310.12670, 2023.
### Live Migration
- Parcae: Proactive, Liveput-Optimized DNN Training on Preemptible Instances [[Paper]](https://www.usenix.org/conference/nsdi24/presentation/duan)
    - Jiangfei Duan, The Chinese University of Hong Kong; Ziang Song, ByteDance; Xupeng Miao and Xiaoli Xi, Carnegie Mellon University; Dahua Lin, The Chinese University of Hong Kong; Harry Xu, University of California, Los Angeles; Minjia Zhang, Microsoft; Zhihao Jia, Carnegie Mellon University
    - 21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24). 2024: 1121-1139.
- Oobleck: Resilient Distributed Training of Large Models Using Pipeline Templates [[Paper]](https://dl.acm.org/doi/abs/10.1145/3600006.3613152)[[Github]](https://github.com/SymbioticLab/Oobleck)
    - Insu Jang, Zhenning Yang, Zhen Zhang, Xin Jin, Mosharaf Chowdhury
    - Proceedings of the 29th Symposium on Operating Systems Principles. 2023: 382-395.
### Module Redundancy
- Bamboo: Making Preemptible Instances Resilient for Affordable Training of Large DNNs [[Paper]](https://www.usenix.org/conference/nsdi23/presentation/thorpe)[[Github]](https://github.com/uclasystem/bamboo)
    - John Thorpe, Pengzhan Zhao, Jonathan Eyolfson, and Yifan Qiao, UCLA; Zhihao Jia, CMU; Minjia Zhang, Microsoft Research; Ravi Netravali, Princeton University; Guoqing Harry Xu, UCLA
    - 20th USENIX Symposium on Networked Systems Design and Implementation (NSDI 23). 2023: 497-513.
- SlipStream: Adapting Pipelines for Distributed Training of Large DNNs Amid Failures [[Paper]](https://arxiv.org/abs/2405.14009)
    - Swapnil Gandhi, Mark Zhao, Athinagoras Skiadopoulos, Christos Kozyrakis
    - arXiv preprint arXiv:2405.14009, 2024.
- SWARM Parallelism: Training Large Models Can Be Surprisingly Communication-Efficient [[Paper]](https://proceedings.mlr.press/v202/ryabinin23a)[[Github]](https://github.com/yandex-research/swarm)
    - Max Ryabinin, Tim Dettmers, Michael Diskin, Alexander Borzunovs
    - Proceedings of the 40th International Conference on Machine Learning, PMLR 202:29416-29440, 2023.
