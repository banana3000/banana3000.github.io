---
layout: post
title: 有限群概形的分类有什么用
---

classification of finite flat (commutative) group schemes over good base rings by (semi-)linear data是一个有趣的主题，这方面有很多值得一提的结果。非常粗糙的来说，这些结果既有整体算术上的应用，又有局部几何和Galois表示上的应用。

感觉很多人对这套东西的理解零零散散（知道几个结论，也串不起来），就随便聊一聊。

它们的证明是重要的（你可以从中看到技术的发展），但（对我来说）同样重要的是如何使用它们得到更多有趣的结果，发现新的概念。有了这些结果，通过一些hard computations in linear algebra，我们能得到意想不到的好东西。

工作太多了，就随便举几个早期的重要例子。

Dieudonne在1950s发展了Dieudonné theory，分类了perfect field上的finite flat group schemes，这是很多计算的基础。Grothendieck想得到分类的相对版本，他也注意到abelian variety over k的Dieudonne module和first de Rham cohomology存在很多联系，后来发明了crystal和crystalline cohomology.

Tate的p-divisible groups (1967年) 则是p-adic Hodge theory的开端，动机来自elliptic curves可以定义一串相容的finite group schemes，于是我们可以将一串finite flat group schemes拼凑，定义p-divisible group的概念。他证明了noetherian normal domain with char 0 fraction field 上的p-divisible group被其generic fiber唯一决定 (see theorem 4)。

Exercise: what can we say about p-divisible groups over Z_p[[T]] using this theorem?

Michel Raynaud 的Schémas en groupes de type (p,...,p) (1974年, over DVR with small ramification)发展了Tate-Oort的Group schemes of prime order (1970年, over a quite general base e.g over Z[\zeta_{p-1}, 1/(p(p-1))] \cap Z_p for p>2)的分类结果。

它们有很多应用，如用在Mazur分类rational torsion points of elliptic curves over Q的工作Modular curves and the Eisenstein ideal (1977年)（see the proof of theorem 5.1 e.g page 159）.

Exercise: classify finite flat group schemes of order 2 over any base by yourself.

Fontaine的Il n'y a pas de variété abélienne sur Z (1985年)得到了finite flat group schemes over p-adic integer ring / number field的Galois表示的一个ramification bound ，加上low ramification几个具体case的手动分类（计算），证明了there is no abelian variety over Z.

之后的故事就不说了，纯粹叙述结论而不讲动机或证明想法比较无聊，也不能过度纠结无关的细节。给一个报告，如何在1小时内把故事讲好，把新的重点突出，是很累的事，所以就以一个更现代的例子作为结束

Theorem. Let p>=3, and G be a finite flat commutative group scheme over Z. Assume G is killed by p and has order p^2 (like a 2-dim F_p vector space). Then G must be isomorphic to Z/p \oplus Z/p, Z/p \oplus \mu_p, \mu_p \oplus \mu_p.

这个结论不在Fontaine也不在Raynaud的paper里。但如果我们假定更现代的技术，这是很容易证明的，但注意这里的base是Z，并非纯粹的局部结果（so you can't get it by XXX big classification immediately）。这里就有意略去证明，希望能鼓励更多人了解新东西。
