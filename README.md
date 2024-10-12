# protein-anti-Affinity-predict
数据进行预处理，进行了整个链的信息的合并，再随机以一个max_gap 200bp的大小来进行填充到固定大小（1000）
加入了氨基酸的力场数据，氨基酸的理化属性，主要采用的是skempi dataset的突变体数据。
用了train数据data作为预训练的输入数据
预测test数据
最后把预测结果对齐到给定的valdation数据的label

模型框架请看架构图。

model procedure
1.data processing
2.pretrain the amino acid space 
3.train the affinity score with mutation dataset
4.predict the test data affinity 

a.pretrain_amino_space.py 预训练
b.train_affinity_predict_model 有标签训练 加上了预训练的氨基酸空间结果
c.predict_test_affinity 预测test的亲和力结果


#results 重要文件夹
res文件夹下 是预训练的结果
affinity_predict_res_property_test 文件夹下 是train model 的结果 r2 可以达到0.7
predict_Test_affinity_res_mut 是test数据 的预测结果 

代码模型的思想参考了 
MethylBERT: A Transformer-based model for read-level DNA methylation pattern identification and tumour deconvolution
https://github.com/CompEpigen/methylbert/tree/main
