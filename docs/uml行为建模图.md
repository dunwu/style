# 行为建模图

<!-- TOC depthFrom:2 depthTo:2 -->

- [2.1. 用例图](#21-用例图)
- [2.2. 顺序图](#22-顺序图)

<!-- /TOC -->

## 2.1. 用例图

**用例模型** - 用例模型用来记录系统的需求，它提供系统与用户及其他参与者的一种通信手段。

**执行者** - 用例图显示了系统和系统外实体之间的交互。这些实体被引用为执行者。执行者代表角色，可以包括：用户，外部硬件和其他系统。执行者往往被画成简笔画小人。也可以用带«actor»关键字的类矩形表示。

<div>
<img src="http://upload-images.jianshu.io/upload_images/3101171-ee55c839bb75bfa8.gif?imageMogr2/auto-orient/strip" />
<img src="http://upload-images.jianshu.io/upload_images/3101171-a4d6d2405eb9e800.GIF?imageMogr2/auto-orient/strip" />
</div>

在下图中，执行者可以详细的泛化其他执行者:

![image](http://upload-images.jianshu.io/upload_images/3101171-74b6ae51651ceeb9.GIF?imageMogr2/auto-orient/strip)

**用例** - 用例是有意义的单独工作单元。它向系统外部的人或事提供一个易于观察的高层次行为视图。 用例的标注符号是一个椭圆。

![image](http://upload-images.jianshu.io/upload_images/3101171-fb294052d4ee9242.GIF?imageMogr2/auto-orient/strip)

使用用例的符号是带可选择箭头的连接线，箭头显示控制的方向。下图说明执行者 "Customer"使用 "Withdraw"用例。

![image](http://upload-images.jianshu.io/upload_images/3101171-356e9bc9f477494f.GIF?imageMogr2/auto-orient/strip)

用途连接器（uses connector）可以有选择性的在每一个端点有多重性值，如下图，显示客户一次可能只执行一次取款交易。但是银行可以同时执行许多取款交易。

![image](http://upload-images.jianshu.io/upload_images/3101171-01b6a0f9d3b04705.GIF?imageMogr2/auto-orient/strip)

### 用例定义

一个典型的用例包括:

- **名称和描述** - 用例通常用一个动词词组定义，而且有一个简短的文字说明。
- **需求** - 需求定义了一个用例必须提供给终端用户的正式功能性需求。它们符合构造方法建立的功能性规范。一个需求是用例将执行一个动作或提供多个值给系统的约定或承诺。
- **约束** - 一个约束是一个用例运行的条件或限制。它包括：前置条件，后置条件和不变化条件 。前置条件指明了用例在发生之前需要符合的条件。后置条件用来说明在用例执行之后一些条件必须为"真"。不变化条件说明用例整个执行过程中该条件始终为"真"。
- **情形** - 情形是用例的实例在执行过程中，事件发生流程的形式描述。它定义了系统和外部执行者之间的事件指定顺序。通常用文本方式来表示，并对应顺序图中的文字描述。
- **情形图**
- **附加信息**

### 包含用例

用例可能包含其他用例的功能来作为它正常处理的一部分。通常它假设，任何被包含的用例在基本程序运行时每一次都会被调用。下面例子：用例“卡的确认”<Card Identification> 在运行时，被用例“取钱”<Withdraw>当作一个子部分。

![image](http://upload-images.jianshu.io/upload_images/3101171-5b1ea57e9bf7443e.GIF?imageMogr2/auto-orient/strip)

用例可以被一个或多个用例包含。通过提炼通用的行为，将它变成可以多次重复使用的用例。有助于降低功能重复级别。

### 扩展用例

一个用例可以被用来扩展另一个用例的行为，通常使用在特别情况下。例如：假设在修改一个特别类型的客户订单之前，用户必须得到某种更高级别的许可，然后“获得许可”<Get Approval>用例将有选择的扩展常规的“修改订单”<Modify Order>用例。

![image](http://upload-images.jianshu.io/upload_images/3101171-6218dcd5aa5f970e.GIF?imageMogr2/auto-orient/strip)

**扩展点** - 扩展用例的加入点被定义为扩展点。

![image](http://upload-images.jianshu.io/upload_images/3101171-1ac6b427bbf7b768.GIF?imageMogr2/auto-orient/strip)

**系统边界** - 它用来显示用例在系统内部，执行者在系统的外部。

![image](http://upload-images.jianshu.io/upload_images/3101171-8fc64e4963b0b9da.GIF?imageMogr2/auto-orient/strip)

## 2.2. 顺序图

顺序图是交互图的一种形式，它显示对象沿生命线发展，对象之间随时间的交互表示为从源生命线指向目标生命线的消息。顺序图能很好地显示那些对象与其它那些对象通信，什么消息触发了这些通信，顺序图不能很好显示复杂过程的逻辑。

**生命线** - 一条生命线在顺序图中代表一个独立的参与者。表示为包含对象名的矩形，如果它的名字是"self"，则说明该生命线代表控制带顺序图的类元。

![image](http://upload-images.jianshu.io/upload_images/3101171-84d4c28990089835.GIF?imageMogr2/auto-orient/strip)

有时，顺序图会包含一个顶端是执行者的生命线。这情况说明掌握这个顺序图的是用例。健壮图中的边界，控制和实体元素也可以有生命线。

![image](http://upload-images.jianshu.io/upload_images/3101171-2a31055037ddd7f1.GIF?imageMogr2/auto-orient/strip)

**消息** - 消息显示为箭头。消息可以完成传输，也可能丢失和找回，它可以是同步的，也可以是异步的，即可以是调用，也可以是信号。在下图中，第一条消息是同步消息(标为实箭头)完成传输，并隐含一条返回消息。第二条消息是异步消息 (标为实线箭头)，第三条是异步返回消息(标为虚线)。

![image](http://upload-images.jianshu.io/upload_images/3101171-acfc006cb1f08692.GIF?imageMogr2/auto-orient/strip)

**执行发生** - 向下延伸的细条状矩形表示执行事件或控制焦点的激活。在上图中有三个执行事件。第一个是源对象发送两条消息和收到两条回复。第二个是目标对象收到一条同步消息并返回一条回复。第三个是目标对象收到一条异步消息并返回一条回复。

**内部通信** - 内部消息表现为一个操作的递归调用，或一个方法调用属于同一个对象的其他方法。显示为生命线上执行事件的嵌套控制焦点。

![image](http://upload-images.jianshu.io/upload_images/3101171-f041d07a5e21317c.GIF?imageMogr2/auto-orient/strip)

**迷路消息和拾取消息** - 迷路消息是那些发送了却没有到达指定接收者，或者到达的接收者不再当前图中。拾取消息是收到来自那些未知的发送者，或者来自没有显示在当前图的发送者的消息。它们都表明是去往或来自一个终点元素。

![image](http://upload-images.jianshu.io/upload_images/3101171-df9907958b097ca1.GIF?imageMogr2/auto-orient/strip)

**生命线开始与结束** - 生命线可以在顺序图时间刻度范围内创建和销毁，在下面的例子中，生命线被停止符号（叉号）终止。在前面的例子中，生命线顶端的符号（Child）显示在比创建它的对象符号（parent）沿页面要低的位置上。下图显示创建和终止对象。

![image](http://upload-images.jianshu.io/upload_images/3101171-1856a0aff9a4779a.GIF?imageMogr2/auto-orient/strip)

**时间和期限约束** - 消息默认显示为水平线。因为生命线显示为沿屏幕向下的时间通道，所以当给实时系统建模，或是有时间约束的业务过程建模，考虑执行动作所需时间长度是很重要的。因此可以给消息设置一个期限约束，这样的消息显示为下斜线。

![image](http://upload-images.jianshu.io/upload_images/3101171-3b893a4cc39c6e1b.GIF?imageMogr2/auto-orient/strip)

**复合片段** - 如前面所说，顺序图不适合表达复杂的过程逻辑。在一种情况下，有许多机制允许把一定程度的过程逻辑加入到图中，并把它们放到复合片段的标题下。复合片段是一个或多个处理顺序被包含在一个框架中，并在指定名称的环境下执行。片段可以是:

- 选择性片段 (显示 “alt”) 为 if…then…else 结构建模。
- 选项片段 (显示 “opt”) 为 "switch"(开关) 结构建模。
- 中断片段对被处理事件的可选择顺序建模，而不是该图的其他部分。
- 并行片段(显示 “par”) 为并发处理建模。
- 弱顺序片段 (显示 “seq”) 包含了一组消息，这组消息必须在后继片段开始之前被处理。但不会把片段内消息的先后顺序强加到不共享同一条生命线的消息上。
- 严格顺序片段 (显示 “strict”) 包含了一系列需要按照给定顺序处理的消息。
- 非片段 (显示 “neg”) 包含了一系列不可用的消息。
- 关键片段 具有关键部分。
- 忽略片段 声明一个没有意义的消息，如果它出现在当前上下文中。
- 考虑片段与忽略片段相反，不包含在考虑片段内的消息都应该被忽略。
- 断言片段 (显示 “assert”)标明任何没有显示为声明操作数的顺序都是无效的。
- 循环片段 包含一系列被重复的消息。

下图显示的是循环片段：

![image](http://upload-images.jianshu.io/upload_images/3101171-395990e2b2a9227a.GIF?imageMogr2/auto-orient/strip)

这也是一个类似于复合片段的交互发生。 交互发生被其他图参考，显示为左上角带"ref"，将被参考图名显示在方框的中间。

**门** - 门是连接片段内消息和片段外消息的连接点。 在 EA 中，门显示为片段框架上的小正方形。作用为顺序图与页面外的连接器。 用来表示进来的消息源，或者出去消息的终点。下面两个图显示它们在实践中的使用。注意：" top level diagram"中的门用消息箭头指向参考片段，在这里没有必要把它画成方块。

![image](http://upload-images.jianshu.io/upload_images/3101171-76c9d0ed8fb81594.GIF?imageMogr2/auto-orient/strip)

![image](http://upload-images.jianshu.io/upload_images/3101171-cbc88f525e140f73.GIF?imageMogr2/auto-orient/strip)

### 部分分解

一个对象可以引出多条生命线，使得对象内部和对象之间的消息显示在同一图上。

![image](http://upload-images.jianshu.io/upload_images/3101171-81962e0e941980f1.GIF?imageMogr2/auto-orient/strip)

**状态常量/延续** - 状态常量是生命线的约束，运行时始终为"真"。显示为两侧半圆的矩形，如下图：

![image](http://upload-images.jianshu.io/upload_images/3101171-9885bcfde2f2482a.GIF?imageMogr2/auto-orient/strip)

延续虽与状态常量有同样的标注，但是被用于复合片段，并可以延伸跨越多条生命线。
