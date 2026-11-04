# S-100 5.2.1 · 第 13 部分 · 脚本

非官方机器翻译参考稿，尚未逐条人工校订。公式与代码保留原文，解释以英文规范为准。

## 官方 PDF 第 623 页

S-100 - 第13编

脚本

## 官方 PDF 第 624 页

5.2.1版实质性变动摘要

已生效的概要条款

从规范性参考资料中删除了URL链接和整个链接 13-3, 13-7.1

表13-7:经过修改的URI值标记,用于反映字符编码可以反映任何URI格式;添加缺失值文件URI.

```text
13-8.1
```

澄清了 AtproductionControlints 的参数精度指定了小数位数位位数到小数取位数的右后方的位数.

```text
13-8.1.1.1
```

## 官方 PDF 第 625 页

中文目录（可用上方目录直接跳转）

13-1 范围 · 官方 PDF 627
13-2 符合性 · 官方 PDF 627
13-3 规范性引用文件 · 官方 PDF 627
13-4 目的 · 官方 PDF 627
13-5 脚本目录 · 官方 PDF 627
13-5.1 分发 · 官方 PDF 628
13-5.2 具体领域目录功能 · 官方 PDF 629
13-6 数据交换 · 官方 PDF 629
13-6.1 DEF 模式 · 官方 PDF 629
13-6.1.1 特殊人物 · 官方 PDF 629
13-6.1.2 字符串编码 · 官方 PDF 630
13-6.1.3 分析 · 官方 PDF 630
13-6.2 属性路径 · 官方 PDF 631
13-7 宿主环境要求 · 官方 PDF 631
13-7.1 Lua 版本 · 官方 PDF 631
13-7.2 字符编码 · 官方 PDF 632
13-7.3 错误处理 · 官方 PDF 632
13-7.4 阵列参数 · 官方 PDF 632
13-7.5 主办职能 · 官方 PDF 632
13-7.5.1 兼容性 · 官方 PDF 632
13-8 标准脚本函数 · 官方 PDF 632
13-8.1 标准目录功能 · 官方 PDF 633
13-8.1.1 对象创建功能 · 官方 PDF 634
13-8.1.2 类型信息创建功能 · 官方 PDF 641
13-8.1.3 杂项职能 · 官方 PDF 648
13-8.2 标准东道方职能 · 官方 PDF 649
13-8.2.1 数据存取功能 · 官方 PDF 649
13-8.2.2 类型信息访问功能 · 官方 PDF 655
13-8.2.3 空间操作功能 · 官方 PDF 657
13-8.2.4 调试器支持功能 · 官方 PDF 658

## 官方 PDF 第 626 页

本页特意留空

## 官方 PDF 第 627 页

13-1 范围

这一部分定义了将脚本支持包含在以S-100为基础的产品中的标准机制. 脚本提供通过用Lua编程语言编写的脚本文件处理以S-100为基础的数据集.

13-2 符合性

符合这一部分的脚本必须使用Lua编程语言5.1版本来实施.

13-3 规范性引用文件

本文件的应用需要下列参考文件:关于注明日期的参考文件,仅适用所引用的版本;关于未注明日期的文件,适用所参考文件的最新版本(包括修正案)。

5.1 参考手册

ISO 19125-1:2004,地理信息 -- -- 简单要素访问 -- -- 第1部分:共同架构

13-4 目的

提供这一部分是为了允许S-100产品规则的规范表达和处理,可能的使用例子包括:显示规则,产品互操作性规则,探测导航危险的规则,数据验证规则等.

使用脚本可以去除规则表达中的模糊性,确保应用程序的一致性,并且允许通过目录更新修改或扩展规则.

13-5 脚本目录

脚本目录(见图1)是被写作用于一个脚本域的脚本文件的集合.

例如, 显示是一个脚本域。 Lua 显示 目录中包含的规则文件包含一个脚本目录 。

所有脚本目录都保证包含第13-8.1.条所定义的标准目录功能. 脚本分类目录可能额外包含域特定目录功能,标准目录功能简化了脚本域内脚本的创建,整合,测试.

## 官方 PDF 第 628 页

图13-1 - 脚本目录的组成

为了在脚本域内应用规则,脚本目录与主机函数相互作用. 脚本分类目录与站机函数之间的关系如下文图13-2所示. 主机函数可以将脚本编目与主機S-100概念和功能的實作相去开脱.

图13-2 - 脚本目录 / 主机在脚本域内的交互

13-5.1 分发

脚本目录的发售机制在脚本域内被定义. 例如,S-100 第9A部分包含在显示 Catalogue内的脚本编目;通过发售Portaryal Ctalogue完成脚本分目的发出.

## 官方 PDF 第 629 页

脚本目录的每一个实例必须包括所有标准目录功能.

13-5.2 具体领域目录功能

标准脚本功能总是在一个脚本目录中提供. S-100中使用脚本的部分可能会根据支持域特定功能的需要提供额外的脚本函数,在这种情况下,额外的功能被称为"域特定函数".

用于主机/脚本目录交互的域名特定功能(见图2)必须在S-100的相关部分内指定. 脚本分类目录内内部使用域名的特定功能无需在S- 100内指定出.

例如,假设S-100 Part N使用脚本,需要添加脚本函数 X,Y,和Z. 如果函数 X和Y是从主机调用,但函数 Z只从函数 X 和 Y调用出,S- 100 PartN必须指定需要的函数 X 为每个函数提供文档. 由于函数 Z 仅由脚本目录内部使用,所以不需要用文件来记录.

主机和脚本目录之间互动所使用的域名特定功能被指为"域名具体主机函数"或"域相特定目录函数",这取决于由主机还是由脚本分类目录内执行.

13-6 数据交换

从脚本目录中传递给主机的数据,可以使用与数据类型相匹配的Lua CPI API函数检索。对于零、布尔、字符串和数字等简单数据类型,数据检索是微不足道的。对于更复杂的数据类型来说,脚本分类使用本节所描述的数据交换格式(DEF)编码数据。

13-6.1 DEF 模式

数据交换格式(DEF)是一个字符串,其格式如下所描述. 主机解析DEF是简单的,可以使用所有流行编程语言中构建的解析能力来进行. 主機解析 DDEF 通常应该使用字符串分拆操作,如 Java 中的 String.split () , 或者使用简单的扫描解析, 如 C 或 C++ 中的 strtok ()等.

DEF 字符串是用分号(;)相分隔的一个或多个元素的系列。每个元素由一个项目字符串组成,然后是可选的以分号 (:) 和参数列表相接。参数列表是用逗号 (,)相隔的一个或多个参数字符串。

注意字符串参数没有被任何诸如引号等分隔符所包围,然而,字符串指标内的特殊字符会像第13-6.1.2条所描述的那样使用一个活字形((和))来逃避.

13-6.1.1 特殊人物

下表列出DEF使用的特殊字符.

表13-1 - 特殊字符

特殊字符使用

分号 (;) 分离DEF 的单个元素.

Colon (:) 将每个元素分离成项目字符串和参数列表.

逗号 (,) 分隔一个参数列表的单个参数.

