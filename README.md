# L2C: Learning to Cluster
Paper: https://openreview.net/forum?id=SJzR2iRcK7
Author's code:https://github.com/GT-RIPL/L2C

# Team member：














## Introduction


This repository covers following references:
```
@inproceedings{Hsu19_MCL,
	title =	    {Multi-class classification without multi-class labels},
	author =    {Yen-Chang Hsu, Zhaoyang Lv, Joel Schlosser, Phillip Odom, Zsolt Kira},
	booktitle = {International Conference on Learning Representations (ICLR)},
	year =      {2019},
	url =       {https://openreview.net/forum?id=SJzR2iRcK7}
}

@inproceedings{Hsu18_L2C,
	title =     {Learning to cluster in order to transfer across domains and tasks},
	author =    {Yen-Chang Hsu and Zhaoyang Lv and Zsolt Kira},
	booktitle = {International Conference on Learning Representations (ICLR)},
	year =      {2018},
	url =       {https://openreview.net/forum?id=ByRWCqvT-}
}

@inproceedings{Hsu16_KCL,
	title =	    {Neural network-based clustering using pairwise constraints},
	author =    {Yen-Chang Hsu and Zsolt Kira},
	booktitle = {ICLR workshop},
	year =      {2016},
	url =       {https://arxiv.org/abs/1511.06321}
}
```

## Preparation
This repository supports PyTorch 1.0, python 2.7, 3.6, and 3.7.

```bash
pip install -r requirements.txt
```
## Demo
### Supervised Classification/Clustering with only pairwise similarity
```bash
# A quick trial:
python demo.py  # Default Dataset:MNIST, Network:LeNet, Loss:MCL
python demo.py --loss KCL

# Lookup available options:
python demo.py -h

# For more examples:
./scripts/exp_supervised_MCL_vs_KCL.sh
```
### Unsupervised Clustering (Cross-task Transfer Learning)
```bash
# Learn the Similarity Prediction Network (SPN) with Omniglot_background and then transfer to the 20 alphabets in Omniglot_evaluation.
# Default loss is MCL with an unknown number of clusters (Set a large cluster number, i.e., k=100)
# It takes about half an hour to finish.
python demo_omniglot_transfer.py

# An example of using KCL and set k=gt_#cluster
python demo_omniglot_transfer.py --loss KCL --num_cluster -1

# Lookup available options:
python demo_omniglot_transfer.py -h

# Other examples:
./scripts/exp_unsupervised_transfer_Omniglot.sh
```

### Acknowledgments
This is a Reproducibility Challenge which is based on the paper-Multi-class classification without multi-class labels
