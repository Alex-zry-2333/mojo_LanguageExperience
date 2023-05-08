从矩阵乘法的演示源码量来看，它并不如自己所介绍的那样 *simple * 。他所实现的矩阵乘法方式只有乘法实现部分是和python一致，是实现了它所谓的直接移植的。但是benchmark部分已经面目全非了。

相对的，它所谓的性能提升并没有给出原始的python实现算法到底如何。所以缺少相对的比较。

给出我自己部分的python实现对比，可以看出更加少的代码量实现：
```python
def benchmark_matmul_python(M,N,K):
    A-=-Matrix(list(np.random.rand(M,K)),M,K)
    B.=Matrix(list(np.random.rand(K,N)),K,N)
    C.=-Matrix(list(np.zeros((M,N))),M,N)
    secs-=timeit(lambda:matmul_python(C,A,B),number=2)/2
    gflops ((2*M*N*K)/secs)/1e9
    print(gflops,"GFLOP/s")
    return gflops
def benchmark_matmul_numpy(M,N,K):
    A=-np.random.rand(M,K)
    B=np.random.rand(K,N)
    secs=timeit(lambda:matmul_np(A,B),number=2)/2
    gflops=((2*M*N*K)/secs)/1e9
    print(gflops,"GFLOP/s")
    return gflops
```

所以目前还是先给他成长的空间吧。

附赠一些网友有趣的讨论：

>1. 来自reddit的评价说的很准确，虽然自称为为ai而生的语言，没有解决任何一个python之于ai方向的缺陷，并没有原生的自动求导、显存管理等功能。就像是Nim一样，只是一个类似python语法的更快的语言。为了兼容cpython，很可能还不如Nim，唯一的优势就是天生能用python生态，但我并没有看到用它的优势。

>2. 在.py里面写c，然后c编译器编译。py性能追上c，指日可待😋😋😋


----------------
### 以下为Mojo原本内容:


# Welcome to Mojo 🔥

Mojo is a new programming language that bridges the gap between research 
and production by combining Python syntax and ecosystem with systems 
programming and metaprogramming features. Mojo is still young, but it is designed
to become a superset of Python over time.  

We plan to open-source Mojo progressively over time, but it's changing very quickly now. 
We believe that a small, tight-knit group of engineers with a shared vision can move 
faster than a community effort, so we will continue to incubate it within Modular until 
it's more complete.  Please see the [Mojo FAQ](https://docs.modular.com/mojo/faq.html)
for more information about this and other common questions. 

We've opened this repo now because we want to gather issues and engage in feedback 
from users who have access to the Mojo Playground (our hosted JupyterHub
where you can try coding with an early version of Mojo). 
To get access to the Mojo Playground, [see here to sign up](https://docs.modular.com/mojo/get-started.html).
Then, when you want to report issues or request features,
[please create a GitHub issue here](https://github.com/modularml/mojo/issues).

For more general questions or to chat with other Mojo developers,
check out our [Discord](https://discord.gg/modular). 

Otherwise, you can:
- Read the [inspiration behind Mojo](https://docs.modular.com/mojo/why-mojo.html).
- Check out the [Mojo programming manual](https://docs.modular.com/mojo/programming-manual.html).
- Read our other docs on [docs.modular.com/mojo](https://docs.modular.com/mojo).