Ampersand ( &) Esces / 编码了DEF 中包含的特殊字符.

## 官方 PDF 第 630 页

13-6.1.2 字符串编码

DEF中包含的特殊字符被用下表所列出的字符序列来逃脱/编码.

表13-2 – 字符串编码

特殊字符编码

分号 (;) & s

科隆 (:) & c

逗号(,) m( M)

Ampersand (( )) &a

例如,一个概念性DEF包含四个要素,可用于表示绘图指示:

```text
PenWidth:0.64;PenColor:LANDF,0.75;DrawLine;DrawTextStrings:Hello&m
world!,,Foo&cbar
```

第一元素有一个参数(0.64),第二元素有两个参数(LANDF和0.75),第三元素没有参数,而第四元素有三个参数(Hello,world!,无效或空;和Foo:bar).

13-6.1.3 分析

解析DEF有四个步骤:(1) 获得每个元素,(2) 获得各个元素的项和参数,(3) 将参数分解为单个块,再(4) 解码每个参数。

项目1:P1A;项目2:P2A,P2B;项目3:Hello &m World!

主机应首先在每个分号(;)边界上将DEF分割成单个元素,从而产生以下结果: 1.

表13-3 分析 - 第1步

要点#要点

1 项目1:P1A

2 第2项:P2A、P2B

3 项目3: Hello &m World! 然后,每个元素应该通过分拆分出分号(:)边界来被分出一个项和参数,从而产生:

表13-4 分析-步骤2

要点# 要点项目

1 项目1:P1A 项目1P1A

2 项目2:P2A,P2B 项目2P2A,P2B

3 项目3: Hello &m World! 项目3: Hello &m World! 然后通过将每个逗号(,)边界上的参数分开来逐一取出参数,从而产生:

表13-5 分析-步骤3

要点# 要点项目Parameter 1 Parameter 2... Parameter N

1 项目1:P1A 项目1P1A

2 项目2:P2A,P2B 项目2 P2A P2B

3 项目3: Hello &m世界! 项目3: Hello &m世界!

## 官方 PDF 第 631 页

一旦DEF被分为其组成部分,每个参数都应该通过进行表13.2所列举的替代来被转换为原来的字符串编码:

表13-6 分析-步骤4

要点# 要点项目Parameter 1 Parameter 2... Parameter N

1 项目1:P1A 项目1P1A

2 项目2:P2A,P2B 项目2 P2A P2B

3 第3项:Hello &m World! 第3项:World!

13-6.2 属性路径

脚本目录需要能够确定数据集内包含的每个要素实例上属性的值。要做到这一点,目录会根据需要查询每个属性值的主机。在查询主机时,目录必须确定询问特定要素的属性。 如果一个要素实例只包含简单的属性,那么识别要素实例和属性代码就足以使主机能够唯一地识别所请求的属性.

当属性值包含在一个复杂的属性中时,主机需要更多信息. 例如,考虑以下属性值的查找:

```text
feature.sectorCharacteristic[2].lightSector[1].valueOfNominalRange
```

这里的特性有一个复杂的属性扇形,它是一个阵列. 扇形的第二个条目包含复杂的属性光扇形(Light Spector),它的第一个条目包含简单的属性值OfNominal Range.

