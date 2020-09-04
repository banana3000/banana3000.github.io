---
layout: post
title: Cousin复形，Grothendieck duality定理
---


下面假设你已经看完了Residues and duality的介绍（写得很好，从例子和历史开始，一步步formulate想证明的结果），知道这本书的主题是构造Rf^! for proper f: X ->S，知道基本证明路线(projective的情况可以具体算，把morphism拆成好算的smooth map/ finite map/ regular immersion)，知道derived category is not a local object不能直接glue所以这本书花了大功夫取具体的residual complex造具体的injective resolution (by a general theory of Cousin complex)，知道本书附录Deligne给出了存在性第一个抽象简短证明（和本书套路完全不同，考虑的是一般finite type morphism，尽管有一些条件限制。翻译了Verdier的结果，需要用Nagata compactification，Lipman很多年之后大大发展了这条路线，补充了细节）。

这本书是非常经典的读物，但你当然可以认为它已经过时了，如果用不上这些工具，看不看完全是个人喜好。我以前看过此书的一部分，现在忘了很多，也用不上。

所以我就随便谈一谈，证明有人说了几点，我就不说了。

也谈不上是最现代的观点，Stacks project讲dualizing complex参考了这本书的第五节，但是Grothendieck duality的主体还是Neeman的Brown representability （本书开头说unbounded derived category is too big这件事导致了很多麻烦，却想不到Neeman能直接使用）。而除了这几种，还有其他的证明方式。

这本书开头介绍基础知识花了很大篇幅（两百多页，当时derived category并没有专门的材料介绍），另外交换图表好多没有验证交换性（Grothendieck的直觉害人），还有一些小错误，Hartshorne当年改了那么多次后还是无力地出版了。后来Conrad写过书改正了一些问题。

比起长长的正文，Deligne附录的证明看起来比较短，而且原理基于抽象的adjoint functor theorem（抽象论证爱好者可能会喜欢）：


但是，这本书真的没有可取之处么？我想，这是一本很有意思的书，写法很有趣，影响也不止Grothendieck duality。

Introduction引用的希腊语ὁδὸς ἄνω κάτω μία καὶ ὡυτή是赫拉克利特（Heraclitus）的一句名言

上升的路和下降的路是同一条路。

Cousin complex那部分的写法如同在作曲，性质变成了Motif（本义，音乐中一段特定的短旋律），推广到其他情形的讨论变成了variation（变奏）：


而residue symbol的处理还有一维情况的计算，还是应该查查此书。

抽象性的存在性证明并不适合计算，这条路线看起来dirty其实现在也有不少简化，可以用来算具体的dualizing complex等东西。

作为早期一本经典的教材，有各种各样的结论方便引用，Grothendieck duality, local duality, 而同类教材少之又少，故大家都引这一本书。

最后想提的是书里发展了Cousin complex的理论。

Cousin这个名字来自于复分析里著名的Cousin问题，和sheaf cohomology有关。Cousin complex的定义实际上非常简单，Grothendieck总能从朴素的想法中提炼出新东西：

假设Z是拓扑空间X里的一个闭集，那对于X上面的abelian sheaf F，可以考虑global sections of F with support in Z，取其derived functor，再去graded part随即得到cohomology with compact support H^i_Z(X,F)。

假如Z_2 in Z_1, 那么为什么不考虑abelian sheaf的global sections with support in Z_1商掉global sections with support in Z_2得到的abelian group H^0_{Z_1/Z_2}(X,-)呢？

再取derived functor，我们得到cohomology groups记为H^i_{Z_1/Z_2}(X,F)。

Exercise：证明H^0_{Z_1/Z_2} is left exact, and we can define derived functor.

于是对于Z_3 in Z_2 in Z_1，我们可以看到有长正合列

0-> H^0_{Z_2/Z_3}(X,-) -> H^0_{Z_1/Z_3}(X,-) -> H^0_{Z_1/Z_2}(X,-) -> H^1_{Z_2/Z_3}(X,-) -> H^1_{Z_1/Z_3}(X,-) -> ...

于是我们得到一个自然的map H^i_{Z_1/Z_2}(X,-) -> H^{i+1}_{Z_2/Z_3}(X,-)

现在考虑....Z_4 in Z_3 in Z_2 in Z_1 in Z_0=X，我们得到一串maps

H^0_{Z_0/Z_1}(X,F) -> H^1_{Z_1/Z_2}(X,F) -> H^2_{Z_2/Z_3}(X,F) -> H^3_{Z_3/Z_4}(X,F) -> ....

Exercise: 证明这构成一个complex，也就是说两个相邻map的复合是0.

（如果看不出这个显然的习题，可以考虑复习一下基本的同调代数）

这就称为F关于拓扑空间X的闭子集降链Z_i的Cousin complex。

在非常好的情况下，这个complex给出H^0(X,F)的一个explicit resolution.

Grothendieck创造的用Cousin complex算global sections的方法，最早是在这本书里出现的，虽然书里只用了height filtration这个case，但是这种方法其实在各种地方都能用上，非常方便。在交换代数里可以和Cohen-Macaulay module扯上关系，被大量研究。Kempf用它重新证明了表示论里的Borel–Weil vanishing theorem（任何特征）和Borel-Weil-Bott theorem（特征0）。更多现代应用就不说了。
