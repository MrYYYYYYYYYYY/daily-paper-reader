---
title: Binary search and set operations on compacted k-mer lists
title_zh: 压缩k-mer列表上的二分查找和集合操作
authors: "Dufresne, Y., Andreace, F."
date: 2026-07-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735436v2.full.pdf"
tags: ["query:lpt"]
score: 7.0
evidence: 将排序k-mer表示为虚拟超k-mer，实现高效集合操作
tldr: 在生物信息学中，k-mer集合操作需要高效数据结构，现有方法如KMC存储单个k-mer导致内存开销大。本文提出将排序k-mer表示为重组super-k-mer的排序列表，并引入虚拟super-k-mer概念，支持高效构建、查询和集合操作。在sklib实现中，数据结构的构建和集合操作吞吐量高，查询性能有竞争力，内存占用仅为KMC的2-5倍（bits/element）。该工作提供了一种内存高效且快速的k-mer集合操作工具，降低了内存需求同时保持高性能。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735436-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1074, \"height\": 192, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735436-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 995, \"height\": 229, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735436-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1182, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735436-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1179, \"height\": 451, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735436-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1188, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735436-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1258, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735436-v2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1619, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735436-v2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 921, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735436-v2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 599, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735436-v2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 605, \"height\": 261, \"label\": \"Table\"}]"
motivation: 现有k-mer集合操作工具内存开销大，需要更紧凑的表示方法以减少存储成本。
method: 引入虚拟super-k-mer概念，将排序k-mer重组为super-k-mer排序列表，支持二分查找和集合操作。
result: sklib实现中，内存占用降低至KMC的2-5倍，构建和集合操作吞吐量高，查询性能有竞争力。
conclusion: 提出一种紧凑的k-mer表示方法，实现了低内存下的高效集合操作。
---

## 摘要
有序元素列表特别适用于计算集合操作。只需一次扫描两个列表即可实现并集、交集、差集和异或操作的结果的具体化或计数。在生物信息学中，专门设计用于对k-mer执行这些操作的工具很少。像KMC这样的快速工具可以以存储单个k-mer为代价进行集合操作。

在本文中，我们引入了一种新的方法来表示排序的k-mer，即作为重组超k-mer排序列表的集合。我们引入了虚拟超k-mer的概念，并展示了如何在虚拟超k-mer的有序列表上构建、查询和执行集合操作。

在实现sklib中，我们展示了该数据结构在构建和集合操作上的高吞吐量，同时在查询能力方面保持竞争力，并且内存占用可控（与KMC相比，每个元素的位数减少了2-5倍）。

## Abstract
Sorted lists of elements are particularly good for computing set operations. A single scan of the two lists is sufficient to materialize or count the results of the union, intersection, difference, and xor operators. In bioinformatics, only a few tools are designed to perform these operations on k-mers. A fast tool like KMC allows set operations at the cost of storing individual k-mers.

In this paper, we introduce a novel way to represent sorted k-mers as a collection of recomposed super-k-mer sorted lists. We introduce the concept of virtual super-k-mer and show how to construct, query and perform set operations on sorted lists of virtual super-k-mers.

In the implementation sklib, we demonstrate high throughput of the data structure for construction and set operations, while remaining competitive in query capabilities, within a controlled memory footprint (2-5x decrease in bits/element compared to KMC).