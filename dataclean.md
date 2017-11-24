```py
import sys
import pandas as pd
from numpy import *
from sklearn import preprocessing as pp

"""
该脚本主要对数据进行初步的清洗，主要包含以下步骤
1. 对次数相关的数据进行缺失值填补
2. 对含空值较多的数据进行过滤
3. 对缺失值进行相关性填补
4. 数据的标准化
"""


#对次数类的特征进行空值填补
def countFeaNull(df, count_feature_list):
    for fi in count_feature_list:
        n_before = len(df[df[fi].isnull()])
        df[fi] = df[fi].fillna(0)
        n_after = len(df[df[fi].isnull()])
        print di, '-' * 8, n_before, '-' * 8, n_after 
    return df 

#过滤掉含空值比例较高的样本
def dropNull(df, rate_min = 0.2):
    n_before = len(df)
    #计算空值比例
    def nullRate(a):
        return len(a[a.isnull()]) * 1.0 / len(a)
    #计算数据中每个样本的空值比例
    df['null_rate'] = df.apply(nullRate, axis = 0)
    df_new = df[df['null_rate'] >= rate_min]
    df_new = df_new.reset_index(drop = True) 
    n_after = len(df_new)
    print '-- before:  ', n_before, '/n-- after:  ', n_after 
    return df_new 

#对缺失值进行中位数/均值填补
def FeaNull(df, feature_list):
    for fi in feature_list:
        medi = np.median(df[fi])
        n_null = len(df[df[fi].isnull()]) / len(df)
        print '-' * 10, fi, '-----', n_null
        df[fi].fillna(medi)
    return df

#数据标准化
def standard(df, user_list, feature_list):
    X = df[feature_list].values.astype(float)
    #标准化
    #X_scaled = pp.scale(X)
    #X_scaler = pp.StandardScaler().fit_transform(X)
    #正则化
    X_norm = pp.normalize(X)
    #X_norma = pp.Normalizer().fit_transform(X)
    #归一化
    #X_std = pp.MinMaxScaler().fittransform(X)
    return pd.concat([pd.DataFrame(X_norm, index = df.index, columns = feature_list), df[user_list]], axis = 1)
```



