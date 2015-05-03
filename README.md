TextRank
========

TextRank算法提取关键词与自动摘要的Java实现

## 注意

**TextRank已经集成到[HanLP](https://github.com/hankcs/HanLP)中，本项目不再维护。**

TextRankKeyword提取关键词
--

 - 调用方法
 
```java
public static void main(String[] args)
{
    String content = "程序员(英文Programmer)是从事程序开发、维护的专业人员。一般将程序员分为程序设计人员和程序编码人员，但两者的界限并不非常清楚，特别是在中国。软件从业人员分为初级程序员、高级程序员、系统分析员和项目经理四大类。";
    System.out.println(new TextRankKeyword().getKeyword("", content));
}
```
 - 算法详解
 TextRank是在Google的PageRank算法启发下，针对文本里的句子设计的权重算法，目标是自动摘要。
 详见[《TextRank算法提取关键词的Java实现》][1]
 - 关于分词
  分词不是TextRank关注的重点，项目中的警告是分词库发出，不影响功能。

TextRankSummary自动摘要
--
 - 调用方法
 
```java
 public static void main(String[] args)
 {
    String document = "算法可大致分为基本算法、数据结构的算法、数论算法、计算几何的算法、图的算法、动态规划以及数值分析、加密算法、排序算法、检索算法、随机化算法、并行算法、厄米变形模型、随机森林算法。\n" +
                "算法可以宽泛的分为三类，\n" +
                "一，有限的确定性算法，这类算法在有限的一段时间内终止。他们可能要花很长时间来执行指定的任务，但仍将在一定的时间内终止。这类算法得出的结果常取决于输入值。\n" +
                "二，有限的非确定算法，这类算法在有限的时间内终止。然而，对于一个（或一些）给定的数值，算法的结果并不是唯一的或确定的。\n" +
                "三，无限的算法，是那些由于没有定义终止定义条件，或定义的条件无法由输入的数据满足而不终止运行的算法。通常，无限算法的产生是由于未能确定的定义终止条件。";
    System.out.println(TextRankSummary.getTopSentenceList(document, 3));
 }
```
 - 算法详解
 通过句子的相关程度（BM25相关度）决定票的权重，迭代投票得出最终权重。
 详见[《TextRank算法自动摘要的Java实现》][2]

TODO
--
- 自然语言处理任重道远，本项目只是对TextRank的一份简明实现，效果和性能请自行评估。
- 我写了[一系列入门笔记][3]，欢迎NLP领域的朋友[前来交流、指导我的学习][3]。
- 事实上，我正在开发一个完备的汉语处理包，目前能够提供分词、词性标注、命名实体识别、关键字提取、短语提取、自动摘要、自动推荐等功能，未来可能开源并逐步实现依存关系、句法树等功能，敬请期待。

  [1]: http://www.hankcs.com/nlp/textrank%E7%AE%97%E6%B3%95%E6%8F%90%E5%8F%96%E5%85%B3%E9%94%AE%E8%AF%8D%E7%9A%84java%E5%AE%9E%E7%8E%B0.html
 [2]: 
http://www.hankcs.com/nlp/textrank-algorithm-java-implementation-of-automatic-abstract.html
 [3]: 
http://www.hankcs.com/category/nlp/