# Materials for Response letter

## Reviewer 1

## Reviewer 2

## Reviewer 3

## General Response
Changes to the Final Draft
Based on the reviewers' shared concerns, we will make the following changes in the final draft.

## Reviewer #1
Q1. Here are some papers [1-3] with respect to which the paper needs to be positioned starting even from the introduction.
A1. aaa

Below are responses to questions raised as limitations.
Q2. The main theorem is a bit practically vacuous as the sampling error decays with the minibatch size which is typically very small for the theorem to have any bite
A2. 诚然sample complexity is a common and well-studied problem.但是，wass的不多见。
此外，这是必要的，因为就如文章里说的那样，目前的定理主要是基于全量分布已经知道的情况，不适用于batch训练的情况。
最后，证明是为了引出采样敏感性，使得文章的intuition self-contained
Q3. The biggest problem is if a confounder changes the relationship between the two potential outcomes. Their method only removes confounder bias when confounders also change the baseline responses. What if all a confounder does is add a constant effect to all samples. This will never be detected by their regularization term.
A3. Limitation. But our contribution and primary aim is xxx.

[1] An Optimal Transport Approach to Causal Inference, Torous et al 
[2] Optimal transport weights for causal inference, Dunipace 
[3] Deep treatment-adaptive network for causal inference, Li et al

## Reviewer #2

Q1. Do you need to use the Wasserstein distance? Would it work using MMD as well? 

Q2. It seems like most other method overfits (in-sample performance on AUUC is high but OOS is low), could you interpret ESCFR as an efficient regularizer for ITE estimation in TarNets as well? 

Q3. What's the (ball-park) complexity of the algorithm wrt batch size?

Below are responses to questions raised as limitations.

Q4. Some further contextualization against baselines would be appreciated (CFR-MMD and CFR-Wasserstein)

## Reviewer #3
Q1. Representation learning mitigates variance by minimizing distributional discrepancies; there is no bias once confounders are conditioned on by design.

Q2. It is questionable to assume that all variation in Y that does not come from observed confounders X or treatment T, must be due to unobserved confounders X′. Could it not be due to variables Z with an independent causal effect on Y? Specifically the reasoning in lines 204-206 is not necessarily correct, I believe. Beyond intuitive explanations, there are no references to similar approaches or formal justification of the proposed approach, can a simple example be constructed to understand how the proposed regularization correctly accounts for distributional differences between treatment groups?
A2.1 YES, but not important. That is the adjustment variable, conditioning on which do not introduce extra bias. 然而这是一个很重要的问题，将在revision中特别claim它。
A2.2 Admittedly this is an intuitive approach. However, we think this intuitive is worth mentioning.
A2.3 Yes, we provide a link xxx.
A2.4 Further experiments. (JDOT exp)

Q3. Strong experimental evaluation is needed to facilitate theoretical understanding. 
Q3.1 If using (semi) synthetic labels for data generation, how is unobserved confounding introduced? 
A3.1 很高兴看到insightful的comment。半合成数据的生成过程中，在生成T和Y的时候一般会mask部分变量，详情请参考xxx for ACIC数据和xxx for IHDP数据。
Q3.2 Does the performance increase in Figure 5 (c) indicate that there are unobserved confounders, why else would performance increase? Could it just be due to increased regularization?
A3.2当然，我们也认为increased regularization是涨点的一个因素。但是我们在实验的时候fix other strengths of regularization.

Q4.1 Model selection based on AUUC is not standard in the ITE literature. Has AUUC been used for hyperparameter selection in other methods?
A4.1 理解您的担忧，做模型选择相比MSE确实优势不大，但在开发过程中我们认为其可以有效指导早停，可视化见xxx。AUUC被用于所有模型的evaluation and selection protocol。
Q4.2 Since one of the biggest challenges for this problem is hyperparameter selection (and the authors optimize over many of them) I wonder whether performance improvements come from the model selection procedure rather than anything else. 
A4.2 ablation study中的对比试验。报一下没有finetune的点。

Q5. The most recent baseline algorithm dates from 2017. Many, many ITE methods have been developed since.
A5. 这是这篇文章的主要缺陷，然而在我们的调研阶段发现，大多数方法都是将分布对齐作为一个组件使用，并在此基础上扩展，比如linexxx所示的xxx，并没有考虑改善分布对齐本身带来的增益。因此，针对分布对齐本身在因果推断中的应用，最经典和完善的研究应该是xxx，在此基础上进行改进可以带来显著和基础性的贡献。
Q6. One reason for poor performance of benchmarks is low minibatch size, can this be tested empirically?
A6.   1. 实验导出的；2. 数据量普遍偏小，所以这个batch size是合理的；3. Follow了经典文献的做法；4. 验证了不同batch下+- RMPR的有效性。

Below are responses to questions raised as limitations.

Q7. For example, there is no mention of assumptions or underlying causal framework under which treatment effect estimation can be shown to be sound, e.g. overlap, positivity, how unobserved confounders are defined, etc (a general overview is given in the Appendix but is not clear whether the authors adopt these assumptions or not).

