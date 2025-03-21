# 全局游戏设置

:::tip

这里是标签为「全局游戏设置」的分类下的设置项目。在这里您可以满足最基本的游戏启动设置需求，每一项设置在**具体的游戏**中若有特别的设置，将不会生效。详见: [版本隔离与独立设置](/zhCN/lxguide/settings/special/independent-config)

:::

[[toc]]

## Java虚拟机设定

*选择全局使用的Java，下载、搜索、管理Java运行环境*

###### **在账户页面固定账户**: `开关` | 默认:关闭.

开启此选项后，您在[账户管理](/zhCN/lxguide/settings/special/manage-accounts)页面**选中**的账户将被视为固定的账户，并在您点击任意一个地方的启动按钮时作为默认的账户来启动，并不会询问选择哪个账户来完成启动。开启后,主界面固定游戏的启动按钮后会有一个标签显示当前固定的用户名; 而游戏列表中的启动按钮将会在您的鼠标悬浮在其上的时候显示为您固定的用户名.



###### **Java路径**: `组合设置`

包含: 展示路径的选择框、`重新检查Java可用性`按钮；`重新搜索`、`深度搜索 (仅Windows)`、`手动添加`按钮:  使用选择框来选择一个全局使用的JRE以供启动。每一条项目均为被搜索到的Java，并且依次显示了「LauncherX对该Java可用性的判断」、「Java版本」、「该Java的完整路径」。选中的Java将使用主题色高亮显示，其版本信息将在选择框收起的情况下于下方并排着的2或3个按钮的下方可见.

**对于代表可用性的图标，有*四种可能*:**

- **&#xe8fb;** : 代表这个Java是完整可用的，并且适合您的操作系统;  

- **&#xe7ba;** : 代表这个Java存在问题，不建议使用它。通常可能是因为架构和当前系统不符(arm架构使用x64版本JRE、x64使用x32JRE都会使游戏体验大打折扣); 

- **&#xe8bb;** : 代表这个Java已损坏，或者LauncherX无法识别这个Java(如果您为了启动1.7.0以前版本的游戏而使用Java7，则可以忽略LauncherX的判断)。您可以使用下方的**下载Java**按钮来下载一个Mojang官方选择的适用于amd64架构的JRE，或者自行下载安装一个新的JRE。  详见: [[下载合适的JRE](/zhCN/lxguide/others/download-jre)]; 

- **&#xe895;** : 代表正在或此时无法或暂时没有运行对该Java的检查。无论如何您都可以通过选择框右侧的按钮来发起检查;

无论何时您都可以无视LauncherX的判断，但是使用LauncherX不认可的JRE有可能严重破坏您的游戏体验。由于我们的Java运行时检测机制是通过 “搜索-执行” 模式工作以确认该运行时是否可用，所以在您启动LauncherX时候，可能会遇到来自Java的错误弹窗。——您完全可以直接将它关闭，因为这并不影响LauncherX运行；且如果您没有选择任何一个被LauncherX判断为有问题的JRE作为游戏启动所使用的Java，那么您的游戏启动几乎不可能受到受损JRE的影响。由于每次LauncherX启动都会检查搜索到的JRE是否可用，因此您应该将该受损的运行时**移除**，或者用自动化窗口关闭工具（比如 火绒弹窗拦截）对错误弹窗进行精准打击。

如果您需要LauncherX不再显示某个特定的JRE，请点开选择框，右键点击包含那个JRE路径的项目，点击「排除」。

:::info 对于非Windows用户，在手动添加Java时，您可能需要注意赋予LauncherX足够的权限。

不建议直接用管理员命令启动LauncherX。<br>macOS用户若不得不使用SUDO启动LauncherX，则请使用命令:  

```bash
sudo open  <LauncherX.app的路径，可以拖入app包文件到终端窗口中来填充路径>
```

-------

“下载Java” 按钮、“查看CSKB文章” 按钮(仅在ARM架构系统中可见): 

前者可以选择下载一个Mojang官方选择的适用于amd64架构的JRE，或者自行下载安装一个新的JRE。  详见: [[下载合适的JRE](/zhCN/lxguide/others/download-jre)]

在这个设置项下方有一串文字用于显示LauncherX对选中的运行时的判断。比如: **该Java运行时(17.0.1)匹配您的系统**

:::warning 意外

如果那里显示了类似`picked JAVA_OPTS="xxx"`的文字，请在环境变量中寻找名为`JAVA_OPTS`的环境变量并删除，然后注销或重启系统。这可能是其他启动器创建的临时项目.

:::





## 游戏通用设定

*游戏内存大小、垃圾回收、窗口分辨率、JavaAgent参数、高级启动参数*

###### **内存大小**: `正整数` | 默认: 1024 | 单位: MB

在这个设置项的下方有较为明了的内存占比图示。基于您选择的LauncherX主题色，较深色的代表您电脑未被使用的内存量，较浅色的代表您电脑已被包括LauncherX在内的其他程序占用的内存量。

剩余一部分则是您全局分配给游戏的内存量在装机内存的总量中的占比。请注意，如果您分配的内存超出了空闲内存量，那么横条下方**空闲内存的实际数量将会显示为负数** (较新版本LauncherX将在内存超额的情况下使输入框的背景色呈淡红色)。

此外，针对不同版本的游戏，有不同的建议的内存大小。若内存分配量小于512(1.15.2更早版本游戏) 或小于1024 (1.15.2 ~ 1.17.x) 或小于1500 (1.18.x+)，都会带来游戏体验变差，甚至导致游戏无法启动。

::: info 关注电脑内存用量

错误的内存分配也会带来未知错误。同时，针对Mod和材质、光影包，应适量针对性地增加内存分配。  相关阅读: [配置内存和GC、JavaAgent](/zhCN/lxguide/others/adjust-ram-gc-ja)

