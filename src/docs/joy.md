# 卿雲爛兮

::: warning 注意
本方案基于宇浩拆分，为 25.5 键乱序单编、繁简通打方案。初始学习难度较大，请务必充分了解、分析、平衡其风险和收益后再决定是否学习使用。
:::

## 简介

卿雲爛兮是宇浩输入法的**乱序单编**衍生方案。方案名取自《尚書大傳》之「卿雲爛兮，糺縵縵兮」。取码规则共两条：

1. 依次取第一、二、三、末字根对应的编码；
2. 不足四码时，输入一个补码，即末根读音。

::: info 公式化规则
所以，根据字根数量，有以下几种形式。设首根为 A，次根为 B，三根为 C，末根为 Z，读音为 v。

1. 单根字：Zv
2. 双根字：AZv
3. 三根字：ABZv
4. 多根字：ABCZ
:::

本方案的**补码**，是末根的读音首字母，**没有读音**则默认为 v。唯一的例外是高频`口`字根，虽然读音为 k，但当作没有读音处理。

::: tip 卿云取码歌诀  

一二三末取字根　单根成字即自身  
双根便作首和末　三根首二同末存  
字根表中找编码　二十五键莫看岔  
依次填入根字母　不足四码加补码  
补码就是末根音　以下法则心里记  
鱼化ｖ来衣作ｉ　口补ｖ外无特例  
:::


| 末根补码 | 规则                     | 举例                      |
| :------- | :----------------------- | ------------------------- |
| v        | 频率最高的字根，补码为 v | `口`                      |
| v        | 读音为 ㄩ 的，补码为 v   | `鱼魚雨禺予 月曰`         |
| i        | 读音为 ㄧ 的，补码为 i   | `一乙已乂弋亦衤 言羊用夭` |

字根是有限的，因此本方案依旧是纯形方案，不是形音方案。

本方案**繁简通打**，其关键数据如下：

- 简体动态选重率 0.079%
- 繁体动态选重率 0.079%
- 繁简混合动态选重率 0.134%
- 全码速度当量 1.27，简码速度当量 1.28
- 单字平均双手互击率 > 65%，连续文本双手互击率 > 45%

以下为本方案的字根图。有可能作为末根的生僻部首，图上标注其读音，以供参考：

[![yujoy](/yujoy.png)](/yujoy.png)

## 优缺点

本方案编码**乱序**，200多个字根的在25键上随机出现，相比「光華」「星陳」两个方案，优缺点都十分突出，故总结如下：

### 缺点

- 初始学习难度较大，同键位字根之间的字形关系不强，难以进行相似字形联想记忆。
- 双根字全码为三码，对于大字集来说，静态重码较高。
- 双根字需要按空格，无法四码顶屏，因此拇指压力增大，不适合腱鞘炎患者。

### 优点

- 字形相近的部首在键盘上离散。因此，字根编码中可以包含更多信息，使得规则的复杂度较低。
- 编码随机分布，有利于分散双手互击，提高理论击键速度当量。
- 补码严格取字根读音，对于日常使用拼音或注音的人比较友好。

## 数据

见[《常见输入法重码数据》](./statistics.md)

## 对比

以下是本方案同「光华」「星陈」在各个维度上一个大致的对比：

- 简体白话文：光华 > 星陈 ≈ 卿云
- 繁体白话文：卿云 ≈ 光华 ≈ 星陈
- 繁简白话文：光华 ≈ 卿云 > 星陈
- 古代文言文：星陈 > 光华 > 卿云
- 字根容易度：星陈 > 光华 > 卿云
- 规则容易度：卿云 > 星陈 ≈ 光华
- 手感舒适度：卿云 > 星陈 > 光华
- 简码效率值：星陈 > 光华 > 卿云

| 特点                       | 光華 | 星陳 | 卿雲 |
| :------------------------- | :--- | :--- | :--- |
| 使用最新版本宇浩拆分       | ✅    | ✅    | ✅    |
| 繁简通打低极选重率 (<0.2%) | ✅    | ✅    | ✅    |
| 字根字重复小码             | ✅    | ✅    | ❌    |
| 两根字取首根小码           | ✅    | ✅    | ❌    |
| 大码使用 Z 键              | ❌    | ❌    | ❌    |
| 小码使用 Z 键              | ❌    | ✅    | ✅    |
| 相似字形字根同分区聚类     | ✅    | ❌    | ❌    |
| 相似字形字根同大码聚类     | ❌    | ✅    | ❌    |
| 小码 >85% 使用拼音首字母   | ❌    | ✅    | ✅    |
| 小码 >99% 使用拼音首字母   | ❌    | ❌    | ✅    |
| 双手互击率 >60%            | ❌    | ✅    | ✅    |
| 严格优化键位分布           | ❌    | ✅    | ✅    |
| Z 键反查                   | ✅    | ✅    | ✅    |

## 作者

钱多多，为主要策划人、项目发起人、测试员、制图员、皮肤设计者、社区维护者。

forFudan，提供字根排布计算和技术支持。
