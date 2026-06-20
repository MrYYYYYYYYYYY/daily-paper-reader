---
title: A run-length-compressed skiplist data structure for dynamic GBWTs supports time and space efficient pangenome operations over syncmers
title_zh: 一种用于动态GBWT的游程编码跳表数据结构，支持基于syncmer的时间空间高效泛基因组操作
authors: "Durbin, R."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.26.714584v2.full.pdf"
tags: ["query:lpt"]
score: 7.0
evidence: 提出基于跳表的新型动态数据结构实现高效泛基因组操作
tldr: 当前基于图BWT（GBWT）的泛基因组搜索方法为静态实现，构建和使用繁琐。本文提出一种基于游程压缩BWT的跳表数据结构，支持对数时间复杂度的rank/access和动态插入操作。在92个人类基因组上构建了5.8GB无损GBWT表示，单线程52分钟完成，搜索速度约每秒1亿碱基。该工作为同步图上的路径存储与搜索提供了高效的动态方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有GBWT实现静态，无法高效支持动态泛基因组操作，需一种可动态构建和更新的数据结构。
method: 提出运行长度压缩BWT的跳表变体，支持O(log N) rank/access和O(log N+S)插入操作。
result: 在92个人类基因组上构建5.8GB无损GBWT表示，单线程52分钟；搜索速度约1Gbp/10秒/线程。
conclusion: 该动态跳表结构实现了时间和空间高效的泛基因组路径存储与搜索，可应用于同步图。
---

## 摘要
跳表（Pugh, 1990）是一种基于有序列表的概率数据结构，支持[O]（log N）的插入和搜索操作，与平衡二叉树具有许多共同特性。此前我们引入了图Burrows-Wheeler变换（GBWT）来支持对泛基因组路径集合的高效搜索，但当前的实现是静态的，构建和使用较为繁琐。本文提出了一种基于游程编码BWT的双向链表跳表变体，支持[O]（log N）的rank和access操作，并进一步提出了其动态版本，支持[O]（log N + S）的rank和insert操作，其中S是字母表中的符号数量。我们利用这些结构来存储和搜索通过由Edgar闭合syncmer构建的syncmer图的路径，该图等价于稀疏的de Bruijn图。代码位于github.com/richarddurbin/syng的syng包中的rskip.[ch]文件。以此为基础，我们在37分钟内构建了一个4GB的63bp syncmer集合，并在其上以单线程52分钟构建了92个完整人类基因组的5.8 GB无损GBWT表示。随后可以找到任意长的最大精确匹配（MEM）作为序列与图匹配的种子，搜索速度约为每线程每10秒1Gbp。

## Abstract
Skiplists (Pugh, 1990) are probabilistic data structures over ordered lists supporting [O] (log N) insertion and search, which share many properties with balanced binary trees. Previously we introduced the graph Burrows-Wheeler transform (GBWT) to support efficient search over pangenome path sets, but current implementations are static and cumbersome to build and use. Here we introduce a doubly-linked skiplist variant over run-length-compressed BWTs that supports [O] (log N) rank and access operations, and a dynamic version of this that supports [O] (log N + S) rank and insert operations, where S is the number of symbols in the alphabet. We use these to store and search over paths through a syncmer graph built from Edgars closed syncmers, equivalent to a sparse de Bruijn graph. Code is available in rskip.[ch] within the syng package at github.com/richarddurbin/syng. This builds a 5.8 GB lossless GBWT representation of 92 full human genomes, single-threaded in 52 minutes, on top of a 4GB 63bp syncmer set built in 37 minutes. Arbitrarily long maximal exact matches (MEMs) can then be found as seeds for sequence matches to the graph at a search rate of approximately 1Gbp per 10 seconds per thread.