:::

---

###### **游戏窗口设置**: `组合设置` 

- 游戏窗口标题：`文本输入框` | 默认：空

  用于修改游戏窗口的标题。
  :::tip 可用占位符

  通过使用这些占位符，可以在窗口标题中动态显示一些信息：

  - `%account%`：当前游戏启动用户名
  - `%launch_time%`：启动时的时间
  - `%game_name%`：所启动的游戏名

  :::

  ------

- 窗口大小: `正整数` &times; `正整数` | 默认: 0 &times; 0 | 单位: ppi?

  当此值为默认值 (即 0 &times; 0) 时，窗口大小将由游戏决定。

  ------

- 全屏: `开关` | 默认: 关

  这决定了游戏是否在启动时就以占满全屏幕的形式展现。
  请注意: 在游戏的全屏状态下 (而不是系统的全屏方案)，有些系统功能可能不可用 (比如Windows的系统截屏) 或出现异常表现 (如macOS可能出现退格键清除中文输入法候选时导致已输入内容被意外删除，或鼠标指针无法在游戏中隐藏)。
  
  -------

###### **GC设置和高级参数设置**: `组合设置`

- **启用GC**: `开关` | 默认: 开 | 控制垃圾回收器 (GarbageCollector) 启用与否

  建议保持开启状态。

  游戏在运行时候产生的不需要的内存借助GC进行清理和空间回收，籍由此来让内存利用更高效。除非您有开发者级别的必要的特殊需求，否则不建议关闭它.

  ------

- **GC类型**: `选择框` | 默认: G1GC

  LauncherX提供了几个常见的垃圾回收器可供选择。对于如何选择，参见: [配置内存和GC、JavaAgent](/zhCN/lxguide/others/adjust-ram-gc-ja)

  ------

- **Java虚拟机高级启动参数**: `文本输入框` | 默认: [空]

  额外的启动参数。您可以参考 [[优化配置: 启动参数](/zhCN/lxguide/others/args)] 作为指引.

  ------

- **JavaAgent设置**: `文本输入框`:路径 `文本输入框`:额外参数 | 默认: [空] [空]

  一般用户基本用不上它。这是JVM提供的一系列调试接口。参见:  [配置内存和GC、JavaAgent](/zhCN/lxguide/others/adjust-ram-gc-ja)

---

###### **启动后加入服务器**: `设置` | 入口

点击“管理服务器”按钮 进入对应的管理界面。详见: [功能: 服务器管理](/zhCN/lxguide/features/manage-server)

## 启动器行为

*游戏资源检查、原生库替换策略(ARM)、启动后行为、日志记录*

###### **检查游戏文件**: `开关` | 默认:  开

将在游戏启动的时候检查游戏的资源文件。如果您需要修改原版游戏的资源文件，相比于关闭此选项并直接修改assets，我们更建议您以资源包的形式覆盖。

---

###### 资源补全最大重试次数: `正整数` | 默认：3 | 取值范围：`1~10`

拖动以修改值。

当资源补全遇到个别任务失败，允许重试的最多次数。在网络条件较差的环境下，越高的重试次数将会提升补全完成后资源绝对完整的可能性。重试补全将花费额外的时间。

------

###### **使用快速资源检查**: `开关` | 默认: 开

通过更激进的优化算法来节省启动前检查时间。

------

###### **补全游戏文件时检查文件完整性**: `开关` | 默认:  开

在补全游戏资源文件的时候检查文件完整性。如果网络可能存在波动，则这个功能可以很好地确保下载文件的完整性，并降低游戏时出现故障的概率.

------

###### **原生库替换策略**: `选择框` | 默认: LegacyOnly

这个设置仅在ARM设备上可见，用于控制LauncherX在ARM设备上优化游戏体验的行为。有以下可选值:

- LegacyOnly: 仅对较老的不携带ARM版游戏支持库的游戏进行库文件替换。
- All: 对所有游戏使用原生库替换，即使游戏携带了ARM版支持库.
- Disabled: 对所有游戏都「**不**」使用原生库替换，即使是不携带ARM版支持库的游戏。(建议仅在替换后游戏出现问题的情况下使用此项目。)

较老版本的游戏不携带ARM版本运行库。为了尽可能发挥ARM设备的性能，可以使用支持ARM的游戏支持库 (LWJGL等) 

---

###### **游戏启动后启动器行为**: `选择框` | 默认: 最小化

选择让LauncherX主窗口和其他窗口 (除了日志窗口) 在一个游戏启动后的行为: 是“保持原状”、“最小化” 还是 “直接退出LauncherX”

------

###### **资源检查最大并行程度**: `选择框` | 默认: 4

在执行资源检查时同时进行的检查数量。可选值: 1、2、4、8。更多的数量将会占用更多的CPU资源，请根据您的CPU参数配置进行调整.

-------

###### **启动游戏时显示输出日志**: `开关` | 默认: 开

在启动游戏时是否显示游戏的日志窗口。详见: [[日志窗口功能介绍](/zhCN/lxguide/features/log-window)]

------

###### **启动器日志记录等级**: `选择框` | 默认: Error

可选(整体详细程度从高到低): All(全部输出)，Unknown(未知来源)，Debug(调试信息)，Info(一般信息-包括游戏内聊天信息)，Warning(警告)，Error(错误)，Fatal(致命错误);  Stacktrace(仅: 输出异常的完整溯源信息)，ExceptionMessage(仅: 输出异常的名称/和简单描述)(?)

:::info 关于日志窗口

日志窗口展示的最低等级。越低的等级会显示得越详细.

[了解更多关于日志窗口的信息](/zhCN/lxguide/features/log-window)

:::



