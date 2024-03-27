# 进阶讨论

## 字形选取的标准

汉字具有多态性。同一个汉字，在不同的标准、不同的字体下，存在一定的差别。有些字形上的差别，通过 Unicode 的离散来实现。比如「户」「戶」「戸」三字，在 Unicode 里被安排在了不同的码位上，故而实现了分离。但是很多汉字的不同字形，却共用 Unicode 码位（这其实是 CJK 的初衷），那么这个字到底应该依照哪个标准来拆分，便成了问题。

宇浩输入法的规定是：

- 每个字都有一种**标准拆法**，字形标准取自：The Unicode Standard, Version 15.0。各地区优先级降序为：GTHJKV，即陆、台、港、日、韩、越。也就是说，如果存在大陆提交的标准，就依照大陆标准。如果大陆没有提交标准，就按照台湾标准。依此类推。
- 每个字都可能有若干**兼容拆法**，目的是兼容台湾、香港、大陆古籍的字形标准。比如「起=走己」（大陆标准）和「起=走巳」（台湾标准）兼收。

宇浩输入法的笔顺选取，依照大陆标准《GF 3003-1999 GB13000.1 字符集汉字字序（笔画序）规范》。同时，也兼容台湾标准的笔顺。比如「攀=木乂乂木手」（大陆标准）和「攀=乂乂木木手」（台湾标准）兼收。

## 字根的内在属性

上面我们提到了宇浩输入法拆字规则的优先级。其实，在「字根最少」之上，还有一个隐藏的原则，也就是：**字根的内在属性**。

何为字根的内在属性？其实就是指某一个字根区别于另一个字根的内在特点。

::: tip 例
「吉」拆成「士口」而不是「土口」，这是因为「土」的下面一笔更长，而「士」的下面一笔更短。这是区别两个字根的本质原因和内在属性。
:::

「内在属性」可以解释为什么有些字这样拆而不是那样拆，有些字为什么看上去违反了「字根最少」的原则。

::: tip 例
「敝」拆为「丷巾八攵」而非「氺巾攵」，这看似违反了「字根最少」原则，但其实没有。注意到，「敝」字左下的笔画是撇不是提；在「氺」中，左下角的笔画是提不是撇。故而，「敝」字里并不存在「氺」字根。正因为如此，我们取四根「丷巾八攵」而非三根「氺巾攵」。
:::

在这个章节，我们就详细讨论字根的内在属性，讨论某些字根在宇浩拆分中被分离或者被合并的原因，从而让某些字的拆分原因更加明确。

### 日曰之辨

不少输入法对与「日」「曰」两字的区分，比较复杂。大概有两种情况：

- 有些是基于形状的，凡是长大于高的都为「曰」，凡是长短于高的都为「日」。但这个方法会跟随着字体的不同而不同，有时候不合字源，也不统一。例如：「書」字源于「聿者」，徐码中「書」下为「曰」，但「者」下为「日」，取码不统一。「曹」古字为「东东口」。在徐码中，「曹」下为「日」，不符合字源。
- 另外一种区分方法是基于字源。也就是说：凡是在古文中作「口」形，之后隶变为「曰」形或「甘」形的字，都作「曰」。但这个方法对方一般的使用者难度太大，且分析字源会有疏漏之处，不应用于输入法。

我们必须注意到，在汉字中，存在「日曰」对立的字形，只有三组，分别为：「日曰」、「汨汩」、「曶㫚」。在其他的情况下，不存在对立，也就不存在混淆问题。

因此，我基于**实用主义**原则，对这两个字根不多加以区分，而采取更简单的方法。即：除了上述三组对立情况外，全部取「日」根。换句话说，「曰」根只需要在对立情况下才会使用，包括：「曰」「汩」「㫚」三个字。

这样一来，可以显著降低使用者的记忆和学习负担。

### 勹𠂊之辨

「旬」的外框「勹」，同「敖」左下的「𠂊」都是撇加横折钩。宇浩输入法不做区分。

### 点

这里对「点」的拆分作出解释：

- 单点和捺视为一个字根。
- 相重叠的两点，即「头」「冬」中的部分，同「二」。
- 左对点「冫」和右对点「飞右」，同「二」。故而「兆」拆为「儿二二」。
- 下对点「八」为一个字根。
- 上对点「丷」「䒑」「リ」在一个大码。
- 左「⺦」为一个字根。
- 所有三点都在一个大码。
- 所有四点都在一个大码。

「为」「卵」等字的两点和「冬」下的两点不同，相隔太远，且被半包围或全包围分割，故而不认定为「两点」。

