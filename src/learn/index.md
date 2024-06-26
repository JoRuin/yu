<script setup>
import Chaifen from '@/chaifen/Chaifen.vue'
import MultiChaifen from '@/chaifen/MultiChaifen.vue'
</script>

# 前言

::: warning 终南捷径

如果你已经知道形码是什么，可以直接[从单字拆分开始学习](./division)。

如果你已经掌握了一种形码，可以直接[从宇码字根开始学习](./division)。

如果你想直观感受宇码拆分，可以直接[查看宇码的拆分图例](./examples)。

:::

## 汉字输入法

<MultiChaifen chars="漢字輸入法" :size="50" loc='left' />

汉字输入法，顾名思义，就是汉字（部首、笔画）录入进电脑中的方法。大多数时候，输入的过程，有两个阶段：

1. 用户将汉字，用一定规则，编成一串字母、数字、符号的组合，输入电脑中。
2. 输入法会串字符，根据一定的规则，转化为对应的汉字，显示到屏幕上。

::: info 定义

本教程中的「输入法」，特别指代上文中提到的第一阶段，亦即：用户将汉字，用一定规则，编成一串字母、数字、符号的组合，输入电脑中，并获得想要的汉字。
:::

### 输入法种类

输入法，根据其特点，一般分为三类

- 拼音（音码）
- 字形（形码）
- 音形（形音）混合。

<div class="flex justify-left flex-wrap">
<Chaifen char='音' :parts='[5,4]' />
<Chaifen char='码' :parts='[5,3]' />
</div>

**音码输入法**，最常见的例子就是拼音。我们将汉字对应的拼音，直接输入到软件中，软件会显示对应的汉字供你选择。这其中包括了一个反馈的过程，即：输入字母——获得候选——输入数字——获得汉字。
<div class="flex justify-left flex-wrap">
<Chaifen char='形' :parts='[4,3]' />
<Chaifen char='碼' :parts='[5,10]' />
</div>

**形码输入法**，最常见的例子是五笔字型。我们将汉字拆成若干部件，输入每一个部件对应的代码，软件会显示出汉字。常见的形码，还包括五笔字型，郑码，仓颉等等。这其中有时包括了一个反馈的过程，但因为形码的确定性，大多数时候是不需要确认的，即：输入字母——获得汉字。

::: info 注意

判断一个输入法是音码还是形码的最简单的方法，就是：对于**任意**一个汉字，不用知道它**本身**的读音便能输入。

因此，「宇浩」繁简通打输入法，是一种形码输入法。
:::

### 形码和音码的对比

形码输入法和拼音最大的区别，在于拼音输入法，知道读音，便能输入汉字。而形码输入法，知道写法，便能输入汉字。

音码的优点，便是像**说话**一样去打字。你只要知道标准的发音，便可以打出字来。同时，汉语拼音也是当代人的必修课，不需要特别地学习，因此，它的学习成本近乎为零。

音码的缺点，那便是同音字很多，经常需要选字。虽然当代的不少输入软片在「智能化」上下足了工夫，但在输入一些书面语、古文、或者生僻字词时，还是需要选字。大量翻页会打输入的节奏。笔者正是因为写小说时候被翻页打断思路而使用了形码。

<MultiChaifen chars='優點' loc='left' />

形码的优点，便是像**写字**一样去打字。你不需要知道每个字的具体读音。同时，因为编码比较离散，你甚至不怎么需要去选字。这在写作时，保证你的思路不被打断。在看打、或者打古文的时候，形码的速度很快。

<MultiChaifen chars='缺點' loc='left' />

形码缺点是，如果你一下字忘了这个字的写法，那就会卡住，必须临时改用拼音输入法（反查）。

至于音码和形码哪个更好？这就是仁者见仁、智者见智的问题了。当然，也依赖于你的需求和使用场合。笔者在日常对话时使用全拼，在写作时使用形码，做到扬长避短。

## 宇浩输入法特点

「宇浩」作为一种**形码输入法**，除了继承了刚刚所说的形码的全部重点外，还有一些自身的特点。这些特点，自然受到了笔者偏好的影响。这里仅举例一二：

- 大字集。也就是说，用「宇浩」可以打出所有的汉字（CJK + 部首 + 笔画），并且有 99000 多个汉字的单字拆分，且一直保持保持更新维护。
- 繁简通。也就是说，你可以直接打出繁体汉字和简化汉字。繁简字根不占用同一个码位，因此繁简混输的时候也很少选字。
- 低重码。也就是说，每个编码一般只对应唯一的候选项，你不需要进行选字，可以不用打断思路地进行输入。
- 手感好。笔者不喜欢使用 Z 键，所以这个键位被空了出来，用于反查或其他功能。

这里对比一下五笔、郑码、宇浩等十余种常见输入法在不同汉字字符集下 [重码数据](../docs/statistics)，供大家参考。

## 学习步骤

学习「宇浩」，一般从了解拆字和熟悉字根开始。

拆字，就是把汉字按照一定的规则，拆成唯一的部件组合。拆分出来的部件，便叫做「字根」。字根不仅包括你我熟知的「偏旁部首」，也包括了一些基本笔划，甚至是一些汉字。因此，笔画输入法（横竖撇捺折），也是一种特殊的形码。那么我们为什么要创造别的形码呢？因为一个字若用十几个、甚至几十个字母代替，太没有效率。故而，我们会截取一些比较大的部件作为字根。

对于汉语使用者，拆字并不是一件陌生的事情。我们自小就学会将一个字拆成分离的部首，进行检索。大多数时候，这是非常直观的。

::: tip 例

`部`字，大家会自然地将他拆分为`立口阝`三个部分。  

`程`字，大家会自然地将他拆分为`禾口王`三个部分。  
<div class="flex justify-left flex-wrap">
<Chaifen char='部' :parts='[5,3,2]' />
<Chaifen char='程' :parts='[5,3,4]' />
</div>
:::

对于「宇浩」而言，大多数的字，也是这么拆分的。并且大多数的偏旁部首，也都是「字根」。所以恭喜你，对于大多数的汉字，你已经可以凭借直觉进行拆分了。

本教程推荐的学习步骤如下。

1. 了解「宇浩」拆字的规则，学会如何得到唯一的拆分方法。
2. 看字根图，**大致**了解「宇浩」的字根有哪些，以及它们对应的编码。
3. 学习编码规则，学会如何将拆好的字根转化成最终的「宇浩」。
4. 记诵**最常用的 100 个字根**的编码（可以基本输入最常用的 500 个汉字）。
5. 直接在输入软件中练习前 500 常用字（覆盖了 77% 的字频），边练习边记忆字根。
6. 阅读进阶教程，更加深入地了解一些「宇浩」的特点。

以上内容不论顺序，可以交叉或同步进行。
