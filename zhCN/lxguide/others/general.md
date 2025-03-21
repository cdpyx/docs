# 常见名词解释

其他: 这里存放着一些解释文字的文字，和一些特性说明等其他内容.

[[toc]]

:::info

善用浏览器的页内搜索功能! 可以尝试组合键 `Ctrl + F` 或者 ` ⌘ + F `。如果是在手机上浏览，请试着在浏览器的功能菜单里找一找有没有搜索功能.

:::

## 游戏类

### 与Minecraft游戏运行相关的名词解释 

:::

###### 日志

在游戏尝试启动阶段、JRE(JVM)已启动的时候就会输出到游戏版本目录下logs文件夹中的.log文件或者.log.bz压缩包。如果LauncherX开启了[**游戏日志实时输出**](/zhCN/lxguide/features/log-window)功能，那么将会在其中展示实时的日志，方便人类可以读懂“游戏现在在干什么”。*这个词也可能是指由启动器产生的日志文件，请根据上下文判断。与此同时，存在名为“crash-report”的Forge崩溃报告与这个词有极大的联系，后者本质上也是一种日志，但是是用于分析Forge崩溃原因的。无论如何，请具体分析*.

----

###### 启动参数

在启动游戏时，附加给游戏的启动命令。*本页中「环境类」类别有相同的词，可以结合另一个释义深入了解*.

----

###### 待补充

2024年3月13日 最后更新





## 环境类

:::info 与计算机软件环境相关的名词解释。但是一般而言，这里只会解释和Minecraft相关的环境的名词。

:::

### 环境

计算机软件运行所需要的前置条件。*您可以把Mod的前置也理解为一种环境(的一部分)，但是一般而言的环境的定义比前置更大*.

---

### JRE

全称为「Java Runtime Environment」，Java运行时环境。这是运行Java软件必要的一套环境。一般而言，无论是一般的JRE还是JDK，其中都包含JRE，而JRE一般包含JVM(Java Virtual Machine，Java虚拟机)，这为Java的跨平台等特性提供了运行的框架。*很温暖，像家一样*…

---

### 启动参数

或使用更广泛范围下的说法: 「JVM参数/Java参数」。您需要将它和Java Agent作出区分，一般而言，要想优化游戏启动，只需要更改JVM参数。*对于JavaAgent设置的解释将在晚些时候LauncherX设置说明完成了「JavaAgent设置」分段后补充*。  -  这是在启动JVM时附加在启动指令末尾的一串以`-`开头、使用空格分隔的附加字符，一般而言是用于指定JVM运行行为的。所以如果使用得当，将会为您的Minecraft游戏带来更好的体验。比如，您可以通过附加`-Xmx5G` 来为Java程序设定最高使用**5GB**内存的限额(实际用量视设备可用内存和程序需要情况而不同。而指定内存已经由LauncherX在[全局游戏设置](/zhCN/lxguide/settings/item/global) 中提供了带有**可视化提示**的输入框可供直接使用.)  -  由于「但凡是使用JVM的程序，都可以使用JVM参数指定行为」，所以您同样可以用这种方法来优化其他在JVM中运行的程序或游戏(比如**Project Zomboid**，您可以在游戏目录中的`ProjectZomboid64.bat`中通过将默认的`-Xmx3072m`改到更大来允许游戏使用更多的物理内存.)

---

### JA

为了节省空间而使用的 **JavaAgent** 的缩写.

---

###### 待补充

2024年3月13日 最后更新





## Corona Studio

:::info 日冕工作室特色。

::: 

###### %*一切严格的按词分隔的“帕斯卡大小写”单词*%

可能是Rider对单词拼写的要求太严格了，或者老腊肉对帕斯卡大写法有种奇怪的执着，总之像「*Minecraft*」这样的单词在LauncherX中可能会呈现为「MineCraft」…

---

###### 吔!

这是个语气词! 但还是放进来了! 这是Corona Studio常有的! 发音和用法均同“耶!”!

---

###### 待补充

2024年3月13日 最后更新





:::info

想起来了会更新的。催更请发邮件到 [frigeso@icloud.com](mailto:frigeso@icloud.com)，告诉我您搞不明白哪个词。勘误也发到这个邮箱好了www

:::