# 第二次作业-基于HMM的语音识别系统

1.认真读lab2.pdf, 思考lab2.txt中的问题
2.理解数据文件
3.ref文件作为参考输出，用diff命令检查自己的实现得到的输出和ref是否完全一致
4.实验中实际用的GMM其实都是单高斯
5.阅读util.h里面的注释，Graph的注释有如何遍历graph中state上所有的arc的方法。

p1 给定一个gmm用viterbi解码,有参考的解码图chart.ref进行校验。

p2 估计模型参数,不使用前向后向算法计算统计量，而是用viterbi解码得到的最优的一条序列来计算统计量，叫做viterbi-EM. 给定align（viterbi解码的最优状态序列)，原始语音和GMM的初始值，更新GMM参数.有参考的输出gmm.ref进行校验。

p3 用前向后向算法来估计参数， 有参考的gmm.ref进行校验。 
p3a:1条数据，1轮迭代
p3b:22条数据，1轮迭代
p3c:22条数据，20轮迭代
p3d:使用p3c的模型，结果应该和p1b一样

p4
p4a:使用100，300，1000条孤立词数据训练模型，在100条孤立词测试数据上viterbi解码，测试错误率
p4b:使用p4a中的300条孤立词训练出的模型，在100条连续词数据上viterbi解码，测试错误率。 再用300条连续词训练数据训练模型，在同样的100条连续词数据上viterbi解码，测试错误率
p4c:使用带state transition概率的HMM，进行解码。