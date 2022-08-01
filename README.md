# Materials for Response letter
## General Response
### Q2
The figure below reports the PEHE of ESCFR under different hyper-parameter $\kappa$. All ESCFR implementations outperform the strongest baseline CFR-WASS ( $\kappa=\infty$) on all batch sizes, most of which are statistically significant. As such, hyper-parameter is not necessarily the reason why ESCFR works well. This can be further supported by our extensive ablation and parameter studies in the manuscript.
![RMPR figure](./fig_rmpr.png "aaa")


## Reviewer #1
### Q2
Since accurate estimation of factual outcomes is the basis for causal inference, the batchsize, as well as learning rate, was finetuned based on TARNet at the very beginning, to improve the performance of factual estimation. We selected batchsize=32 due to its superior factual accuracy (R2, MSE of factual outcome estimation) on evaluation set. Raw logs are available in this link
![RMPR figure](./batch_size.png "aaa")

## Reviewer #2
### Q3
We report the actual running time in seconds for 100 runs on the GPU (mean + std). In general, the computational cost of optimal transport is not a concern of ESCFR at the mini-batch level.

| Batch size | 32            | 64            | 128           | 256           | 512           | 1024           |
|------------|---------------|---------------|---------------|---------------|---------------|----------------|
| Algorithm1 | 0.0266+0.0102 | 0.0241+0.0075 | 0.0326+0.0088 | 0.0499+0.0099 | 0.0725+0.0128 | 0.1430+0.0259  |
| Algorithm2 | 0.0050+0.0004 | 0.0051+0.0001 | 0.0065+0.0002 | 0.0104+0.0005 | 0.0138+0.0008 | 0.0256+0.0007  |

| Parameter   | $\epsilon$=0.1 | $\epsilon$=0.5 | $\epsilon$=1.0 | $\epsilon$=5.0 | $\epsilon$=10.0 | $\epsilon$=100.0  |
|-------------|----------------|----------------|----------------|----------------|-----------------|-------------------|
| Algorithm l | 0.1683+0.0038  | 0.1207+0.0102  | 0.0699+0.0095  | 0.0153+0.0013  | 0.0097+0.0009   | 0.0072+0.0009     |
| Algorithm 2 | 0.0166+0.0019  | 0.0068+0.0010  | 0.0052+0.0011  | 0.0047+0.0010  | 0.0045+0.0011   | 0.0043+0.0009     |

| Parameter   | $\kappa$=0.1  | $\kappa$=0.5  | $\kappa$=1.0  | $\kappa$=5.0  | $\kappa$=10.0 | $\kappa$=100.0  |
|-------------|---------------|---------------|---------------|---------------|---------------|-----------------|
| Algorithm 2 | 0.0050+0.0011 | 0.0059+0.0008 | 0.0060+0.0011 | 0.0112+0.0014 | 0.0162+0.0016 | 0.1039+0.0033   |

## Reviewer #3


