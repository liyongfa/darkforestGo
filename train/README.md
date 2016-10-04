Training Policy network
=================

In this directory, we implement a simple reinforcement learning framework using Lua/torch, and use
it for training the policy network.

1. `./infra` The simple framework.

2. `./examples/go` The training code for policy network.

For simple usage, the main program for training is under the root directory. Simply run ./train.sh
will start the training procedure, which is an implementation of our [paper](http://arxiv.org/abs/1511.06410) plus a few modifications, including adding batch-normalization layers.

With 4 GPUs, the training procedure should be able to give around 56% accuracy in KGS dataset in three days. In the following there is a simple log.

```
| Sun Aug 21 21:54:15 2016 | epoch 0001 | ms/batch 721 | train [1pi@1]:
11.230860 [1pi@5]: 30.617970 [3pi@1]: 3.099219 [3pi@5]: 14.042188 [2pi@5]:
18.935938 [2pi@1]: 4.482813 [policy]: 8.361849 | test [1pi@1]: 27.767189
[1pi@5]: 59.403130 [3pi@1]: 5.380469 [3pi@5]: 24.729689 [2pi@5]: 34.030472
[2pi@1]: 8.382812 [policy]: 6.558414 | saved *

| Thu Aug 25 10:35:11 2016 | epoch 0381 | ms/batch 719 | train [1pi@1]: 56.226566 [1pi@5]: 87.523834
[3pi@1]: 21.542580 [3pi@5]: 51.992970 [2pi@5]: 68.728127 [2pi@1]: 34.199612 [policy]: 3.736506  |
test [1pi@1]: **56.124222** [1pi@5]: 87.432816 [3pi@1]: 21.600000 [3pi@5]: 52.107815 [2pi@5]: 68.922661
[2pi@1]: 34.421875 [policy]: 3.737540  | saved *
```

Note that this is a general framework and could be used to train other tasks (e.g, value networks) in the future. If you have used our engine or training procedure, please cite the following paper:

```
Better Computer Go Player with Neural Network and Long-term Prediction, ICLR 2016
Yuandong Tian, Yan Zhu

@article{tian2015better,
  title={Better Computer Go Player with Neural Network and Long-term Prediction},
  author={Tian, Yuandong and Zhu, Yan},
  journal={arXiv preprint arXiv:1511.06410},
  year={2015}
}
```

