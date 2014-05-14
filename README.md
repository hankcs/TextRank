TextRank
========

TextRank算法提取关键词的Java实现
----------------------

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

  [1]: http://www.hankcs.com/nlp/textrank%E7%AE%97%E6%B3%95%E6%8F%90%E5%8F%96%E5%85%B3%E9%94%AE%E8%AF%8D%E7%9A%84java%E5%AE%9E%E7%8E%B0.html