在请求值OfNominal Range时,脚本除了给所希望的属性编码外,还必须为主机提供一条通往所希望属性的路径,以便主机能够返回实际值. 需要路径是因为特性实例可能包含多个属性实例,其代码相同,包含在不同的属性路径中——例如:title.simpleAttize, vs. splexAtpiz[n].sipleAdtiziation vs sitle (complexAPt. [n+1]. simplyAtized.

当脚本目录请求主机的属性值时,会使用DEF字符串向主机提供属性路径. 路径的每个部分被编码为包含属性代码和索引的元素. 属性代码包含一个复杂的属性代码; 索引存储复杂属性的数组索引.

在上述例子中,以DEF表示的数值范围路径如下:

```text
sectorCharacteristic:2;lightSector:1
```

DEF将用于从脚本目录中向东道主发出如下呼吁:

```text
HostFeatureGetSimpleAttribute(featureID, sectorCharacteristic:2;lightSector:1,
valueOfNominalRange)
```

13-7 宿主环境要求

本节定义了为支持脚本功能而给主机施加的要求. 例如,一个使用S-100 Part 9A的描述来显示S-101 ENC的程序必须符合本节的要求.

13-7.1 Lua 版本

主机必须提供脚本引擎; Lua 版本 5.1 解释器或虚拟机. 参考执行可以从 lua.org 上获取. 建议将参考执行嵌入主机中。 为了实现最大性能, 主机可以嵌入或执行 LuaJIT 等 Lua编译器。

Lua-Part IV(消费物价指数)的方案拟订中提供了关于嵌入的进一步指导。

## 官方 PDF 第 632 页

13-7.2 字符编码

主机和脚本目录之间交换的所有字符串都必须被UTF-8编码.

13-7.3 错误处理

在从主机调用 Lua 脚本目录函数时, LUA_OK 从 lua_ pall 返回值表示成功。 否则, 将使用标准 Lua错误处理机制。 错误代码会返回主机, 并且堆栈顶部将有一个详细显示错误的字符串 。

13-7.4 阵列参数

脚本目录的几个功能期望数组作为参数被传递。 数组是标准Lua数组,应该使用LuA – Part IV(CAPI)中编程中记录的Luan CPI数组函数创建。

13-7.5 主办职能

主机必须提供第13-8.2条所详述的标准主机功能.

主机还必须提供域特定主机功能,以支持域特定功能. 域特定函数被主机所未使用,不需要提供. S-100 部分提供了域特定的主机功能的文档,描述了域特定职能.

13-7.5.1 兼容性

主机必须保证所提供的函数与所有先前已发布的脚本目录的倒向兼容性,即在执行函数 X时,主机只能调用在X被添加时S-100版本中可用的脚本编目函数.

未能遵守这一要求可能导致主机试图运行更旧的脚本目录时出现不相容.

13-7.5.1.1 脚本目录/主机不兼容

随着S-100新版本的发布,脚本功能可能会被添加. 脚本功能永远不会被从S-100中去除,尽管使用特定功能可能会被贬值.

虽然向后兼容性得到保证,但较新的脚本目录可能会试图调用当前主机不支持的主机函数。这种情况表明一个主机还没有更新最新的主机脚本函数。为了限制这类案例的发生,应该使用尽可能早的脚本功能子集来编写脚本分类目录。

脚本初始化时会显示脚本不兼容( 缺少主机功能) 。 无法兼容性通过从 lua_ pall 返回 LUA_ ERRERR 来表示给主机; 堆栈顶端的错误字符串会详细显示不兼容的原因。 当发生这种情况时, 主机应该恢复到脚本目录的更早版本。 还建议提醒用户检查主机软件的更新情况.

13-8 标准脚本函数

本节描述构成脚本系统的标准脚本功能集。有两组功能:标准目录功能;标准主机功能。脚本目录的实现只在脚本领域存在。

13-8.1条中所述的标准目录功能在每一脚本目录中都有规定,13- 8.2条中所述标准主机功能将由主机程序实施。

## 官方 PDF 第 633 页

下图13-3显示了脚本环境内各类脚本功能的位置.

图13-3 – 脚本功能在脚本环境中的位置

每一个标准脚本函数在下文中按其子密钥描述。该函数的目的以及参数和返回值的描述。为了清晰起见,空格用于表示一个函数没有返回值。

能够接受多个类型函数参数会被指为变体. 如果函数可以返回一个以上类型,则变量也会被使用。 例如,一个函数会接受第一个参数的整数和字符串,并返回一个整数或以第一个参数通过的类型为依归的字符串。 它会具有以下签名:

变位函数( 变相参数1)

函数描述将显示允许变量参数的类型。

许多标准脚本功能接受一个特性ID,信息TypeID或空间ID参数. 主机必须确保这些各种ID参数在主机在脚本会话中所使用的所有产品类型的数据集中,独一识别出一个单一实例. 由于每种ID都是字符串,因此实现这一点的一种方法是预先将相关信息放入ID;例如"S101.01/US003DE01M_0000.F1",以识别被引用的S-101数据集中的第一个功能.

13-8.1 标准目录功能

本节介绍所有脚本目录提供的标准功能集.

所有传递到这些函数的字符串必须被UTF-8编码.

调用这些函数时, 属性值总是使用字符串从主机传递到脚本环境。 这样就可以通过没有Lua等同的值

## 官方 PDF 第 634 页

明确无误。这也允许在转换为 IEEE 浮点类型时,在不丧失精确度的情况下传递小数值。

如果属性值存在但未知,则应使用从 GetUnknownAttizeString () 返回的值。

下表列出由S100_CD_AttizeValueType定义的类型的字符串表示.

表 13-7 – S100_CD_ 属性表盘定义类型字符串表示法

```text
S100_CD_AttributeValueType
Representation
```

布尔 “ 0” 表示假

“1”代表真实

点出 S100_FC_ListedValue:code. 不要使用 S100_FC_ListValue: label

签名整数的字符串表示

实际字符串表示小数。只允许在有分量的情况下拖动零

文本按规定

字符编码必须遵循ISO 8601规定的日期格式

时间字符编码必须遵循ISO 8601规定的时间格式

日期: 时间字符编码必须遵循ISO 8601规定的日期和时间格式

URI 字符编码必须遵循 RFC 3986 指定的任何 URI 格式

URL 字符编码必须遵循 RFC 3986 指定的 URL 格式

URN字符编码必须遵循RFC 2141定义的URN格式.

file URI 字符编码必须遵循 RFC 8089 定义的 file URI 格式

```text
S100_CodeList
As provided
```

```text
S100_TruncatedDate
As provided
```

13-8.1.1 对象创建功能

这些函数可以免除主机构建与脚本目录中使用的复杂类型相适应的Lua表格的负担,它们允许主机创建对象,这些对象将传递到脚本 目录中。创建对象的图案和内容对主机不透明 — 它们只是用于脚本分类目录中。

```text
13-8.1.1.1 AttributeConstraints CreateAttributeConstraints(integer stringLength, string textPattern, string rangeLower, string rangeUpper, string rangeClosure, integer precision)
```

返回值

```text
AttributeConstraints
```

包含属性约束对象的Lua表.

参数

字符串连:整数或零

文本属性类型中可指定的最大字符数。如果该值为零,则长度不受限制。

文本格式:字符串或零

一个正则表达式,定义可指定属性的文本值的结构。如果该值为零,则结构不受限制。

W3C XML 标准 第2部分 附录F(正则表达式) 需要用于定义文本模式.

## 官方 PDF 第 635 页

下行范围:字符串或零

指定属性允许值的下限。如果该值为零,则没有更低的值约束。

范围上:字符串或零

指定属性允许值的上行范围。如果该值为零,则没有上行值约束。

关闭范围:字符串或零

定义下行和上行区域的关闭操作。这是表1-3所定义的已列出的数值之一。如果指定了下行或上行两个数值,则必须指定。

精确度:整数或零

如果指定,则表示一个实数的精度,作为小数点右侧的位数.

备注

从主机中调用来创建属性限制,供脚本目录使用.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.1.2 SpatialAssociation CreateSpatialAssociation(string spatialType, string spatialID, string orientation, variant scaleMinimum, variant scaleMaximum)
```

返回值 :

```text
SpatialAssociation
```

包含空间相通物体的Lua表.

参数:

```text
spatialType: string
```

空间类型,其中之一为:"点","多点","环","复合环",或"指相".

```text
spatialID: string
```

被主机用来独占地识别空间.

方向: 字符串

空间方向 向后或向后方向

最小值:整数或零

空间或零的最小显示尺度。

平方厘米:整数或零

空间或零的最大显示尺度。

备注:

从主机中调出,创建了空间协会,供脚本目录使用.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.1.3 Point CreatePoint(string x, string y, variant z)
```

返回值 :

点

含有点对象的 Lua 表格 。

## 官方 PDF 第 636 页

参数:

x: 字符串

X坐标指向点.

Y: 字符串

Y 坐标对点。

Z: 字符串或零

Z坐标表示点。对于2D点,该值必须为零。

备注:

x、y和z 使用第13-8.1条所描述的实际字符串表示法表示。

从主机中调用,创建出一个点空间对象,供脚本目录使用.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

13-8.1.1.4 多点创建多点(点)

返回值 :

```text
MultiPoint
```

一个包含多点对象的Lua表.

参数:

点: 点 []

Lua 数组积分。 主机通过调用 CreatPoint 创建每个积分 。

备注:

从主机中调用,创建多点空间对象,供脚本目录使用.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.1.5 CurveSegment CreateCurveSegment(Point[] controlPoints, string interpolation)
```

返回值 :

```text
CurveSegment
```

含有曲线分块对象的 Lua 表格 。

参数:

```text
controlPoints: Point[]
```

用于定义曲线段控制点的点组。主机通过调用 CreatPoint 创建每个控制点。

内插: 字符串

连接控制点时使用的插值。 S100_CurvepotolationL: name。

备注:

从主机调用创建曲线段空间对象.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

13-8.1.1.6 曲线创建曲线(空间协会起步点、空间协会端点、曲线区段)

返回值 :

曲线

## 官方 PDF 第 637 页

含有曲线对象的Lua表。

参数:

```text
startPoint: SpatialAssociation
```

曲线的起点。 主机通过呼叫 CreateSpatial Association 创建 。

```text
endpoint: SpatialAssociation
```

曲线的终点。 主机通过呼叫 CreateSpatial Association 创建 。

```text
segments: CurveSegment[]
```

包含曲线的曲线段数组。每个数组项都通过调用 CreatCurveSegment 创建 。

备注

从主机中调用以创建曲线空间对象.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

13-8.1.1.7 综合调查创建综合调查(空间协会)[ []曲线协会]

返回值 :

```text
CompositeCurve
```

含有复合曲线对象的Lua表。

参数:

```text
curveAssociations: SpatialAssociation[]
```

组合定义复合曲线元素的空间关联。 主机通过调用 CreatSpatial Association 创建每个空间关联 。

备注:

从主机中调出创建了复合曲线空间对象.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

13-8.1.1.8 表面创造面(空间协会外接线,变体内接线)

返回值 :

表面

含有表面物体的Lua表.

参数:

```text
exteriorRing: SpatialAssociation
```

定义地表外环的环的空间关联。 主机通过呼叫 CreateSpatial Association 创建 。

内饰:空间协会[]或无

定义表层中的“ 空洞 ” 。 主机通过呼叫 CreatSpatial Association 来创建每个内环。 如果没有空洞, 此参数为零 。

备注:

从主机中调用来创建地表空间物体.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

## 官方 PDF 第 638 页

13-8.1.1.9 ArcByCenterPoint Create ArcByCenterpoint(空间协会中心点,正半径,正起步角,正角相位)

返回值 :

```text
ArcByCenterPoint
```

含有 ArcByCenterPoint 对象的 Lua 表格。

参数:

```text
centerPoint: SpatialAssociation
```

定义弧心点的点的空间关联。主机通过调用 CreatSpatial Association 创建 。

半径: 真实

定义与中心之间的大地测量距离。

```text
startAngle: real
```

弧以度为起始轴承,范围以[0.0,360.0]为限.

```text
angularDistance: real
```

弧以度为角相距,范围限于[-360.0,360.0]. 正数表示顺时针方向.

备注:

从主机调用创建 ArcByCenterPoint 空间对象。弧从启动安格尔参数给出的轴向开始,到轴向结束,通过将角向分解参数的值加到起始角度来计算。弧的方向由角向相距的标志给出。 轴承与正北方相对,但以正北方为中心(正北方为未定义或含糊不清的地方)的弧以正中线为参考方向。

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

13-8.1.1.10 CircleByCenterPoint 创建 CircleByCenterpoint(空间协会中心点,真实半径,真实起步的Angle,真实角分相)

返回值 :

```text
CircleByCenterPoint
```

含有 CircleByCenterPoint 对象的 Lua 表格。

参数:

```text
centerPoint: SpatialAssociation
```

定义圆心点的点的空间关联。 主机通过呼叫 CreatSpatial Association 创建 。

半径: 真实

定义与中心之间的大地测量距离。

```text
startAngle: real
```

可选。 弧以度为起点, 范围限制为 [0.0, 360. 0]。 默认为零 。

```text
angularDistance: real
```

可选的。 圆圈以度为单位的角相距, 必须是 -360.0( 逆时针) 或 360.0( 顺时针) 。 正数表示顺时针方向。 默认为 360( 顺时针 )。

备注:

从主机调用创建 CircleByCenterPoint 对象 。

## 官方 PDF 第 639 页

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.1.11 SplineCurve CreateSplineCurve(Point[] controlPoints, string interpolation, integer degree, Knot[] knots, KnotType knotSpec, boolean isRational)
```

返回值 :

```text
SplineCurve
```

含有分线曲线的 Lua 表格 。

参数:

```text
controlPoints: Point[]
```

组合用于定义曲线段控制点的点。主机通过调用 CreatPoint 创建每个控制点。控制点的数量必须是三个或更多 。

插值:字符串

连接控制点时使用的插值。 S100_ Curvepotation: name。

度:整数

用于定义插值的多名分级.

结:克诺 []

结的组合。每个结定义了用于定义分线基础函数的示意图参数空间中的参数。每个节是通过呼叫 CreatKnot 创建的。

```text
knotSpec: KnotType
```

定义 spline 时的结分布类型。 由 S100_ GM_ KnotType 定义 。

```text
isRational: boolean
```

表示该示意图是否使用理性函数来定义曲线。

备注:

从主机中调用以创建一个相向曲线空间对象.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.1.12 PolynomialSpline CreatePolynomialSpline(Point[] controlPoints, string interpolation, integer degree, Knot[] knots, KnotType knotSpec, Vector[] derivativeAtStart, Vector[] derivativeAtEnd, integer numDerivativeInterior)
```

返回值 :

```text
PolynomialSpline
```

含有多名分型的Lua表。

参数:

```text
controlPoints: Point[]
```

组合用于定义曲线段控制点的点。主机通过调用 CreatPoint 创建每个控制点。控制点的数量必须是三个或更多 。

插值:字符串

连接控制点时使用的插值。 S100_ Curvepotation: name。

度:整数

用于定义插值的多名分级.

## 官方 PDF 第 640 页

结:克诺 []

结的组合。每个结定义了用于定义分线基础函数的示意图参数空间中的参数。每个节是通过呼叫 CreatKnot 创建的。

```text
knotSpec: KnotType
```

定义 spline 时的结分布类型。 由 S100_ GM_ KnotType 定义 。

```text
derivativeAtStart: Vector[]
```

用于定义在线条起点此曲线中插入的初始导出值的矢量矩阵。可以定义到地平度的-2个向量。每个向量都通过调用 CreatVector 创建。

```text
derivativeAtEnd: Vector[]
```

用于定义在线程终点此曲线中插入的最终衍生物所使用的数值的矢量矩阵。可以定义到地平度的-2个向量。每个向量是通过呼叫CreativeVector来创建的。

```text
numDerivativeInterior: KnotType
```

内结所需要连续衍生出的数量.

备注:

从主机中调用创建多名分形空间对象.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.1.13 Knot CreateKnot(string value[, integer multiplicity])
```

返回值 :

键

包含有结项的Lua表.

参数:

值: 字符串

结之相值.

复数:整数

结的多,如果省略,多是一.

备注:

值用第13-8.1条中所述的实际字符串表示表示。

从主机调用创建结对象 。

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.1.14 Vector CreateVector(Point origin, string[] offset, integer dimension, string coordinateSystem)
```

返回值 :

键

包含有结项的Lua表.

参数:

来源: 点

矢量为正切的几何参考surface上点的位置.

## 官方 PDF 第 641 页

相冲:字符串 []

本地坐标差的正切矢量。 相抵值是每个坐标轴上的矢量的大小 。

维数:整数

由来之分.

```text
coordinateSystem: string
```

发源地的坐标系统(如EPSG:4326).

备注:

抵消值用第13至8.1条所述的实际字符串表示。

从主机调用创建向量对象 。

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

13-8.1.2 类型信息创建功能

这些函数可以免除主机构建与脚本目录中使用的复杂类型相对应的Lua表格的负担。它们允许主机创建调用脚本 目录时使用的对象。创建对象的策略和内容对主机不透明 — 它们只是用于脚本分类目录中。

复杂类型对应S-100 Part 5 - Feature Catalogue中描述的类别. 本节所描述的每一种类型信息创建函数都指定了相应的S- 100 Part 第5 FetatureCatalocata类型.

FC_定义参考及其所依赖的种类的创建功能,包括CI_Citation类,被故意省略. FC-定义参考没有识别出使用例,CI-Cition的实现将比目前定义的本节全部分更为复杂.

```text
13-8.1.2.1 Item CreateItem(string code, string name, string definition, string remarks, string[] alias)
```

返回值 :

项目

包含一个对应 S100_FC_项目的项目的 Lua 表格。

参数:

代码:字符串

在要素目录中唯一识别被命名类型的代码 。

名称:字符串

所取品名.

定义:字符串

以自然语言对被命名类型的定义.

备注: 字符串

可选,关于该项目的进一步解释。

别名: 字符串[]

本项目等同名称.

备注:

从主机调用创建项目 。

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

## 官方 PDF 第 642 页

```text
13-8.1.2.2 NamedType CreateNamedType(Item item, boolean abstract, AttributeBinding[] attributeBindings)
```

返回值 :

```text
NamedType
```

含有一个与 S100_FC_NamedType 相对应的命名类型的 Lua 表格。

参数:

项目:项目

调用 Create 项目创建项目的实例( ) 。

抽象:布尔

说明在地理数据集中是否可以存在这种命名类型的实例。摘要类型不能被即时化,而只能作为其他(非抽象)类型的基础类别。

```text
attributeBindings: AttributeBinding[]
```

描述此命名类型特性的零或更多属性绑定的数组。

备注:

从主机中调用以创建命名类型 。

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

13-8.1.2.3 对象Type创建对象Type(取名:Type,信息Binding[]信息Bindings)

返回值 :

```text
ObjectType
```

含有一个对象类型的Lua表格,对应的天体类型为S100_FC_ObjectType.

参数:

```text
namedType: NamedType
```

通过调用 CreateNamedType () 创建的命名类型实例 。

```text
informationBindings: InformationBinding[]
```

与信息类型可被通过信息协会与该对象类型相联的零或更紧密地绑定的数组.

备注:

从主机调用以创建对象类型 。

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.2.4 InformationType CreateInformationType(ObjectType objectType, string superType, string[] subType)
```

返回值 :

```text
InformationType
```

一个Lua表格,包含一个对应于S100_FC_InformationType的信息类型.

参数:

```text
objectType: ObjectType
```

通过调用 CreateObjectType () 创建的命名类型实例 。

## 官方 PDF 第 643 页

```text
superType: string
```

可选的。请注明该类型来源的信息类型的代码。

子类型: 字符串 []

从该类型中衍生出来的零或多条信息类型代码阵列。

备注:

从主机中调用创建信息类型.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.2.5 FeatureType CreateFeatureType(ObjectType objectType, string featureUseType, string[] permittedPrimitives, FeatureBinding[] featureBindings, string superType, string[] subType)
```

返回值 :

```text
FeatureType
```

含有对应 S100_FC_FeatureType 的特性类型的 Lua 表格.

参数:

```text
objectType: ObjectType
```

通过调用 CreateObjectType () 创建的命名类型实例 。

```text
featureUseType: string
```

```text
A S100_CD_FeatureUseType:Name.
```

```text
permittedPrimitives: string[]
```

为特性类型指定零或更多允许的空间原始类型的阵列。 每个条目都是 S100_FC_Spatrial Primmitive Type :Name

```text
featureBindings: FeatureBinding[]
```

与要素类型可以通过要素关联方式与该要素类型相联的要素类型相联的零或更多绑定的数组.

```text
superType: string
```

可选。 指定该类型所衍生的特性类型的代码。 子类型将继承其超级类型的所有属性: 名称、 定义和代码通常会被子类型所覆盖, 尽管子类型可能添加新的属性 。

```text
subType: string[]
```

由该类型衍生出来的零或多功能类型代码阵列。

备注:

从主机中调用以创建要素类型 。

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.2.6 InformationAssociation CreateInformationAssociation(NamedType namedType, Role[] roles, string superType, string[] subType)
```

返回值 :

```text
InformationAssociation
```

包含一个对应 S100_FC_Information Association 的信息协会的Lua表.

参数:

```text
namedType: NamedType
```

## 官方 PDF 第 644 页

通过调用 CreateNamedType () 创建的命名类型实例 。

角色: 角色[]

由协会的0到2个角色组成的阵列.

```text
superType: string
```

可选性. 说明据以建立该社团的信息协会的代码。

```text
subType: string[]
```

由此关联衍生出来的零或多条信息关联代码。

备注:

由主办方召来创建信息协会.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.2.7 FeatureAssociation CreateFeatureAssociation(NamedType namedType, Role[] roles, string superType, string[] subType)
```

返回值 :

```text
FeatureAssociation
```

包含一个与 S100_FC_Feature 协会相对应的要素关联的 Lua 表.

参数:

```text
namedType: NamedType
```

通过调用 CreateNamedType () 创建的命名类型实例 。

角色: 角色[]

由协会的0到2个角色组成的阵列.

```text
superType: string
```

可选性。请注明该协会的起源地要素协会的代码。

```text
subType: string[]
```

从此关联中衍生出一系列零或更多特性关联代码 。

备注:

从主办方召来创建特写协会.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

13-8.1.2.8 角色创建(项目)

返回值 :

角色

一个Lua表格,包含一个对应S100_FC_Role的角色.

参数:

项目:项目

调用 Create 项目创建项目的实例( ) 。

备注:

从主持人处召来,以创造出一角色.

## 官方 PDF 第 645 页

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.2.9 SimpleAttribute CreateSimpleAttribute(Item item, string valueType, string uom, string quantitySpecification, AttributeConstraints attributeContraints, ListedValue[] listedValues)
```

返回值 :

```text
SimpleAttribute
```

一个Lua表,包含一个与S100_FC_SimpleAttize相对应的简单属性.

参数:

项:字符串

调用 Create 项目创建项目的实例( ) 。

```text
valueType: string
```

此特性属性的值类型。 A S100_ CD_ 属性ValueType: Name

uom: 字符串

可选。 此特性属性的值所使用的计量单位。 AS100_ UnitOfMeasure: Name

```text
quantitySpecification: string
```

可选的,数量规格。 S100_CD%%=数量规格: Name

```text
attributeContraints: AttributeConstraints
```

可选。 可能适用于属性的限制 。 通过调用 CreateAttificial Controlints () 创建的 。

```text
listedValues: ListedValue[]
```

列出属性域的零或以上列表值的矩阵。每个列表值都是通过调用 CreatListedValue () 创建的。只有当值Type是 Enumeration 或 S100_Codelist(带有可打开的引用的代码列表Typi)时才适用。

备注:

从主机调用创建简单的属性类型信息对象.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

13-8.1.2.10 复杂属性创建复合属性(项目项目,属性编码[]子属性编码)

返回值 :

```text
ComplexAttribute
```

一个Lua表,包含一个与S100_FC_Complex属性相对应的复杂属性.

参数:

项目:项目

调用 Create 项目创建项目的实例( ) 。

```text
subAttributeBindings: AttributeBinding[]
```

包含一个或多个属性对子属性绑定的数组.

备注:

从主机中调用以创建一个复杂的属性类型信息对象.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

## 官方 PDF 第 646 页

```text
13-8.1.2.11 ListedValue CreateListedValue(string label, string definition, integer code, string remarks, string[] aliases)
```

返回值 :

```text
ListedValue
```

包含一个与S100_FC_ListedValue相对应的上市值的Lua表.

参数:

标签:字符串

描述性标签,可以单独识别要素属性的一个值.

定义:字符串

以自然语言对上列价值的定义。

代码:整数

数字代码,用于对相应的要素属性进行唯一识别。正整数。

备注: 字符串

可选,对所列数值作进一步解释.

别名: 字符串 []

可选。 列出的数值为零或更多等同名称的矩阵 。

备注:

从主机调用创建一个列出的值类型信息对象 。

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.2.12 AttributeBinding CreateAttributeBinding(string attributeCode, integer lowerMultiplicity, integer upperMultiplicity, boolean sequential, integer[] permittedValues)
```

返回值 :

```text
AttributeBinding
```

含有一个对应于S100_FC_AttitionBinding的属性的Lua表.

参数:

```text
attributeCode: string
```

绑定在项目或复杂属性上的复杂或简单属性的代码.

```text
lowerMultiplicity: integer
```

此属性所需的最小出错数。 对于可选属性, 这是零 。

```text
upperMultiplicity: integer
```

此属性允许发生的最大次数 。 对于无限允许的属性, 这是零 。

相继:布尔

描述属性的顺序是否有意义。仅适用于可能不止一次发生的属性。

```text
permittedValues: integer[]
```

属性的零或更多允许值的矩阵。每个条目都是 S100_FC_ListedValue:code。仅适用于数据类型计数的属性。

## 官方 PDF 第 647 页

备注:

从主机调用创建属性绑定对象.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.2.13 InformationBinding CreateInformationBinding(string[] informationTypeCode, integer lowerMultiplicity, integer upperMultiplicity, string roleType, string role, string association)
```

返回值 :

```text
InformationBinding
```

一个Lua表格,包含一个与S100_FC_InformationBinding对应的信息绑定.

参数:

```text
informationTypeCode: string[]
```

一个包含一个或多个 S100_FC_InformationType 的数组:代码,表示目标信息类型.

```text
lowerMultiplicity: integer
```

此属性所需的最小出错数。 对于可选属性, 这是零 。

```text
upperMultiplicity: integer
```

此属性允许发生的最大次数 。 对于无限允许的属性, 这是零 。

```text
roleType: string
```

关联的结束性质。 AS100_FC_ RoleType: Name

角色:字符串

可选的,用于约束的角色的代码,必须是用于约束的协会的一部分,并定义了协会的终结.

关联:字符串

用于约束的信息协会的代码;同时也定义了角色.

备注:

从主机调用创建信息绑定对象.

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

```text
13-8.1.2.14 FeatureBinding CreateFeatureBinding(string[] featureTypeCode, integer lowerMultiplicity, integer upperMultiplicity, string roleType, string role, string association)
```

返回值 :

```text
FeatureBinding
```

一个Lua表格,包含一个对应于S100_FC_FeatureBinding的特性.

参数:

```text
featureTypeCode: string[]
```

包含一个或多个 S100_FC_FeatureType 的数组: 表示目标要素类型的代码 。

```text
lowerMultiplicity: integer
```

此属性所需的最小出错数。 对于可选属性, 这是零 。

## 官方 PDF 第 648 页

```text
upperMultiplicity: integer
```

此属性允许发生的最大次数 。 对于无限允许的属性, 这是零 。

```text
roleType: string
```

关联的结束性质。 AS100_FC_ RoleType: Name

角色:字符串

用于约束的角色的代码,必须是用于约束的关联的一部分,并定义了关联的结束.

关联:字符串

用于装订的要素协会代码.

备注:

从主机调用创建特性绑定对象 。

无意使主机操纵返回对象;该对象打算从主机传回脚本目录.

13-8.1.3 杂项职能

以下页所描述的功能不属于前述功能之一.

```text
13-8.1.3.1 string GetUnknownAttributeString()
```

返回值 :

字符串

一个字符串,代表一个存在但未知的属性值。

备注:

旨在允许将未知字符串值与空字符串值区分开来。此函数返回一个常数。

```text
13-8.1.3.2 string EncodeDEFString(string input)
```

返回值 :

字符串

第13-6.1.2条所述输入编码。

参数

输入:字符串

未编码的字符串 。

备注:

编码第13-6.1.2节所描述的输入字符串.

```text
13-8.1.3.3 string DecodeDEFString(string encodedString)
```

返回值 :

字符串

已解码的版本被解码为String.

参数

```text
encodedString: string
```

被编码的字符串 。

## 官方 PDF 第 649 页

备注:

解码一个先前被编码为第13-6.1.2节所描述的输入字符串.

```text
13-8.1.3.4 void TypeSystemChecks(boolean enabled)
```

返回值 :

无

参数

启用:布尔

启用或禁用类型检查 。

备注:

指定每个参数的数据类型, 在每个函数调用时都要进行校验。 默认情况下已禁用。 在目录开发过程中, 可以启用类型系统检查作为调试帮助 。

13-8.2 标准东道方职能

主机必须提供一套"召回"功能,为脚本环境提供: 访问主机实现S-100通用要素模型; 访问该模型所定义的任何实体的类型信息; 获取空间操作,可用于对模型所界定空间元素进行关系测试和操作. 主机可能可选择提供用于与调试器交互的回调函数.

将这些任务卸入主机,而不是提供在主机和脚本之间传递的僵硬数据结构,使得主机能够使用主机最优的通用特质模型的表示方式与脚本交互. 主机将其内部数据模型翻译为特定的输入子方案在使用脚本时是不必要的.

任何标准主机功能都可以在执行一个脚本的过程中从脚本目录中调用.

13-8.2.1 数据存取功能

主机必须执行以下页面所描述的功能,以便脚本环境访问主机从数据集中装入的数据。这些功能为脚本环境中提供了访问特性、空间、属性值和信息关联的通道。

```text
13-8.2.1.1 string[] HostGetFeatureIDs()
```

返回值 :

字符串 []

包含数据集中所有特性ID的Lua阵列.

备注:

指示主机返回所有与当前脚本目录操作相关的特性 ID。 这通常是S100_Dataset或S100_DataCoverage中的所有特性 。

如第13至8条所讨论,主机负责确保每个特性ID在目前脚本会话中在所有产品类型和数据集中单独识别出一个特性实例.

```text
13-8.2.1.2 string HostFeatureGetCode(string featureID)
```

返回值 :

字符串

由"要素目录"为要素实例的要素类型定义的代码.

参数:

```text
featureID: string
```

## 官方 PDF 第 650 页

被主机用来独占要素识别实例 。

备注:

指示主机返回特性ID所识别的特性实例的特性类型代码.

```text
13-8.2.1.3 string[] HostGetInformationTypeIDs()
```

返回值 :

字符串 []

包含数据集中所有信息类型ID的Lua阵列.

备注:

允许脚本查询主机,以查询某一数据集中包含的信息类型列表。

指示主机返回包含给定数据集中所有信息ID的数组.

```text
13-8.2.1.4 string HostInformationTypeGetCode(string informationTypeID)
```

返回值 :

字符串

由"要素目录"为信息类型实例的信息类型定义的代码.

参数:

```text
informationTypeID: string
```

被主机用于唯一识别信息类型实例 。

备注:

指示主机返回信息类型实例的信息类型代码,信息类型实例由信息类型ID识别.

```text
13-8.2.1.5 string[] HostFeatureGetSimpleAttribute(string featureID, path path, string attributeCode)
```

返回值 :

字符串 []

每一个属性值的文字表示,如第13-8.1.条所描述的,即使属性有一个单一的值,仍返回一个数组.

参数:

```text
featureID: string
```

被主机用来独占要素识别实例 。

路径:路径

第13-6.2条描述的属性路径

```text
attributeCode: string
```

要素目录中为要素ID所识别的要素类型定义的属性代码之一.

备注:

指示主机在特性ID所识别的要素实例的路径路径上对属性属性进行简单的属性查询。如果请求的属性不出现,则返回空数组。

## 官方 PDF 第 651 页

```text
13-8.2.1.6 integer HostFeatureGetComplexAttributeCount(string featureID, path path, string attributeCode)
```

返回值 :

整数

特性实例路径中存在的匹配复杂属性的数量 。

参数:

```text
featureID: string
```

被主机用来独占要素识别实例 。

路径:路径

第13-6.2条所描述的属性路径.

```text
attributeCode: string
```

要素目录中为要素ID所识别的要素类型定义的属性代码之一.

备注:

指示主机返回给定特性实例的给定属性路径匹配属性代码的属性数。给定路径对特性实例总是有效的。返回的整数可以是零。

```text
13-8.2.1.7 SpatialAssociation[] HostFeatureGetSpatialAssociations(string featureID)
```

返回值 :

```text
SpatialAssociation[]
```

包含所有空间关联的Lua阵列,用于以特性ID为代表的要素实例。

参数:

```text
featureID: string
```

被主机用来独占要素识别实例 。

备注:

指示主机返回包含给定要素的空间关联的数组。 对于每个空间关联,主机会调用标准目录函数 CreatSpatial Association 来创建空间关联对象 。

如果特性没有空间关联,主机应该返回一个空阵列.

```text
13-8.2.1.8 string[] HostFeatureGetAssociatedFeatureIDs(string featureID, string associationCode, variant roleCode)
```

返回值 :

字符串 []

包含相关特性ID的Lua阵列.

参数:

```text
featureID: string
```

被主机用来独占要素识别实例 。

```text
associationCode: string
```

要素目录所定义的被请求关联的代码.

## 官方 PDF 第 652 页

角色代码:字符串或零

要素目录定义的所请求角色代码。 如果关联代码本身足以指定关联, 或者需要关联代码定义的所有角色, 则代码为零 。

备注:

当调用时, 主机返回一个包含与给定的特性实例相匹配的特性ID的阵列。 如果找不到匹配, 主机返回一个空阵列 。

角色代码可以是零,在这种情况下,只应该使用协会代码进行查询.

```text
13-8.2.1.9 string[] HostFeatureGetAssociatedInformationIDs(string featureID, string associationCode, variant roleCode)
```

返回值 :

字符串 []

包含相關相關資訊ID的 Lua 陣列.

参数:

```text
featureID: string
```

被主机用来独占要素识别实例 。

```text
associationCode: string
```

要素目录所定义的被请求关联的代码.

角色代码:字符串或零

要素目录定义的所请求角色代码。 如果关联代码本身足以指定关联, 或者需要关联代码定义的所有角色, 则代码为零 。

备注:

当调用时, 主机返回一个包含与给定的特性实例相匹配的信息ID的阵列。 如果找不到匹配, 主机返回一个空阵列 。

角色代码可能为零,在这种情况下,只使用协会代码进行取景.

```text
13-8.2.1.10 string[] HostInformationGetAssociatedInformationIDs(string informationID, string associationCode, variant roleCode)
```

返回值 :

字符串 []

包含相關相關資訊ID的 Lua 陣列.

参数:

```text
informationID: string
```

被主机用来独占地识别信息实例.

```text
associationCode: string
```

要素目录所定义的被请求关联的代码.

角色代码:字符串或零

要素目录定义的所请求角色代码。 如果关联代码本身足以指定关联, 或者需要关联代码定义的所有角色, 则代码为零 。

## 官方 PDF 第 653 页

备注:

当调用时, 主机返回一个包含与给定信息实例相匹配的信息ID的阵列。 如果找不到匹配, 主機会返回一个空阵列 。

角色代码可能为零,在这种情况下,只使用协会代码进行取景.

```text
13-8.2.1.11 string[] HostGetSpatialIDs()
```

返回值 :

字符串 []

包含数据集中所有空间ID的Lua阵列.

备注:

指示主机返回所有与当前脚本目录操作相关的空间ID。 这通常是S100_Dataset或S100_DataCoverage中的所有空间对象 。

如第13至8条所讨论,主机负责确保每个空间ID在目前脚本会话中使用的所有产品类型和数据集中,都独一地识别出一个空间实例。

```text
13-8.2.1.12 Spatial HostGetSpatial(string spatialID)
```

返回值 :

空间

通过注释所列出的标准目录函数创建的空间物体.

参数:

```text
spatialID: string
```

被主机用来独占地识别空间.

备注:

查询主机的给定空间 。

主机返回由第13-8.1.1条所定义的标准目录函数之一所创建的空间对象.

```text
13-8.2.1.13 variant HostSpatialGetAssociatedInformationIDs(string spatialID, string associationCode, variant roleCode)
```

返回值 :

无

信息关联对于这个空间无效.

字符串 []

包含相關相關資訊ID的 Lua 陣列.

参数:

```text
spatialID: string
```

被主机用来独占地识别空间.

```text
associationCode: string
```

要素目录所定义的所请求的关联的代码.

角色代码:字符串或零

要素目录所定义的所请求角色的代码。 如果关联代码本身足以指定该关联, 或者需要关联代码定义的所有角色, 可为零 。

## 官方 PDF 第 654 页

备注:

当调用时, 主机返回包含给定空间实例信息ID的阵列, 匹配关联Code和角色Code。 如果根据要素目录信息关联对该特性无效, 主機返回为零。 如果没有找到匹配, 主站返回为空阵列 。

角色代码可能为零,在这种情况下,只使用协会代码进行取景.

```text
13-8.2.1.14 string[] HostSpatialGetAssociatedFeatureIDs(string spatialID)
```

返回值 :

字符串 []

包含空间ID识别空间所需相关要素标识的Lua阵列.

无

空间ID识别的空间不存在任何要素相通.

参数:

```text
spatialID: string
```

被主机用来独占地识别空间.

备注:

当调用时, 主机返回一系列所有引用给定空间的要素实例。 要素实例被视为直接通过该要素上的空间关联与空间相关, 或间接地在被复合曲线或地表环所引用的曲线中相关联 。

```text
13-8.2.1.15 string[] HostInformationTypeGetSimpleAttribute(string informationTypeID, path path, string attributeCode)
```

返回值 :

字符串[]或零

13-8. 1. 句所描述的每个属性值的文字表示值,即使属性有单一值,仍返回数组。如果请求的属性不存在,则主机应返回零。

参数:

```text
informationTypeID: string
```

被主机用来独占地识别信息实例.

路径:路径

第13-6.2条所定义的属性路径.

```text
attributeCode: string
```

由feature Catalogue定义的属性代码之一,用于信息TypeID所识别的信息类型.

备注:

指示主机在信息TypeID识别的信息实例的指定路径上对属性属性进行简单的属性查询。如果请求的属性不在场,则返回 Nil 。

```text
13-8.2.1.16 integer HostInformationTypeGetComplexAttributeCount(string informationTypeID, path path, string attributeCode)
```

返回值 :

整数

信息实例路径中存在的匹配复杂属性的数量 。

## 官方 PDF 第 655 页

参数:

```text
informationTypeID: string
```

被主机用来独占地识别信息实例.

路径:路径

第13-6.2条所描述的属性路径.

```text
attributeCode: string
```

由feature Catalogue定义的属性代码之一,用于信息TypeID所识别的信息类型.

备注:

指示主机返回给定信息实例的给定属性路径上匹配属性代码的属性数。给定路径对信息实例总是有效的。返回的整数可以是零。

13-8.2.2 类型信息访问功能

这些函数允许脚本环境从任何数据集查询任何实体的类型信息。主机提供的类型信息必须匹配相关要素目录中的信息。

```text
13-8.2.2.1 string[] HostGetFeatureTypeCodes()
```

返回值 :

字符串 []

包含要素目录所定义的所有要素类型代码的阵列.

备注:

```text
13-8.2.2.2 string[] HostGetInformationTypeCodes()
```

返回值 :

字符串 []

包含要素目录所定义的所有信息类型代码的阵列。

备注:

```text
13-8.2.2.3 string[] HostGetSimpleAttributeTypeCodes()
```

返回值 :

字符串 []

包含要素目录所定义的所有简单属性类型代码的阵列.

备注:

```text
13-8.2.2.4 string[] HostGetComplexAttributeTypeCodes()
```

返回值 :

字符串 []

包含要素目录所定义的所有复杂属性类型代码的阵列.

备注:

```text
13-8.2.2.5 string[] HostGetRoleTypeCodes()
```

返回值 :

字符串 []

包含要素目录所定义的所有角色类型代码的阵列.

备注:

## 官方 PDF 第 656 页

```text
13-8.2.2.6 string[] HostGetInformationAssociationTypeCodes()
```

返回值 :

字符串 []

包含要素目录所定义的所有信息关联类型代码的阵列 。

备注:

```text
13-8.2.2.7 string[] HostGetFeatureAssociationTypeCodes()
```

返回值 :

字符串 []

包含要素目录所定义的所有特性关联类型代码的矩阵 。

备注:

```text
13-8.2.2.8 FeatureType HostGetFeatureTypeInfo(string featureCode)
```

返回值 :

```text
FeatureType
```

由 CreateFeatureType () 函数创建的 Lua 数据结构 。

参数:

```text
featureCode: string
```

与"要素目录"中的条目相匹配的要素代码.

备注:

```text
13-8.2.2.9 InformationType HostGetInformationTypeInfo(string informationCode)
```

返回值 :

```text
InformationType
```

CreateInformationType () 函数创建的 Lua 数据结构 。

参数:

```text
informationCode: string
```

与"要素目录"条目相匹配的信息代码.

备注:

```text
13-8.2.2.10 SimpleAttribute HostGetSimpleAttributeTypeInfo(string attributeCode)
```

返回值 :

```text
SimpleAttribute
```

CreateSimpleAttize () 函数创建的 Lua 数据结构 。

参数:

```text
attributeCode: string
```

简单属性代码匹配要素目录中的条目.

备注:

```text
13-8.2.2.11 ComplexAttribute HostGetComplexAttributeTypeInfo(string attributeCode)
```

返回值 :

```text
ComplexAttribute
```

CreatComplexAttize () 函数创建的 Lua 数据结构 。

## 官方 PDF 第 657 页

参数:

```text
attributeCode: string
```

复杂属性代码与"要素目录"中的条目相匹配.

备注:

```text
13-8.2.2.12 Role HostGetRoleTypeInfo(string roleCode)
```

返回值 :

角色

CreatRole 函数创建的 Lua 数据结构

参数:

```text
roleCode: string
```

角色代码匹配要素目录中的条目.

备注:

```text
13-8.2.2.13 InformationAssociation HostGetInformationAssociationTypeInfo(string informationAssociationCode)
```

返回值 :

```text
InformationAssociation
```

Create Information Association 函数创建的 Lua 数据结构

参数:

```text
informationAssociationCode: string
```

信息关联代码匹配功能目录中的条目.

备注:

```text
13-8.2.2.14 FeatureAssociation HostGetFeatureAssociationTypeInfo(string featureAssociationCode)
```

返回值 :

```text
FeatureAssociation
```

CreatureFeatural Association 函数创建的 Lua 数据结构

参数:

```text
featureAssociationCode: string
```

特性关联代码匹配要素目录中的条目.

备注:

13-8.2.3 空间操作功能

这些功能使脚本环境能够对空间元素进行关系测试和操作.

主机必须执行下页所描述的功能,为脚本环境提供将空间实体相互连接的能力.

```text
13-8.2.3.1 boolean HostSpatialRelate(string spatialID1, string spatialID2, string intersectionPatternMatrix)
```

返回值 :

布尔

如果两个空间所代表的地理美因关系与DE-9IM矩阵中指定的相关,则返回真实性。

## 官方 PDF 第 658 页

参数:

```text
spatialID1: string
```

被主机用来独占地识别空间实例.

```text
spatialID2: string
```

被主机用来独占地识别空间实例.

```text
intersectionPatternMatrix: string
```

DE- 9IM 相交矩阵按行主顺序表示为九个字符。 例如, 当测试两个区域之间的重叠时 :“ T* T***T** ”

备注:

空间连接以空间ID1和空间ID2为代表的地缘测量,使用通过相交点PaternMatrix字符串指定的DE-9IM相交点.

DE-9IM字符串表示法的细节,参考了ISO 19125-1:2004,"地理信息-简单要素访问" 第1部分:共同架构 第6.1.14.2节:维度扩展九相间模型(DE--9im).

13-8.2.4 调试器支持功能

这些函数允许脚本环境与可能运行在主机上的调试器交互。 开发所需的标准主机函数时, 调试器可以作为辅助工具 。

调试器支持函数的主机执行是可选的。脚本将正常执行,无论主机是否执行这些函数。

```text
13-8.2.4.1 void HostDebuggerEntry(string debugAction, variant parameters)
```

返回值 :

无

参数:

```text
debugAction: string
```

显示请求的调试器动作 :

break – 暂停执行脚本.

track – 在调试控制台中显示字符串, 如第一个参数所提供.

start_performance – 按脚本代码的行形剖析开始行.

stop_polence – 按行图描述脚本代码的行站行. 性能计数器的名称在第一个参数中.

first_chance_error – 通知脚本中即将发生的错误函数调用的主机。参数是传递到错误函数的信件。第二个参数是传递到错误函数的深度。

参数:变体

用于调试动作的0个或更多参数.

备注:

此功能的主机执行是可选的 。
