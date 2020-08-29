---
layout: post
title: 整体Langlands浅谈(一)
---

I will try to explain it to non-experts in a simple and informal way, but I won't just throw out big notions and repeat other people's words.

先往大了说，Langlands program的影响随处可见，特别地联系了数论和表示论，代数几何倒是其次的。Langlands纲领希望在具有"算术"意义的一些域上，建立其Galois群的表示、线性代数群的“代数”光滑表示、代数簇（好听点叫motive）的算术之间的对应关系。整体域比如有理数域Q，函数域F_q(t)，局部域比如p进数域Q_p，实数域R，复数域C，以及有限域F_q上都应该有这种对应。

代数群的“代数”光滑表示是一个不严谨的术语，对于局部域它指的是G(F)的光滑不可约表示，对于整体域它指的是G(A_F)的可容许不可约表示，并且出现在L^2函数空间L^2(G(F)\G(A_F))中，满足增长性条件，自守表示总可以写成局部域表示的限制张量积(Flath)。而代数群是指connected reductive groups，之所以要求reductive是因为不reductive会导致一些分析上的问题，而reductive group至少在特征0其代数表示都是半单的，本身也能够被根系很好的决定有好的分类（至少在代数闭域），所以会优先考虑，即使我们也关心不reductive的例子比如说G_a或者cover groups。

Langlands对应粗糙来说是指，给一个Galois表示，就应该能找一个自守表示，反之亦然。

最重要的是，Langlands program应该具有各种相容性（local-global compatibility、改变对偶群产生的functoriality特别是endoscopic transfer、改变基域产生的base change functoriality），这种函子性的观点才是其威力所在。

就像Galois理论能用群论方便解释域扩张的包含关系一样，Langlands构想这套理论，是希望通过一个方面已有工具来证明得到另一个方面的信息，加深理解。下面举几个例子。

如Galois表示有许多自然的代数操作，restriction, induction, tensor product，symmetric power，那么自守表示侧也应该有这些运算，作为函子性猜想的特例。在Langlands之前，人们没有想到还有这么多方式从一个群的自守表示，得到另一个群的自守表示。特别地函子性告诉我们应该有endoscopic理论也应该有Jacquet-Langlands transfer，任何G的自守表示的L function都是某个GL_N的自守表示的L function。

如自守侧的L function有很多好的解析性质，而Galois侧的Artin L function则非常神秘，如果能通过前者理解后者，再将后者与代数簇的算术联系，那我们可以得到很多有用的算术推论，这是Langlands提出这套纲领的动机之一。

这样的互相理解自然是极好的，Langlands在原始论文里便提到了函子性+自守表示工具的诸多应用，如Symmetric power的函子性可以推出部分Sato–Tate conjecture（还需要知道L function的自守性），Ramanujan conjecture （for cuspidal ones），Selberg conjecture (for cuspidal ones)，如L函数的对应可以推出部分Artin conjecture。更多应用请阅读Shahidi的Langlands Functoriality Conjecture and Number Theory一文。

OK我还没提什么是L function，首先什么是算术？给一组整系数方程组，求它的整数解/有理数解个数，这是最直观的例子。但是整体域上解方程太难了，人们会想先在局部域上求解，mod p后数有限域上解的个数，然后把这无限多个数字打包拼成L function，一个定义在复平面的一个半平面上的实实在在的复值函数，就应该蕴含了很多算术信息。实际上通过Lefschetz trace formula，这个L function是Galois表示的L function的特例，后者统称为Artin L function。而对于自守表示，也能以局部拼整体的方式定义L function，称为automorphic L function。至少对于GL_n，cuspidal automorphic representation的L function是用积分定义的，可以用求和公式等工具截断研究其解析性质，证明其在Re s=1没有零点（这能推出素数定理），其可以解析延拓，很是方便。

L function可以说是整体Langlands program的核心之一，正是因为它在Langlands对应下被保持，才有了那么多丰富的应用。同时，L函数对应+函子性+epsilon factor对应等公理+一维情况的正规化，唯一确定了GL_n的Langlands对应（local的情况是归纳法加分类，global的情况再使用Chebotarev density theorem+multiplicity one theorem），这说明它并非随意捏造的映射。

那么为什么我们相信Langlands对应？原因很多：

