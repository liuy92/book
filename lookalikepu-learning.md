# pu-learning

参考：https://roywright.me/2017/11/16/positive-unlabeled-learning/

### 目标

在lookalike场景下，当只有正样本，没有负样本时，可以建模的方式有两种：

1. 通过一些规则定义负样本
2. 正样本计算相似
3. 用全量未标记的样本作为负样本

当采取方法1进行建模时，在大样本场景下，会存在大量未标记样本，其中存在规则未包含的负样本的状况，并且由于规则会使模型产生较大偏差，会导致最后的lookalike预测用户中推荐出不符合要求的用户

当采取方法2时，在种子用户分布不集中时，会导致推荐用户不准确



#### 附录

* Learning Bayesian classiﬁers from positive and unla-beled examples    2007

* Learning classifiers from only positive and unlabeled data           2008

* Positive unlabeled learning for data stream classification            2009

* A bagging SVM to learn from positive and unlabeled examples   2013

* An Evaluation of Two-Step Techniques for Positive-Unlabeled Learning in Text Classification     2014

* Analysis of learning from positive and unlabeled data                  2014

* Towards Positive Unlabeled Learning for Parallel Data Mining: A Random Forest Framework      2014

* Theoretical comparisons of positive-unlabeled learning against positive-negative learning          2016

* Efficient training for positive unlabeled learning                                      2016

* Positive-Unlabeled Learning with Non-Negative Risk Estimator             2017