### 人八入之辨

「人」「八」「入」三字易混，这里做出区分：

- 凡左撇不低于右捺，作「人」。
- 凡左撇低于右捺，作「入」。
- 凡左撇右捺分离，或者中间被其他笔画隔开，作「八」。

### 口中无整画

口（音`kǒu`），囗（音`wéi`）。这两个根如何区分？

答案是，如果方框里有**完整**的笔画，用「囗」`wéi`。否则一律用「口」`kǒu`。

::: tip 例
「国」字中，有完整的笔画，故而必须用「囗」`wéi`。
「中」字中，虽然「⼁」穿「口」而过，但并未被完全包含在「口」中。由于「口」中没有完整的笔画，故而用「口」`kǒu`。
:::

此规定也适用于另外几个包含「口」的字根。

::: tip 例

- 「古」下的「口」中如果包含完整的笔画，应该拆如「十囗」。例如：「鄙」左下方的「口」中有「口」，故而应该拆成「口十囗口阝」。
- 「合」下的「口」中如果包含完整的笔画，应该拆如「人一囗」。例如：「會」中間的「口」中有「小」，故而应该拆成「人一𫩏丷日」。
:::

## 汉字的拆分禁手

拆分之「禁手」，指的是无论任何时候都不应当出现一些拆分情形。它高于一切拆分规则。一旦某一个拆分候选中出现了「禁手」，则直接淘汰。禁手包括：散件不分割、竖向不包夹、横间不穿心。

### 散件不分割

有一部分字根，本身存在离散的部件，比如「戈」字右上的点、「犬」字的右上的点、「三」字的三个横等等。为了保证拆字的直观，保证检字（尤其是大字集下）的便捷性，我们需要对字根的连续性做出要求，并将它认定为字根的内在属性。

字根的连续性定义如下：

一个字根的离散部件，不可被全包围结构或半包围结构分割。被分割的两个部件不得视为一个字根。

::: tip 例
「为」字的两点不可以被视为字根「两点」，因为它们被半包围结构分割。  
「曵」字不拆「囗戈」而拆成「电丿丶」，因为「戈」字右上方的点被全包围结构分割。
:::

### 竖向不包夹

不少字根中存在若干分散的部件，比如：

- 「二」和「三」中的横画是分离的。
- 「合」分为了「一」「一」「口」三个部分。
- 「儿」分为了「丿」「乚」两个部分。

这给了它们包夹其他字根的可能。如「亘」可看成「二」包夹「日」。

为了防止拆分不直观，我们做出规定，一个字根**可以横向包夹，但不能纵向包夹**。

::: tip 例
卿 = 卯彐厶  
胤 = 儿幺月  
亘 = 一日一  
僵 = 亻一田一田一  
:::

这是因为，汉字的左右对称多于上下对称。左右包夹是可预测的，但上下包夹往往不可预测，必须要观察到最下方。比如，某些输入法设置了「衣」字根，但「亠」和「𧘇」的出现并不总是成对的，必须看到最下方才能正确判断。

### 横间不穿心

为了使拆分更加直观，符合笔顺，防止字根交叉粘连，我们规定：

「工土士干千禾キ王壬龶丰末未生古矢缶早羊虫」等字根不允许在「一一」间穿插其他字根。

这个规定在常用字中比较少用。

::: tip 例

- 「再」不拆「王冂」，而拆「一冂土」
- 「垂」不拆「壬龷」，而拆「千龷一」
- 「夀」不拆「龶乛口口寸」，而拆「二乛口丄口寸」
- 「禹」不拆「丿虫冂」，而拆「丿口冂<丄丶>」

:::

<!-- #### 两根不四分

如果两个字根 A 和 B 存在相交笔画，也就是说它们构成一个独体部件。那么，允许先写 A 的一部分，再写 B，再写 A 剩下的一部分。但不允许两个字根分四次写成。这是因为笔画过于交织的拆分方案往往不直观。

::: tip
「華」字不拆「艹丌丰」，因为先写了「丌」的横，再写了「丰」的横，再写完「丌」剩下的两竖，再写完「丰」剩下的笔画。两个字根分成了四个部分。  
「曵」字不拆「囗戈」，因为先写了「口」的「冂」，再写了「戈」的横，再写完「口」剩下的一竖，再写完「戈」剩下的笔画。两个字根分成了四个部分。  
「妻」字不拆「キコ女」，因为先写了「キ」的横，再写了「コ」的折，再写「キ」的横，再写完「コ」剩下的横，再写「キ」的竖。两个字根分成了五个部分。   -->