在Langlands那个时代，GL_1的情形也就是class field theory早就被人用Galois cohomology+L function的方法证明了。Langlands顺手推广到了所有tori的情况（using Tate-Nakayama duality）。
而Langlands本身对real group上的Eisenstein series有很多研究。 实际上，最早人们在实数域上研究表示论，积累了大量经验，建立了”Langlands对应“的许多例子，Langlands得到了Langlands classification，才有了后来更一般的猜想。而Eisenstein series的构造，conceptually很适合从Galois侧来理解：它无非是Galois表示 Gal -> {}^LM 复合上Levi子群的包含 {}^LM -> {}^L G。但是算它的poles，留数，常数项，证明解析延拓和函数方程，背后有很多分析功夫以及组合，并不是一般人在那时能体会到的。这方面读物除了Shahidi的书似乎也没有什么完整教材，不过最近有一个新证明https://arxiv.org/abs/1911.02342。
最重要的是，unramified情况的Langlands也是知道的（at least for quasi-split ones），这东西通常叫Satake isomorphism，是一切的基础。这东西其实很早就证明了（就是算算积分，上三角矩阵，行列式非零，好像没什么），也是最早被几何化的，然后有了几何表示论，几何Langlands...
很遗憾，上面也不过是一些well-known的东西，都是40年前的近代数学，谈不上现代数学。接下来谈谈30年前的近代数学：

关于Langlands对应的证明，对于GL_n来说，局部理论已经足够清晰（有至少三种证法），最暴力的方法是直接分类，例如GL_2的Galois侧用admissible pairs，自守侧用type theory（compact induction），这一套的大成则是Henniart他们的工作，至今explicit construction of local Langlands以及验证几种构造给出同一个对应还是一个值得研究的话题 e.g by theta correspondence。

而整体理论的Automorphic-to-Galois方向，需要借助Shimura簇的几何作为中间桥梁，因为我们相信Hasse-Weil zeta functions of varieties over number fields are conjecturally products (and quotients) of automorphic L-functions，而Shimura variety over Q^{alg}的上同调上天生有两个群的作用。道理看起来简单，你只要找到一个Galois表示和它的L函数match就行了，对于GL_2可以用Eicher-Shimura relation因为特征多项式是二次的，唯一不知道的就是trace。

一般的话，先假定我们是紧的PEL type A也就是某类unitary Shimura，那就看Langlands-Kottwitz方法，比较Arthur trace formula和Lefschetz trace formula，也就是Kottwitz两篇文章，里面虽然有没解决的猜想，还假定了当时并不知道的基本引理，但可能找不到比这个更好的介绍了。Langlands-Kottwitz大致是用trace formula算Frob twist of Hecke operator的trace，再用合适的test function分离出来spectrum里的各部分，但这个需要比较几何侧，也就是Orbit integral和数点的比较，根据moduli interpretation（差个#Ker^1(Q,G) factor无所谓）可以用Honda-Tate+Dieudonne理论把数点变成轨道积分乘上twist轨道积分 over Kottwitz triple，base change fundamental lemma消掉twist。其实Kottwitz只是把公式给写下来，具体的比较还需要稳定化，非常麻烦。至于更一般的PEL type乃至Hodge type，问题就更复杂了，还需要考虑紧化的问题。Langlands等人在这之前写过一本书，专门研究Hilbert modular surface的zeta function，已经巨复杂了。

假如从GL_n / Q 的自守表示出发，想让它出现在上同调里，我们知道GU(n,1)的Shimura簇不是定义在Q而是在原来那个CM fieldE上，所以表示先要做base change然后descent to GU(n,1)，因此通常得假定自守表示是cuspidal、regular algebraic、self-duality...削弱假设是很难的事，并且整体的Langlands group没有良好定义，所以只能说是long dream。

30-40年前的这方面故事还可以读一读Langlands写的Automorphic Representations, Shimura Varieties, and Motives，我就懒得写了。

然后，20年前的故事勉强算是现代数学，但是我已经浪费了快2小时，下次再说吧。这是一个很大的故事，不可能面面俱到，我也只是提一些有趣的例子。

不打算填的坑：

rationality, algebraicity (零零散散，C-algebraic，L-algebraic，1009.0785v3，Clozel)

The point of view from arithmetic subgroups and torsion story (以后再说)

Function field story (no trace formula)

对几乎所有p，Galois表示在p处的Frob记录了对应自守表示的Hecke operator at p的Satake parameter，那么自守表示at infinity在哪里被记录了？（real story）

注1：不怎么提motive是因为这并不是故事的重点，motive真正困难的是代数闭域上的理论（虽然Jannsen 1992早就证明pure motive模数值等价是半单Abel范畴），而motive本身并不能决定一个代数簇，例如两个isogenous的elliptic curves具有一样的pure motive。而在Langlands program里谈这个还是等同于考虑它的l-adic realization的L function，也就是说Galois表示。

注2：Langlands-Kottwitz里要实现对应，unitary Shimura varieties在real places的sign是非常重要的，必须是U(n,1)才会出来\pi \otimes \rho_{\pi}, 而U(n-1,2)会出来\pi \otimes \wedge^{2} \rho_{\pi}。这一点是很重要的，一般群的Auto-to-Galois很难再用Langlands-Kottwitz，因为Shimura variety对应的\mu是minuscule的，而minuscule cocharacter不一定生成所有dominant coweights，所以只能detect r{\mu} \circ \rho_{\pi} for all minuscule \mu，难以复现Galois表示，这使得问题更加困难。
