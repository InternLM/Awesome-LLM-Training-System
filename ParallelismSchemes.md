 # Training System


## Hybird Parallelism 
### Data Parallelism

- PyTorch\-DDP: Pytorch distributed: Experiences on accelerating data parallel training [[pdf]](https://arxiv.org/pdf/2006.15704) [[GitHub]]()
    - arXiv preprint arXiv:2006.15704, 2020.
    - Shen Li, Yanli Zhao, Rohan Varma, Omkar Salpekar, Pieter Noordhuis, Teng Li, Adam Paszke, Jeff Smith, Brian Vaughan, Pritam Damania, Soumith Chintala

- Horovod: fast and easy distributed deep learning in tensorflow [[pdf](https://arxiv.org/abs/1802.05799)]
    - arXiv preprint arXiv:1802.05799
    - Alexander Sergeev, Mike Del Balso

- Automatic cross-replica sharding of weight update in data-parallel training [[pdf](https://arxiv.org/abs/1802.05799)]
    - arXiv preprint arXiv:2004.13336, 2020.
    - Yuanzhong Xu, HyoukJoong Lee, Dehao Chen, Hongjun Choi, Blake Hechtman, Shibo Wang

- Zero: Memory optimizations toward training trillion parameter models [[pdf](https://arxiv.org/abs/1910.02054)]
    - SC20: International Conference for High Performance Computing, Networking, Storage and Analysis. IEEE, 2020, pp. 1–16.
    - Samyam Rajbhandari, Jeff Rasley, Olatunji Ruwase, Yuxiong He

- PyTorch FSDP: Experiences on Scaling Fully Sharded Data Parallel  [[pdf](https://arxiv.org/abs/2304.11277)]
    - Proceedings of the VLDB Endowment, vol. 16, no. 12, pp. 3848–3860, 2023
    - Yanli Zhao, Andrew Gu, Rohan Varma, Liang Luo, Chien-Chin Huang, Min Xu, Less Wright, Hamid Shojanazeri, Myle Ott, Sam Shleifer, Alban Desmaison, Can Balioglu, Pritam Damania, Bernard Nguyen, Geeta Chauhan, Yuchen Hao, Ajit Mathews, Shen Li

- Mics: Near-linear scaling for training gigantic model on public [[pdf](https://arxiv.org/abs/2205.00119)]
    - Proceedings of the VLDB Endowment, vol. 16, no. 1, pp. 37–50, 2022.
    - Zhen Zhang, Shuai Zheng, Yida Wang, Justin Chiu, George Karypis, Trishul Chilimbi, Mu Li, Xin Jin


### Tensor Parallelism
- Megatron-lm: Training multi-billion parameter language models using model parallelism [[pdf](https://arxiv.org/abs/1909.08053)]
    - arXiv preprint arXiv:1909.08053, 2019
    - Mohammad Shoeybi, Mostofa Patwary, Raul Puri, Patrick LeGresley, Jared Casper, Bryan Catanzaro

- An efficient 2d method for training superlarge deep learning models [[pdf](https://arxiv.org/abs/2104.05343)]
    - 2023 IEEE International Parallel and Distributed Processing Symposium (IPDPS)
    - Qifan Xu, Shenggui Li, Chaoyu Gong, Yang You

- Tesseract: Parallelize the Tensor Parallelism Efficiently [[pdf](https://arxiv.org/abs/2105.14500)]
    - in Proceedings of the 51st International Conference on Parallel Processing, 2022
    - Boxiang Wang, Qifan Xu, Zhengda Bian, Yang You

- Maximizing parallelism in distributed training for huge neural networks [[pdf](https://arxiv.org/abs/2105.144500)]
    - arXiv preprint arXiv:2105.14450, 2021
    - Zhengda Bian, Qifan Xu, Boxiang Wang, Yang You


### Pipeline Parallelism
- Gpipe: Efficient training of giant neural networks using pipeline parallelism [[pdf](https://arxiv.org/abs/1811.06965)]
    - Advances in neural information processing systems
    - Yanping Huang, Youlong Cheng, Ankur Bapna, Orhan Firat, Mia Xu Chen, Dehao Chen, HyoukJoong Lee, Jiquan Ngiam, Quoc V. Le, Yonghui Wu, Zhifeng Chen

- Pipedream: generalized pipeline parallelism for dnn training [[pdf](https://arxiv.org/abs/1806.03377)]
    - Proceedings of the 27th ACM symposium on operating systems principles
    - Aaron Harlap, Deepak Narayanan, Amar Phanishayee, Vivek Seshadri, Nikhil Devanur, Greg Ganger, Phil Gibbons

- Dapple: A pipelined data parallel approach for training large models [[pdf](https://arxiv.org/abs/2007.01045)]
    - Proceedings of the 26th ACM SIGPLAN Symposium on Principles and Practice of Parallel Programming, 2021, pp. 431–445.
    - Shiqing Fan, Yi Rong, Chen Meng, Zongyan Cao, Siyu Wang, Zhen Zheng, Chuan Wu, Guoping Long, Jun Yang, Lixue Xia, Lansong Diao, Xiaoyong Liu, Wei Lin

- Efficient large-scale language model training on gpu clusters using megatron-lm [[pdf](https://arxiv.org/abs/2104.04473)]
    - Proceedings of the International Conference for High Performance Computing, Networking, Storage and Analysis, 2021, pp. 1–15.
    - Deepak Narayanan, Mohammad Shoeybi, Jared Casper, Patrick LeGresley, Mostofa Patwary, Vijay Anand Korthikanti, Dmitri Vainbrand, Prethvi Kashinkunti, Julie Bernauer, Bryan Catanzaro, Amar Phanishayee, Matei Zaharia

- Terapipe: Token-level pipeline parallelism for training largescale language models [[pdf](https://arxiv.org/abs/2102.07988)]
    - International Conference on Machine Learning. PMLR, 2021, pp. 6543–6552.
    - Zhuohan Li, Siyuan Zhuang, Shiyuan Guo, Danyang Zhuo, Hao Zhang, Dawn Song, Ion Stoica

- Tessel: Boosting distributed execution of large dnn models via flexible schedule search [[pdf](https://arxiv.org/abs/2311.15269)] 
    - 2024 IEEE International Symposium on High-Performance Computer Architecture (HPCA)
    - Zhiqi Lin, Youshan Miao, Guanbin Xu, Cheng Li, Olli Saarikivi, Saeed Maleki, Fan Yang

- Zero Bubble Pipeline Parallelism [[pdf](https://arxiv.org/abs/2401.10241)] 
    - The Twelfth International Conference on Learning Representations
    - Penghui Qi, Xinyi Wan, Guangxing Huang, Min Lin

- Chimera: efficiently training large-scale neural networks with bidirectional pipelines [[pdf](https://arxiv.org/abs/2107.06925)] 
    - Proceedings of the International Conference for High Performance Computing
    - Shigang Li, Torsten Hoefler

- Hanayo: Harnessing wave-like pipeline parallelism for enhanced large model training efficiency [[pdf](https://arxiv.org/abs/2308.15762)] 
    - Proceedings of the International Conference for High Performance Computing, Networking, Storage and Analysis, 2023, pp. 1–13.
    - Ziming Liu, Shenggan Cheng, Haotian Zhou, Yang You

- Seq1f1b: Efficient sequence-level pipeline parallelism for large language model training [[pdf](https://arxiv.org/abs/2406.03488)] 
    - arXiv preprint arXiv:2406.03488, 2024.
    - Ao Sun, Weilin Zhao, Xu Han, Cheng Yang, Zhiyuan Liu, Chuan Shi, Maosong Sun

- Breadth-first pipeline parallelism [[pdf](https://arxiv.org/abs/2211.05953)] 
    - Proceedings of Machine Learning and Systems, vol. 5, 2023.
    - Joel Lamy-Poirier

- Dynapipe: Optimizing multi-task training through dynamic pipelines [[pdf](https://arxiv.org/abs/2311.10418)] 
    - Proceedings of the Nineteenth European Conference on Computer Systems, 2024, pp. 542–559.
    - Chenyu Jiang, Zhen Jia, Shuai Zheng, Yida Wang, Chuan Wu

- Distmm: Accelerating distributed multimodal model training [[pdf](https://www.usenix.org/conference/nsdi24/presentation/huang)] 
    - 21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24), 2024, pp. 1157–1171.
    - Jun Huang, Zhen Zhang, Shuai Zheng， Feng Qin,Yida Wang

- Graphpipe: Improving performance and scalability of dnn training with graph pipeline parallelism [[pdf](https://arxiv.org/abs/2406.17145)] 
    - arXiv preprint arXiv:2406.17145, 2024.
    - Byungsoo Jeon, Mengdi Wu, Shiyi Cao, Sunghyun Kim, Sunghyun Park, Neeraj Aggarwal, Colin Unger, Daiyaan Arfeen, Peiyuan Liao, Xupeng Miao, Mohammad Alizadeh, Gregory R. Ganger, Tianqi Chen, Zhihao Jia

- Bpipe: Memorybalanced pipeline parallelism for training large language models [[](https://proceedings.mlr.press/v202/kim23l/kim23l.pdf)] 
    - International Conference on Machine Learning. PMLR, 2023, pp. 16 639–16 653.
    - Taebum Kim, Hyoungjoo Kim, Gyeong-In Yu, Byung-Gon Chun

- Mpress: Democratizing billion-scale model training on multi-gpu servers via memory-saving inter-operator parallelism  [[pdf](https://ieeexplore.ieee.org/document/10071077)] 
    - 2023 IEEE International Symposium on High-Performance Computer Architecture (HPCA). IEEE, 2023, pp. 556–569.
    - Quan Zhou; Haiquan Wang; Xiaoyan Yu; Cheng Li

- mcap: Memorycentric partitioning for large-scale pipeline-parallel dnn training [[pdf](https://link.springer.com/chapter/10.1007/978-3-031-12597-3_10)] 
    - European Conference on Parallel Processing. Springer, 2022,pp. 155–170.
    - Henk Dreuning, Henri E. Bal & Rob V. van Nieuwpoort 

- Pipeline parallelism with controllable memory [[pdf](https://arxiv.org/abs/2405.15362)] 
    - arXiv preprint arXiv:2405.15362, 2024.
    - Penghui Qi, Xinyi Wan, Nyamdavaa Amar, Min Lin

- Varuna: scalable, low-cost training of massive deep learning models [[pdf](https://arxiv.org/abs/2111.04007)]
    - Proceedings of the Seventeenth European Conference on Computer Systems, 2022, pp. 472–487
    - Sanjith Athlur, Nitika Saran, Muthian Sivathanu, Ramachandran Ramjee, Nipun Kwatra

- Adapipe: Optimizing pipeline parallelism with adaptive recomputation and partitioning [[pdf](https://dl.acm.org/doi/10.1145/3620666.3651359)]
    - Proceedings of the 29th ACM International Conference on Architectural Support for Programming Languages and Operating Systems, Volume 3, 2024, pp. 86–100
    - Zhenbo Sun, Huanqi Cao, Yuanwei Wang, Guanyu Feng, Shengqi Chen, Haojie Wang, Wenguang ChenAuthors Info & Claims


### Sequence Parallelism

- Sequence parallelism: Long sequence training from system perspective [[pdf](https://arxiv.org/abs/2105.13120)]
    - Proceedings of the 61st Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers), 2023, pp. 2391–2404
    - Shenggui Li, Fuzhao Xue, Chaitanya Baranwal, Yongbin Li, Yang You

- Reducing activation recomputation in large transformer models [[pdf](https://arxiv.org/abs/2205.05198)]
    - Proceedings of Machine Learning and Systems, vol. 5, 2023.
    - Vijay Korthikanti, Jared Casper, Sangkug Lym, Lawrence McAfee, Michael Andersch, Mohammad Shoeybi, Bryan Catanzaro

- Usp: A unified sequence parallelism approach for long context generative ai [[pdf](https://arxiv.org/abs/2405.07719)]
    - arXiv preprint arXiv:2405.07719, 2024.
    - Jiarui Fang, Shangchun Zhao

- System optimizations for enabling training of extreme long sequence transformer models [[pdf](https://arxiv.org/abs/2309.14509)]
    - Proceedings of the 43rd ACM Symposium on Principles of Distributed Computing, 2024, pp. 121–130.
    - Sam Ade Jacobs, Masahiro Tanaka, Chengming Zhang, Minjia Zhang, Shuaiwen Leon Song, Samyam Rajbhandari, Yuxiong He

- Loongtrain: Efficient training of long-sequence llms with head-context parallelism [[pdf](https://arxiv.org/abs/2406.18485)]
    - arXiv preprint arXiv:2406.18485, 2024.
    - Diandian Gu, Peng Sun, Qinghao Hu, Ting Huang, Xun Chen, Yingtong Xiong, Guoteng Wang, Qiaoling Chen, Shangchun Zhao, Jiarui Fang, Yonggang Wen, Tianwei Zhang, Xin Jin, Xuanzhe Liu

- Ring attention with blockwise transformers for near-infinite context [[pdf](https://arxiv.org/abs/2310.01889)]
    - International Conference on Learning Representations(ICLR), 2024.
    - Hao Liu, Matei Zaharia, Pieter Abbeel

- DISTFLASHATTN: Distributed Memory-efficient Attention for Long-context LLMs Training [[pdf](https://arxiv.org/abs/2310.03294)]
    - arxiv:2310.03294, 2023.
    - Dacheng Li, Rulin Shao, Anze Xie, Eric P. Xing, Xuezhe Ma, Ion Stoica, Joseph E. Gonzalez, Hao Zhang

- Dsp: Dynamic sequence parallelism for multi-dimensional transformers [[https://arxiv.org/abs/2403.10266](https://arxiv.org/abs/2403.10266)]
    - arXiv preprint arXiv:2403.10266, 2024.
    - Xuanlei Zhao, Shenggan Cheng, Chang Chen, Zangwei Zheng, Ziming Liu, Zheming Yang, Yang You

- Striped attention: Faster ring attention for causal transformers [[pdf](https://arxiv.org/abs/2311.09431)]
    - arXiv preprint arXiv:2311.09431, 2023.
    - William Brandon, Aniruddha Nrusimha, Kevin Qian, Zachary Ankner, Tian Jin, Zhiye Song, Jonathan Ragan-Kelley

- Burstattention: An efficient distributed attention framework for extremely long sequences [[pdf](https://arxiv.org/abs/2403.09347)]
    - arXiv preprint arXiv:2403.09347, 2024
    - Ao Sun, Weilin Zhao, Xu Han, Cheng Yang, Zhiyuan Liu, Chuan Shi, Maosong Sun

- Wallfacer: Guiding transformer model training out of the long-context dark forest with n-body problem [[pdf](https://arxiv.org/abs/2407.00611)]
    - arXiv preprint arXiv:2407.00611, 2024.
    - Ziming Liu, Shaoyu Wang, Shenggan Cheng, Zhongkai Zhao, Xuanlei Zhao, James Demmel, Yang You

- Gshard: Scaling giant models with conditional computation and automatic sharding [[pdf](https://arxiv.org/abs/2006.16668)]
    - arXiv preprint arXiv:2006.16668, 2020
    - Dmitry Lepikhin, HyoukJoong Lee, Yuanzhong Xu, Dehao Chen, Orhan Firat, Yanping Huang, Maxim Krikun, Noam Shazeer, Zhifeng Chen

- Switch transformers: Scaling to trillion parameter models with simple and efficient sparsity [[pdf](https://arxiv.org/abs/2101.03961)]
    - Journal of Machine Learning Research, vol. 23, no. 120, pp. 1–39, 2022
    - William Fedus, Barret Zoph, Noam Shazeer

- Tutel: Adaptive mixture-of-experts at scale [[pdf](https://arxiv.org/abs/2206.03382)]
    - Proceedings of Machine Learning and Systems, vol. 5, 2023
    - Changho Hwang, Wei Cui, Yifan Xiong, Ziyue Yang, Ze Liu, Han Hu, Zilong Wang, Rafael Salas, Jithin Jose, Prabhat Ram, Joe Chau, Peng Cheng, Fan Yang, Mao Yang, Yongqiang Xiong

- Deepspeed-moe: Advancing mixture-of-experts inference and training to power nextgeneration ai scale [[pdf](https://arxiv.org/abs/2201.05596)]
    - International conference on machine learning. PMLR, 2022, pp. 18 332–18 346
    - Samyam Rajbhandari, Conglong Li, Zhewei Yao, Minjia Zhang, Reza Yazdani Aminabadi, Ammar Ahmad Awan, Jeff Rasley, Yuxiong He

- Scattered mixture-ofexperts implementation [[pdf](https://arxiv.org/abs/2403.08245)]
    - arXiv preprint arXiv:2403.08245, 2024.
    - Shawn Tan, Yikang Shen, Rameswar Panda, Aaron Courville

- Megablocks: Efficient sparse training with mixture-of-experts [[pdf](https://arxiv.org/abs/2211.15841)]
    - Proceedings of Machine Learning and Systems, vol. 5, 2023.
    - Trevor Gale, Deepak Narayanan, Cliff Young, Matei Zaharia

- Pipemoe: Accelerating mixtureof-experts through adaptive pipelining [[pdf](https://ieeexplore.ieee.org/document/10228874)]
    - IEEE INFOCOM 2023-IEEE Conference on Computer Communications. IEEE, 2023, pp. 1–10.
    - Shaohuai Shi, Xinglin Pan, Xiaowen Chu, Bo Li

- Schemoe: An extensible mixture-of-experts distributed training system with tasks scheduling [[pdf](https://dl.acm.org/doi/10.1145/3627703.3650083)]
    - Proceedings of the Nineteenth European Conference on Computer Systems, 2024, pp. 236–249.
    - Shaohuai Shi, Xinglin Pan, Qiang Wang, Chengjian Liu, Xiaozhe Ren, Zhongzhe Hu

- Accelerating distributed MoE training and inference with lina [[pdf](https://arxiv.org/abs/2210.17223)]
    - 2023 USENIX Annual Technical Conference (USENIX ATC 23), 2023, pp. 945–959.
    - Jiamin Li, Yimin Jiang, Yibo Zhu, Cong Wang, Hong Xu

- Janus: A unified distributed training framework for sparse mixture-of-experts models [[pdf](https://dl.acm.org/doi/10.1145/3603269.3604869)]
    - Proceedings of the ACM SIGCOMM 2023 Conference, 2023, pp. 486–498.
    - Juncai Liu, Jessie Hui Wang, Yimin JiangAuthors Info & Claims

- Ta-moe: Topologyaware large scale mixture-of-expert training [[pdf]](https://arxiv.org/abs/2302.09915)
    - Advances in Neural Information Processing Systems, vol. 35, pp. 22 173–22 186, 2022
    - Chang Chen, Min Li, Zhihua Wu, Dianhai Yu, Chao Yang

- Fastmoe: A fast mixture-of-expert training system [[pdf](https://arxiv.org/abs/2103.13262)]
    - arXiv preprint arXiv:2103.13262, 2021.
    - Jiaao He, Jiezhong Qiu, Aohan Zeng, Zhilin Yang, Jidong Zhai, Jie Tang

- FasterMoE: modeling and optimizing training of large-scale dynamic pre-trained models [[pdf](https://dl.acm.org/doi/10.1145/3503221.3508418)]
    - Proceedings of the 27th ACM SIGPLAN Symposium on Principles and Practice of Parallel Programming, 2022, pp. 120–134.
    - Jiaao He, Jidong Zhai, Tiago Antunes, Haojie Wang, Fuwen Luo, Shangfeng Shi, Qin LiAuthors Info & Claims

- SmartMoE: Efficiently Training Sparsely-Activated Models through Combining Offline and Online Parallelization [[pdf](https://www.usenix.org/conference/atc23/presentation/zhai)]
    - 2023 USENIX Annual Technical Conference (USENIX ATC 23), 2023, pp. 961–975
    - Mingshu Zhai, Jiaao He, Zixuan Ma, Zan Zong, Runqing Zhang, and Jidong Zhai

- Flexmoe: Scaling large-scale sparse pre-trained model training via dynamic device placement [[pdf](https://arxiv.org/abs/2304.03946)]
    - Proceedings of the ACM on Management of Data, vol. 1, no. 1, pp. 1–19, 2023.
    - Xiaonan Nie, Xupeng Miao, Zilong Wang, Zichao Yang, Jilong Xue, Lingxiao Ma, Gang Cao, Bin Cui

- Prophet: Fine-grained Load Balancing for Parallel Training of Large-scale MoE Models [[pdf](https://ieeexplore.ieee.org/document/10319949)]
    - 2023 IEEE International Conference on Cluster Computing (CLUSTER).
    - Wei Wang, Zhiquan Lai, Shengwei Li, Weijie Liu, Keshi Ge, Yujie Liu, Ao Shen, Dongsheng Li


## Auto Parallelism

## Heterogeneous Parallelism