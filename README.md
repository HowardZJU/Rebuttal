# Materials for Response letter
## General Response
### Q2
The figure below reports the PEHE of ESCFR under different hyper-parameter $\kappa$. All ESCFR implementations outperform the strongest baseline CFR-WASS ( $\kappa=\infty$) on all batch sizes, most of which are statistically significant. As such, hyper-parameter is not necessarily the reason why ESCFR works well. This can be further supported by our extensive ablation and parameter studies in the manuscript.
![RMPR figure](./fig_rmpr.png "aaa")


## Reviewer #1
### Q2
Since accurate estimation of factual outcomes is the basis for causal inference, the batchsize, as well as learning rate, was finetuned based on TARNet at the very beginning, to improve the performance of factual estimation. We selected batchsize=32 due to its superior factual accuracy (R2, MSE of factual outcome estimation) on evaluation set. Raw logs are available in this link
![RMPR figure](./batch_size.png "aaa")


## Reviewer #3


