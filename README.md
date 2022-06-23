# StrGNN

---------------------------------------------------------------------------------------------------------------------------------

anomaly detection with accumulate graph

Entern detection folder

python Main.py --graph=acc_email.npy --split=email0.01

acc_email.npy is the graph input with shape (T, N, N), where T is the number of snapshot and N is the number of nodes in the graph

email0.01 contains train_pos_id, train_neg_id, test_pos_id, test_neg_id, train_pos, train_neg, test_pos, test_neg:

train_pos_id is with shape (N,). It indicates the which snapshot the edge (in train_pos) come from

train_pos is with shape (N, 2). Each row i corresponds to a edge in the snapshot train_pos_id[i]

train_neg_id is with shape (N,). It indicates the which snapshot the edge (in train_neg) comes from

train_neg is with shape (N, 2). Each row i corresponds to a non-exist edge (sample for training classifier) in the snapshot train_neg_id[i]

similar for test_pos_id, test_neg_id, test_pos, test_neg

---------------------------------------------------------------------------------------------------------------------------------

#anomaly detection with time-evolving graph

python Main_statistic.py --graph=sta_email.npy --split=email0.01_sta

parameters are the same as accumulate setting, the only difference is that the graph is time-evolving graph

---------------------------------------------------------------------------------------------------------------------------------

data folder contains the processed email data for our model 

data_sta folder contains corresponding time-evolving graphs

--------------------------------------------------------------------------------------------------------------------------------
## Citation
If you find the code in this respository useful for your research, please cite our paper:
  @inbook{cai2021,
  author = {Cai, Lei and Chen, Zhengzhang and Luo, Chen and Gui, Jiaping and Ni, Jingchao and Li, Ding and Chen, Haifeng},
  title = {Structural Temporal Graph Neural Networks for Anomaly Detection in Dynamic Graphs},
  year = {2021},
  address = {New York, NY, USA},
  booktitle = {Proceedings of the 30th ACM International Conference on Information & Knowledge Management},
  pages = {3747–3756},
  numpages = {10}
  }
---------------------------------------------------------------------------------------------------------------------------------

The code is implemented based on 

https://github.com/muhanzhang/SEAL
https://github.com/muhanzhang/pytorch_DGCNN

--------------------------------------------------------------------------------------------------------------------------------
Accumulated Graph and Time-evolving Graph
Typically, there are two ways to model dynamic systems as dynamic graphs, namely, accumulated graph and time-evolving graph. 
The accumulated graph %automatically and incrementally constructs an entire graph using all vertices and edges until the current timestamp. 
In contrast, the time-evolving graph is constructed using vertices and edges only appearing in the current timestamp. 
Therefore, each snapshot represents the graph state at a single instant of time.

--------------------------------------------------------------------------------------------------------------------------------
@CopyRights
This code can only be used for research purpose, and can not be distributed without the authors' permission.


