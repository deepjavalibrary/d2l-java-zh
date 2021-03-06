# 循环神经网络
:label:`chap_rnn`

到目前为止，我们遇到了两种类型的数据：表格数据和图像数据。对于后者，
我们设计了专门的层来利用其中的规律。换句话说，如果我们对图像中的像素进行调换，
就很难对其内容进行推理。这些内容看起来很像模拟电视时代的雪花屏。

最重要的是，到目前为止，我们默认我们的数据都来自某种分布，并且所有样本都是独立同分布的
（i.i.d.）。不幸的是，大多数的数据并非如此。例如，文章中的单词是按顺序写的，
如果打乱它们的顺序，就很难理解它们组成的意思。同样，视频中的图像帧、
对话的音频信号以及网站上的浏览行为都是有顺序的。因此，我们可以合理地假设，
针对这类数据的专门模型会更好地描述它们。

有时我们希望不仅可以接收一个序列作为输入，而是可以期望继续猜测该序列。例如，
任务可以是继续预测$2, 4, 6, 8, 10, \\ldots$。这在时间序列分析中是相当常见的，
可以用来预测股市、患者的体温曲线或赛车所需的加速度。同样，我们需要能够处理这些数据的模型。

简言之，卷积神经网络可以有效地处理空间信息，循环神经网络（RNN）的设计可以更好地处理序列信息。
循环神经网络引入状态变量来存储过去的信息以及当前的输入，以确定当前的输出。

许多使用循环网络的例子都是基于文本数据的。因此，我们将在本章中重点介绍语言模型。
在对序列数据进行更正式的回顾之后，我们将介绍文本预处理的实用技术。接下来，
我们将讨论语言模型的基本概念，并将此讨论作为循环神经网络设计的灵感。最后，
我们描述了循环神经网络的梯度计算方法，以探讨训练此类网络时可能遇到的问题。

```toc
:maxdepth: 2

sequence
text-preprocessing
language-models-and-dataset
rnn
rnn-scratch
rnn-concise
bptt
```