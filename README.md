3d-bin-pack //3d-箱-打包
===========

A set of C programs that calculate the best fit for boxes on a pallet, and visualize the result.  //计算+可视化

Reference Implementation of the EB-AFIT Pallet Loading Algorithm  //EB-AFIT Pallet 加载算法
----------------------------------------------------------------

The algorithm described in the thesis document (see *History and Future*, below) has been retroactively named the EB-AFIT Pallet Loading Algorithm, in honor of its author and the institution where he performed his research.  Since the code in this repository is directly transcribed from the appendices accompanying the thesis, these code files should be considered the [reference implementation](https://en.wikipedia.org/wiki/Reference_implementation) of the algorithm.  //后来被追溯命名为 EB-AFIT Pallet 加载算法，致敬🫡它的作者以及 作者所执行研究 的组织，美国🇺🇸空军技术学院 

History and Future  //历史与未来
------------------

These files represent an obscure little piece of history. While researching bin packing algorithms, I came across this Air Force Institute of Technology master's thesis (included in this repository in doc/) by Erhan Baltacıoğlu, B.S, who was then a First Lieutenant of the Turkish Air Force. This thesis described and documented a heuristic algorithm for finding the best way to pack boxes into a pallet of given dimensions.  //这些文件代表复杂历史的一瞥。当 研究 打包装箱算法 的时候，遇到这个 美国空军技术学院 的硕士论文 （包括在这个代码库中）作者 Erhan Baltacıoğlu 是土耳其空军中尉。这篇论文描述 并 记录了一个在给定尺寸中通过启发式 算法 找到最优包装盒的方法

The document is typical of a thesis in that it describes the problem, looks at extant solutions to the problem and analyzes the pros and cons to each extant solution, then describes a different (presumably better) approach to solving the problem, and then provides implementation details.  The implementation details are described prosaically, but then the document has several appendices which go into implementation detail with pseudocode and C programming code, as well as test and result sets. //文件📃是一个典型的论文范式：描述了一个问题，寻找现行解决方案 并对 现行解决方案做 优势 与 劣势 分析，并且描述一个不同（大概是更好地）方法来解决这个问题，并且提供 实施 细节。 实施细节 被乏味地描述，但是 文件有许多附录 通过 伪代码 和 C 程序 深入实施的细节

The PDF was scanned in as an image and ran through an OCR routine at some point.  I was interested in seeing if I could make the C code run, so copied and pasted the C code into an IDE and set to work fixing the OCR errors and formatting the code in a way that was a bit easier to follow (I'm certain the code was formatted in such a way as to fit onto 8.5" x 11" sheets of paper). //

It took me about 2 days to get the main bin packing code to a point where it would compile and run identically to that described in the thesis, and an additional day to get the visualizer to build and run.  The bin packing code is somewhat windows-specific (utilizing conio.h and malloc.h, with Microsoft specific functions getch() and kbhit()), and will only compile as-written using Microsoft compatible tools.  Specifically, I used the command line compiler (cl) that is distributed with the Microsoft Visual Studio 2010 to get binpack.c to build. The visual.c code is even more obscure in that I had to find, download, and install an archaic version of Borland Turbo C 2.01 in order to get it to compile.

Much to Microsoft and Borland's credit, by the way, is the fact that Turbo C would still run and fully function on Windows 7.

There is much that could be done with this code.  There are aspects of it that I find to be clever and original.  My current plan is to [fork it](https://github.com/thebitpusher/boxologic) (I want to leave this repo as it is for posterity), then begin the process of making it more portable and adherent with modern programming practices.  I'd also like to make it more generically applicable - for example to packing packages inside boxes, and have multiple boxes available for choosing, instead of just boxes on a fixed pallet.

Thanks
------

I am grateful to Mr. Ehran Baltacıoğlu for choosing to tackle a difficult but widely-applicable problem to conduct his master's research on; to the US Air Force, the Air Force Intitute of Technology, the Turkish Air Force, and whatever program was in place that allowed Mr. Baltacıoğlu to carry out his postgraduate degree program with the Air Force Institute of Technology.  This code base has seen more activity than I ever expected, and I'm genuinely pleased to see it enduring.

I would also like to thank Raymond R. Hill, PhD, Lt Col (USAF, Ret) - the original thesis reader and one of two gentlemen that helped guide Mr. Baltacıoğlu as he performed his research - for pointing me towards the academic publication of Mr. Baltacıoğlu's work. You can check your local university or municipal library for the full text of [The distributor's three-dimensional pallet-packing problem: a human intelligence-based heuristic approach](http://www.inderscience.com/dev/search/index.php?mainAction=search&action=record&rec_id=9300&prevQuery=&ps=10&m=or).
