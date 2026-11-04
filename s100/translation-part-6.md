# S-100 5.2.1 · 第 6 部分 · 坐标参考系

非官方机器翻译参考稿，尚未逐条人工校订。公式与代码保留原文，解释以英文规范为准。

## 官方 PDF 第 227 页

S-100 – 第6编

坐标参考系

## 官方 PDF 第 228 页

5.2.1版实质性变动摘要

已生效的概要条款

## 官方 PDF 第 229 页

中文目录（可用上方目录直接跳转）

6-1 范围 · 官方 PDF 231
6-2 规范性引用文件 · 官方 PDF 231
6-3  包概述 · 官方 PDF 232
6-3.1 包图 · 官方 PDF 232
6-4 包的详细说明 · 官方 PDF 233
6-4.1 识别对象包 · 官方 PDF 233
6-4.1.1 S100_IO_识别对象 · 官方 PDF 233
6-4.1.2 类别详情 · 官方 PDF 233
6-4.2 坐标参考系包 · 官方 PDF 234
6-4.3 单一计算机辅助系统 · 官方 PDF 234
6-4.3.1 化合物CRS · 官方 PDF 235
6-4.3.2 类别详情 · 官方 PDF 235
6-4.4 坐标系统包 · 官方 PDF 236
6-4.4.1 类别详情 · 官方 PDF 237
6-4.5 数据包 · 官方 PDF 239
6-4.5.1 类别详情 · 官方 PDF 240
6-4.6 协调行动一揽子计划 · 官方 PDF 241
6-4.6.1 类别详情 · 官方 PDF 243

## 官方 PDF 第 230 页

本页特意留空

## 官方 PDF 第 231 页

6-1 范围

S-100标准是为水道测量信息的制作者和使用者设计的,但其原则可以扩大到许多其他形式的地理信息,包括地图和文本文件。

S-100标准中对象的位置通过坐标来定义。这些坐标与位置相关。本部分介绍通过坐标系统和基准充分定义参考的所有必要要素。 它用坐标来定义空间参考的概念Schema,并描述定义1-、2-和3维空间坐标参考所需的最低数据。

除了定义坐标参考系所必需的要素外,本部分还描述了将坐标从一个坐标参考系中转换到另一个坐标的操作,其中包括数据转换和地图预测操作.

坐标参考系以及界定这些系统的单一要素可在注册簿中登记,或由组织在文件中加以界定,本部分介绍如何确定这些要素。

坐标参考系不得在本部分范围内随时间而改变。

6-2 规范性引用文件

下述引用文件对本文件的应用不可或缺。对于注明日期的参考文献,只适用所引用的版本。对于未标明日期的参考资料,适用所参考文件的最新版本(包括任何修正)。

ISO 19111:2007, 地理信息——通过坐标提供空间参考

ISO/TS 19103, 地理信息——概念计划语言

ISO 19115, 地理信息-元数据

## 官方 PDF 第 232 页

6-3 包概述

6-3.1 包图

图6.1显示了本部分所使用的软件包及其依赖性.

图6-1——中央RS软件包

使用坐标参考空间物体的要素在五个包中描述,所有包都依赖于“已识别对象”包,该包描述了将要素与外部定义联系起来的机制。

它还保证每个元素都可以被单独命名,以便在数据集或软件必须用程序中识别出. 为了方便使用类名的工作,每个包必须使用其类和数据类型的前缀. 下文表6-1显示了各种包的前缀:

表6-1——软件包前缀

软件包名前缀

识别对象 IO

坐标参考系SC

坐标系统 CS

数据 CD

CC 坐标操作

## 官方 PDF 第 233 页

6-4 包的详细说明

6-4.1 识别对象包

图6-2——已识别对象类图.

注:如果包的类图显示的是另一包的类别或类型,则将显示灰色背景。在这种情况下,不显示该类的所有细节;完整的细节将在类所属的包的分类图中加以说明。

```text
6-4.1.1
S100_IO_IdentifiedObject
```

本部分的每个类别都旨在有一个能够被识别和/或识别出来自S100_IO_被识别对象的外源的机制.

与 ISO 19111 不同,此类不是从外部文档中衍生出来的,而是使用外部标准定义的成员。此外,本部分没有其他类别来自外部标准。如果在 ISO 19.111 中这些类别继承了基本成员,则这些成员将被引入到适当的包图中。 这应提高这一组成部分的可读性,并避免在不绝对需要的情况下出现多重继承。

6-4.1.2 类别详情

表6-2——IO类的属性_识别对象

名称类型卡。 描述

名称 RS_ 识别符 1 用于识别对象的主名

标识符 RS_标识符 0.1 引用对象(外部)定义的标识符

别名通用名 0. * 该对象的替代名称

注释字符串0.1 对象的评论或信息 RS_识别器类型(取自ISO 19115) 有三部分:

1) 权威:CI_Citation [0.1];

2) 代码:字符串;

3) 代码空间:字符串 [0.1] version:字符串 [0.1].

## 官方 PDF 第 234 页

CI_Citation类型也在ISO 19115中被定义,详见该条目.

6-4.2 坐标参考系包

图6-3——坐标参考系类图.

此套件描述了所有坐标参考系所使用的基础类和所有由此组件支持的衍生子类。该图还显示了与其他套件中的类的关系。

坐标参考系是一个以基准与现实世界相接的坐标系统,一般来说,真实世界将是地球,尽管原理不仅限于地球. 坐标参考系(CRS)要么是单一的CRS,要么是复合的CSR.

6-4.3 单一计算机辅助系统

单个CRS由坐标系统和相关基准定义. S-100 支持以下类型的单个CRS:

1) 大地测量成像成像仪;

2) 预测的中央RS;

3) 纵向计算机辅助系统;

```text
4) ImageCRS.
```

## 官方 PDF 第 235 页

大地测量 CRS 与大地测量基准相关联,通常使用椭圆坐标系统(地经度,地经和地高等为3D). 大地测定 CRS也可以使用笛卡尔坐标系统 (3D,固定在地上). 在数据集中很少使用笛卡儿系统所引用的坐标,但在某些坐标转换过程中作为中间坐标使用.

预测的CRS是一种衍生的CSR,其基础是大地测量CRS,并使用地图投影进行坐标转换,其基本坐标系统总是笛卡尔坐标系统,预计的CRS经常被用于国家坐标系统。

垂直 CRS 是一个用于报告深度或高度的1D CRS,并与垂直基准相联. 椭圆形高地无法用垂直 CSR 捕获. Ellipsoidal 高地是大地测量 CRS 三维坐标图盘的组成部分,不能独立存在.

图像 CRS 与描述图像坐标系统与图像的关系的图像数据数据相关,这种关系独立于图像是否地理参照。地理参照是通过将图像 CSR 转换为大地测量或预测的 CRS来进行的。

6-4.3.1 化合物CRS

复合式CRS是两个或两个以上单个CRS的组合,尽管使用两个以上组件的可能性很小. 复合CRS的各个组件必须独立. 符合它们相配的坐标不能通过某种坐标操作从一个CRS变为另一个CRS,两个CRS就独立了. 例如,一个水平和垂直CRS都是独立的,而两个垂直CSR则不是独立的. 不允许将复合式CRS嵌入,这意味着所有组件必须是单一的CRS.

数据集中的每个位置, 与类 DirectPosition 相接, 必须绑定在 CRS 上。 如果数据集中对每个位置使用不同的垂直数据, 则必须定义垂直坐标系统。 这些垂直坐标系可以用作复合坐标系统中的组件来描述三维坐标 。

如果一个数据产品规范允许选择大地基准,即使在特定数据集中只允许一个数据,也必须指定转换方法,使数据集能够在必须用程序中一起使用.

6-4.3.2 类别详情

表6-3-SC_CRS类的属性

名称类型卡。 描述

1.* 说明使用量或使用限制,本计算机辅助系统对其有效

cRS 有效的区域或区域

表6-4——SC-SingleCRS类的属性

名称类型卡。 描述

CD_Datum 0.1 与计算机辅助系统相关联的计算机辅助系统的计算机辅助程序。计算机辅助设备必须具有适当的类型(垂直或水平)。除了预测的计算机专用系统外,不可对其加以具体说明。 预测的软件辅助系统使用其基础计算机辅助程序的计算机辅助设施。

坐标System CS_坐标System 1 用于 CRS 的坐标系统

表6-5——SC-GeneralDerivedCRS类属性

名称类型卡。 描述

转换 CC_ Operation 1 坐标转换方法,将坐标从基数转换为所衍生的 CRS(例如地图投影)

## 官方 PDF 第 236 页

表6-6——SC_预测的CRS类属性

名称类型卡。 描述

BaseCRS SC_GeodeticCRS 1 用于计算成份的大地测量式CRS,特别是基准式CRS的基准数据也用于计算成份的CRS。

6-4.4 坐标系统包

图6-4——"坐标系统"类图.

坐标系由非重复的、顺序排列的坐标轴组成。轴数应等于CRS所描述的几何空间的维数。坐标轴的顺序与使用该坐标系的CRS描述的每个坐标图中的坐标顺序相同。

本部分定义了四种类型的坐标系统:

(1) 笛卡尔坐标系统;

2) 轴坐标系统;

3) 椭圆坐标系统;

4)垂直坐标系统.

每个轴由方向,值范围以及所使用的计量单位来定义.

笛卡尔坐标系统是带有正弦直轴的二维或三维坐标系统,所有轴的长度单位必须相同.

外接坐标系统是二维或三维坐标系统,有直轴不一定为正交,所有轴的长度单位应相同.

椭圆坐标系是二维或三维坐标系,它描述椭圆表面或附近坐标,坐标为:大地纬度、地经度和(以三维为例)椭圆高度。

## 官方 PDF 第 237 页

大地纬度是赤道平面到椭圆形到椭圆形通过某一点的角,向北被视作正向.

大地经度是从正中线平面到给定点平面的角,向东被作为正中线.

椭圆高地是从椭圆上到这个点沿椭圆上行所测量出的一个点的相去,如果是上行或椭圆外行所测量出正相.

垂直坐标系统是用来记录点高或深度的一维坐标系统。这样的坐标系统通常取决于地球的重力场。下表指定了可使用特定类型的坐标系统的CRS的类型。

表6-7-用于不同CRS的坐标系统

坐标参考系 坐标参考系

CRS 椭圆坐标系统

笛卡尔坐标系统

```text
2, 3
```

```text
3
```

预计的CRS笛卡尔坐标系统2

CRS 垂直坐标系统 1

图像 CRS 笛卡尔坐标系统

Affine 坐标系统

```text
2
```

```text
2
```

6-4.4.1 类别详情

表6-8——CS-坐标系的属性

名称类型卡。 描述

轴 CS_坐标轴 1.3 坐标系统的轴,顺序与相应位置坐标的顺序相同。数字等于坐标系统描述几何的空间的尺寸。

表6-9—— CS- 坐标轴的属性

名称类型卡。 描述

此坐标系统轴所用的轴式Symbol CharlesString 1 缩写。

轴向 CS_轴向 1 坐标系统轴向。 对于一个被地球固定的坐标系统来说, 值常常是近似值, 意在为轴向提供人类可解释的含义 。

最小值为双0.1 轴的计算单位中允许该轴的最低值

最大值为双0.1 轴的计量单位中允许此轴的最大值

范围表示 CS_ RangeMeaning 0.1 数值范围的含义。

S100 计量单位 1 此轴的计量单位

## 官方 PDF 第 238 页

表 6-10-CS-轴心计算法的计数类型的定义

名称描述

在大地测量或预测的CRS中,北部通过大地测量基准来界定。

东轴正向 90° ( ⁇ /2 弧度) 从北向顺时针方向

南轴正向从北方向顺时针180°( ⁇ 弧度)

西轴正向为270°/3 ⁇ /2弧度) 从北向顺时针方向

轴向上升 相对于重力

轴向下 相对于重力正向下

地心X轴正向从模拟地球中心到赤道与正中线相接处的赤道平面

地心轴正向从模拟地球中心向赤道平面向赤道和地心线相接点向东走去

地心轴正向从地心模型中心与自转轴平行并朝北极方向移动

显示左向轴正向 。

显示正轴正向显示

显示 Up 轴正向显示

显示下轴正向下显示

表6-11——CS_RangeMeaning的计数类型定义.

名称描述

精确的包含 minValue 和 maxValue 之间的任何值都是有效的

环绕轴以在分数和最大值相绕的值相连续。具有相同含义的值重复了modulo(最大值-分数)。这方面的一个例子是大地经度;轴被定义为圆,而数值则被包围在 +(±180°)周围。

## 官方 PDF 第 239 页

6-4.5 数据包

图6-5——达通类图.

基准是一个参数或一组参数,用来定义一个坐标系统的起源位置,尺度和取向. S-100描述了三类基准:

(1) 大地测量基准;

(2) 纵向基准;

3) 图像基准。

大地基准确定二至三维坐标系统与地球的关系,通过椭圆形作为地球模型,由原始地线作为大地经度的起点。

垂直基准确定与地心重力相关的高度或深度之间的关系,用于参照垂直坐标系统,这种关系可能相当复杂。

椭圆形高地被视为与大地测量基准参照的三维椭圆形坐标系统有关,不能被垂直基准参照。

图像基准修正坐标系统和图像之间的关系。 这与图像是否地理参照无关。 图像 CS 用于定位图像中的位置, 而不是物体在现实世界中的位置 。

一般椭圆形是笛卡尔座标中给出的四相地表,由: .

## 官方 PDF 第 240 页

在a,b,c被称作椭圆形的半轴.

在大地测量学上,两个半轴是等分(a=b)和大于(c)的. 这个数字也叫取上位平面平面的平面石. S-100中,这个特例使用椭圆形来表示,两个正轴表示半主轴(a)和半小轴(b),并有大于(b)。

椭圆可按其两个半轴或以半主轴和半主轴来定义。

倒平调:

如果两个半轴均等, 椭圆是一个球体。 在这种情况下, 反平平面没有定义 。 (平面为 0 )

要定义大地经度(圆)轴上的出处,使用主经度,是其他经度的出处。

6-4.5.1 类别详情

表6-12——类CD属性_数据

名称类型卡。 描述

字符串 1..* 本基准对其有效的使用或使用限制说明

锚定字符串0.1 可能包括已查明点或点的坐标的描述,说明将坐标系统锚定在地球或备用物体上的关系

对于大地测量基准来说,这被称为基本点

对于一个图像基准,它通常是图像或图像中心的一角

实现 Epoch 日期为 0. 1 此基准定义生效的时间

域名:EQXX . 1 此数据有效的区域或区域

表 6-13 - 类 CD_ Ellipsoid 属性

名称类型卡。 描述

半主轴长度 1 椭圆形半主轴长度

第二Parameter CD_第二Parameter 1 定义椭圆的第二个参数,或者半小轴的长度,或者椭圆的倒平

表6-14——工会属性 CD_第二Paremeter

名称类型卡。 描述

反向平分双0.11 椭圆平分:

半微分轴长度为0.1椭圆形半微分轴长度

如果椭圆形是一个球体, 则为 . 1 。

表6-15——类CD的属性_PrimeMeridian

名称类型卡。 描述

从格林尼治地平线测得的地平线经度,正向东

1 必须确定一个成员。

## 官方 PDF 第 241 页

表6-16 CD类属性_地极数据

名称类型卡。 描述

椭圆平面 CD_ Ellipsoid 1 此数据时用作地球模型的椭圆平面

primeMeridian CD_PrimeMeridian 1 此数据的首要介质

表 6-17 — 类 CD_ Image Datum 的属性

名称类型卡。 描述

像素InCell CD_像素InCell 1 图像网格与图像数据属性关联方式的规格

表 6-18 — 盘点 CD_ 像素InCell 的定义

名称描述

单元格Center 图像坐标系统的由来是网格单元格或图像像素的中心

单元格Corner 图像坐标系统的由来是网格单元格的一角,或相邻图像像素中心之间的半程

6-4.6 协调行动一揽子计划

图6-6——坐标行动等级图.

坐标操作转换坐标,指一个坐标参考系来表示另一个坐标参考系的坐标,因此,每个坐标操作都有源 CRS 和目标 CRS.

S-100定义了下列类型的坐标操作:

1) 坐标转换;

## 官方 PDF 第 242 页

(2) 坐标转换;

3) 通过操作;

4) 密会坐标行动.

坐标转换变迁坐标从一个基于一个基准的坐标参考系到第二个基准的相坐标参考系的坐标转换,这些操作的参数通常都是在经验上推导出来的,参数的分解性质可能导致多个不同版本的同坐标转换. 因此,对一对特定的坐标参考系来说,可能存在多个坐标转换,它们的方法,参数值和准确性特征不同.

基于同一基准的两座坐标参考系之间的坐标转换变化坐标。这种坐标操作包括地图预测。通过操作可指定坐标图的子集,以进行请求的坐标操作。 其形式是参考另一项协调操作,并指定一系列数字,确定受该协调操作影响的坐标的坐标上的位置。

EXAMPLE 对于由复合参考系统定义的一拖轮高度坐标上的协调操作,通过操作过滤高度坐标后再将其传递给相关的坐标操作.

相接坐标操作是协调操作的不重复序列,这种坐标操作的顺序受到以下要求的限制:每一步的目标坐标参考系应与下一步的源坐标参考系的相同. 第一步的源代码坐标参考系和后一步的目标坐标参考系是为接地坐标操作指定的源和目标坐标参考体系. 接地协调操作可能包含坐标转换和相协调转换. 如果源与目标坐标参考系的基准是不同的,则整个操作就是坐标转换.

结合的一个例子是“Position 矢量7-参数转换”(EPSG 9606),在内部是下列的结合:

1) “地理/地心转换”(EPSG9602);

(2) 地心坐标上的海默特变换;以及

3) “地理/地心转换”的反例。

虽然第一步和最后一步是转换,并没有改变基准,但第二步是这样做的,因此整个操作是一个转变.

坐标转换和转换是使用相近数学概念的单坐标操作,这些概念(算法或程序)由操作方法定义,每个操作方法都由数学公式和一组参数完全定义,尽管这个集可能是空的.

操作的数学公式以文本形式或参考源文档的方式加以规定。

单个坐标操作的每个实例定义了对应操作方法每个参数的值. 参数和方法是可识别的对象,可以通过引用来定义.

## 官方 PDF 第 243 页

6-4.6.1 类别详情

表6-19-CC类协调行动属性

名称类型卡。 描述

字符串 1..* 说明这种坐标操作有效的使用或使用限制

操作Version字符String 0.1 坐标转换版本。在描述坐标转换时必须使用,不应为坐标转换提供

域名:EQX Extent 0.1 此坐标操作有效的区域或区域

精确度 DQQPOSTIONAL 准确度 0.1 这一坐标操作对点精度影响的估计

表6-20——CC-Single Operation类属性.

名称类型卡。 描述

方法 CC_ 操作方法 1 用于执行坐标操作的方法(算法或程序)

参数Value CC_OperationParameterValue 0.* 相关方法的每个参数的值

表 6-21-CC类的属性_连带操作

名称类型卡。 描述

CC_协调行动2. * 调制的有序行动顺序

表 6-22——CC_PassTrough操作类的属性

名称类型卡。 描述

修改坐标整数 1..* 排列正整数的顺序,以定义受此通过操作影响的坐标的坐标上所处位置

操作 CC_ 协调操作 1 的坐标操作, 此操作通过操作时指定坐标的子集

表6-23——CC类操作方法的属性.

名称类型卡。 描述

公式字符串 1 本操作方法所使用的公式或程序

参数 CC_OperationParemeter 0.* 此坐标操作方法所使用的一组参数

表 6-24- CC 类的属性_ 操作ParemeterValue

名称类型卡。 描述

值 CC_ParameterVale 1 坐标操作参数值。大多数参数值是数值,但其他类型的参数值是可能的

参数 CC_OperationParemeter 1 定义值的参数

## 官方 PDF 第 244 页

表6-25-工会属性 CC_ParameterValue

名称类型卡。 描述

S100_Measure 0.12 坐标操作参数的数值及其相关计量单位

字符串 Vale C字符串 0. 1 坐标操作参数的字符串值

整数 Value 整数 0. 1 坐标操作参数的整数值。 通常用于计算或索引

boleanValue bolean 0.1 坐标操作参数的布尔值

值 File 字符串 0. 1 引用包含一个或多个参数值的文件。 这可以是文件名或 URL 或其他一些参考文件的方法

2 必须确定一个成员。

## 官方 PDF 第 245 页

附录6-A

实例(信息)

附录中列出了四个例子,以表明使用所需信息来描述坐标参考系的情况:

1. 2D大地测量成像系统,参照外部来源;

2. 使用外部来源的参考文献预测计算机预报系统;

3. 同样的计算机辅助系统,界定所有已有的细节;

4. 将第一个例子与纵向计算机辅助系统相结合的复合式计算机辅助系统。

示例使用类似 XML 的缩写。 UML 标识符被用作元素名称。 数值以粗体显示。 要进行更好的概述, 数据类型可以包含在元素的名称中, 并且以蓝色显示 。

6-A-1 2D 使用外部来源参考的大地测量CRS

此示例使用 EPSG 大地测量参数数据集的引用。 请注意, SC_ CRS 类用于引用, 所有细节都在引用源中定义。 例外是范围, 因为这是 SC- CRS 有强制性 。

```text
<SC_CRS:example1>
```

```text
<RS_Identifier:name>
```

```text
<code>WGS 84</code>
</RS_Identifier:name>
<RS_Identifier:identifier>
```

```text
<CI_Citation:authority>
```

```text
<title>EPSG Geodetic Parameter Data Set</title>
<edition>6.5</edition>
<CI_Date:date>
```

```text
<date>20040113</date>
<dateType>revision</dateType>
</CI_Date:date>
</CI_Citation:authority>
<code>4326</code>
</RS_Identifier:identifier>
<scope>
```

GPS卫星系统使用的三维大地测量成像成像系统横向组成部分。 </scope > </SC_CRS:实例1 >

6-A-2 参考外部来源的预计计算机预报系统

这个例子与6-A-1相似,它通过引用EPSG大地测量参数数据集来定义预测的CRS.

```text
<SC_CRS:example2>
```

```text
<RS_Identifier:name>
```

```text
<code>Amersfoort / RD new</code>
</RS_Identifier:name>
<RS_Identifier:identifier>
```

```text
<CI_Citation:authority>
```

```text
<title>EPSG Geodetic Parameter Data Set</title>
<edition>6.5</edition>
<CI_Date:date>
```

```text
<date>20040113</date>
<dateType>revision</dateType>
```

## 官方 PDF 第 246 页

```text
</CI_Date:date>
</CI_Citation:authority>
<code>28992</code>
</RS_Identifier:identifier>
<scope>
```

中大尺度地貌测绘和工程勘察. </scope > </SC_CRS:实例2 >

6-A-3 界定所有细节的预计计算机预报系统

这个例子就是6-A-2的全部细节.

```text
<SC_ProjectedCRS:example3>
```

<! -- -- 名称和范围 -- > < RS_ 标识符:name >

```text
<code>Amersfoort / RD new</code>
</RS_Identifier:name>
<scope>
```

大型和中型地形测绘和工程调查。 </scope >

<!--- 坐标系统 -- > < CS_CartesianCS:坐标系统 >

<!-- 轴 # 1- > < CS_坐标轴:轴 >

```text
<RS_Identifier:name>
```

```text
<code>Easting</code>
</RS_Identifier:name>
<axisSymbol>X</axisSymbol>
<axisDirection>east</axisDirection>
<CS_UnitOfMeasure:unitOfMeasure>
```

```text
<RS_Identifier:name>
```

```text
<code>Metre</code>
</RS_Identifier:name>
<symbol>m</symbol>
<type>length</type>
</CS_UnitOfMeasure:unitOfMeasure>
</CS_CoordinateSystemAxis:axis>
<!-- axis # 2 -->
<CS_CoordinateSystemAxis:axis>
```

```text
<RS_Identifier:name>
```

```text
<code>Northing</code>
</RS_Identifier:name>
<axisSymbol>Y</axisSymbol>
<axisDirection>north</axisDirection>
<CS_UnitOfMeasure:unitOfMeasure>
```

```text
<RS_Identifier:name>
```

```text
<code>Metre</code>
</RS_Identifier:name>
<symbol>m</symbol>
<type>length</type>
</CS_UnitOfMeasure:unitOfMeasure>
</CS_CoordinateSystemAxis:axis>
</CS_CartesianCS:coordinateSystem>
<!-- end of the coordinate system -->
```

<! -- -- 坐标转换 -- -- > <CC_转换:转换 >

```text
<RS_Identifier:name>
```

## 官方 PDF 第 247 页

```text
<code>RD New</code>
</RS_Identifier:name>
<scope>
```

大型和中型地形测绘和工程调查。 </scope >

<!- -- 包括参数列表在内的操作方法 -- > <CC_Operation Method:method>

```text
<RS_Identifier:name>
```

```text
<code>Oblique Stereographic</code>
</RS_Identifier:name>
<formula>See EPSG guidance No. 7</formula>
<CC_OperationParameter:parameter>
```

```text
<RS_Identifier:name>
```

```text
<code>Latitude of natural origin</code>
</RS_Identifier:name>
</CC_OperationParameter:parameter>
<CC_OperationParameter:parameter>
```

```text
<RS_Identifier:name>
```

```text
<code>Longitude of natural origin</code>
</RS_Identifier:name>
</CC_OperationParameter:parameter>
<CC_OperationParameter:parameter>
```

```text
<RS_Identifier:name>
```

```text
<code>Scale factor at natural origin</code>
</RS_Identifier:name>
</CC_OperationParameter:parameter>
<CC_OperationParameter:parameter>
```

```text
<RS_Identifier:name>
```

```text
<code>False easting</code>
</RS_Identifier:name>
</CC_OperationParameter:parameter>
<CC_OperationParameter:parameter>
```

```text
<RS_Identifier:name>
```

```text
<code>False northing</code>
</RS_Identifier:name>
</CC_OperationParameter:parameter>
</CC_OperationMethod:method>
<!-- The parameter value # 1 -->
<CC_OperationParameterValue:parameterValue>
```

```text
<parameter>Latitude of natural origin</parameter>
<CC_ParameterValue:value>
```

```text
<CC_Measure:measure>
```

```text
<value>52° 9’ 22.1780” N</value>
<CS_UnitOfMeasure:uom>
```

```text
<RS_Identifier:name>
```

```text
<code>Degree</code>
</RS_Identifier:name>
<type>angle</type>
</CS_UnitOfMeasure:uom>
</CC_Measure:measure>
</CC_ParameterValue:value>
</CC_OperationParameterValue:parameterValue>
<!-- The parameter value # 2 -->
<CC_OperationParameterValue:parameterValue>
```

```text
<parameter>Longitude of natural origin</parameter>
<CC_ParameterValue:value>
```

```text
<CC_Measure:measure>
```

```text
<value>5° 23’ 15.5” E</value>
<CS_UnitOfMeasure:uom>
```

```text
<RS_Identifier:name>
```

## 官方 PDF 第 248 页

```text
<code>Degree</code>
</RS_Identifier:name>
<type>angle</type>
</CS_UnitOfMeasure:uom>
</CC_Measure:measure>
</CC_ParameterValue:value>
</CC_OperationParameterValue:parameterValue>
<!-- The parameter value # 3 -->
<CC_OperationParameterValue:parameterValue>
```

```text
<parameter>Scale factor at natural origin</parameter>
<CC_ParameterValue:value>
```

```text
<CC_Measure:measure>
```

```text
<value>0.9999079</value>
<CS_UnitOfMeasure:uom>
```

```text
<RS_Identifier:name>
```

```text
<code>Scale</code>
</RS_Identifier:name>
<type>scale</type>
</CS_UnitOfMeasure:uom>
</CC_Measure:measure>
</CC_ParameterValue:value>
</CC_OperationParameterValue:parameterValue>
<!-- The parameter value # 4 -->
<CC_OperationParameterValue:parameterValue>
```

```text
<parameter>False easting</parameter>
<CC_ParameterValue:value>
```

```text
<CC_Measure:measure>
```

```text
<value>155000</value>
<CS_UnitOfMeasure:uom>
```

```text
<RS_Identifier:name>
```

```text
<code>Metre</code>
</RS_Identifier:name>
<symbol>m</symbol>
<type>length</type>
</CS_UnitOfMeasure:uom>
</CC_Measure:measure>
</CC_ParameterValue:value>
</CC_OperationParameterValue:parameterValue>
<!-- The parameter value # 5 -->
<CC_OperationParameterValue:parameterValue>
```

```text
<parameter>False northing</parameter>
<CC_ParameterValue:value>
```

```text
<CC_Measure:measure>
```

```text
<value>463000</value>
<CS_UnitOfMeasure:uom>
```

```text
<RS_Identifier:name>
```

```text
<code>Metre</code>
</RS_Identifier:name>
<symbol>m</symbol>
<type>length</type>
</CS_UnitOfMeasure:uom>
</CC_Measure:measure>
</CC_ParameterValue:value>
</CC_OperationParameterValue:parameterValue>
</CC_Conversion:conversion>
<!-- end of coordinate conversion -->
```

<!-- 基准大地测量 CRS -- -- < SC_GeodeticCRS: BaseCRS >

<!--- 碱CRS坐标系统- >

## 官方 PDF 第 249 页

```text
<CS_GeodeticCS:coordinateSystem>
```

<!-- 轴 # 1- > < CS_坐标轴:轴 >

```text
<RS_Identifier:name>
```

```text
<code>Latitude</code>
</RS_Identifier:name>
<axisSymbol>φ</axisSymbol>
<axisDirection>north</axisDirection>
<CS_UnitOfMeasure:unitOfMeasure>
```

```text
<RS_Identifier:name>
```

```text
<code>Degree</code>
</RS_Identifier:name>
<symbol>°</symbol>
<type>angle</type>
</CS_UnitOfMeasure:unitOfMeasure>
</CS_CoordinateSystemAxis:axis>
<!-- axis # 2 -->
<CS_CoordinateSystemAxis:axis>
```

```text
<RS_Identifier:name>
```

```text
<code>Longitude</code>
</RS_Identifier:name>
<axisSymbol>λ</axisSymbol>
<axisDirection>east</axisDirection>
<CS_UnitOfMeasure:unitOfMeasure>
```

```text
<RS_Identifier:name>
```

```text
<code>Degree</code>
</RS_Identifier:name>
<symbol>°</symbol>
<type>angle</type>
</CS_UnitOfMeasure:unitOfMeasure>
</CS_CoordinateSystemAxis:axis>
</CS_GeodeticCS:coordinateSystem>
<!-- end of coordinate system of the base CRS -->
```

<! -- -- 大地测量数据 -- -- < CD_地表数据:datum >

```text
<RS_Identifier:name>
```

```text
<code>Amersfoort</code>
</RS_Identifier:name>
<scope>
```

大地测量、地籍、地形测绘、工程测量。 </镜 > < CD_Ellipsoid:ellipsoid >

```text
<RS_Identifier:name>
```

```text
<code>Bessel 1841</code>
</RS_Identifier:name>
<semiMajorAxis>6377397.155 m</semiMajorAxis>
<CD_SecondParameter:secondParameter>
```

```text
<inversFlattening>299.1528128</inversFlattening>
<CD_SecondParameter:secondParameter>
</CD_Ellipsoid:ellipsoid>
<CD_PrimeMeridian:primeMeridian>
```

```text
<RS_Identifier:name>
```

```text
<code>Greenwich</code>
</RS_Identifier:name>
<greenwichLongitude>0</greenwichLongitude>
<CD_PrimeMeridian:primeMeridian>
</CD_GeodeticDatum:datum>
<!-- end of the geodetic datum -->
</SC_GeodeticCRS:baseCRS>
```

## 官方 PDF 第 250 页

<! -- -- 基准大地测量成像仪的结束 -- -- < /SC_ProjectCRS:实例3 >

6-A-4 A 复合 CRS 将第一个例子与垂直 CRS 合并

这里定义了复合 CRS 。 水平组件将通过引用垂直组件来定义, 并用细节来定义( 同样只有垂直基准再次通过引用来定义 ) 。

```text
<SC_CompoundCRS:example4>
```

<! -- -- -- 水平组件 -- -- > < SC_CRS:组件 >

```text
<RS_Identifier:name>
```

```text
<code>WGS 84</code>
</RS_Identifier:name>
<RS_Identifier:identifier>
```

```text
<CI_Citation:authority>
```

```text
<title>EPSG Geodetic Parameter Data Set</title>
<edition>6.5</edition>
<CI_Date:date>
```

```text
<date>20040113</date>
<dateType>revision</dateType>
</CI_Date:date>
</CI_Citation:authority>
<code>4326</code>
</RS_Identifier:identifier>
<scope>
```

GPS卫星系统使用的三维大地测量成像成像仪的横向组件。

```text
</SC_CRS:component>
<!-- The vertical component -->
<SC_VerticalCRS:component>
```

```text
<RS_Identifier:name>
```

```text
<code>Mean low water springs</code>
</RS_Identifier:name>
<scope>Hydrography</scope>
<CS_VerticalCS:coordinateSystem>
```

```text
<RS_Identifier:name>
```

```text
<code>Gravity related depth</code>
</RS_Identifier:name>
<!-- axis # 1 -->
<CS_CoordinateSystemAxis:axis>
```

```text
<RS_Identifier:name>
```

```text
<code>Depth</code>
</RS_Identifier:name>
<axisSymbol>z</axisSymbol>
<axisDirection>down</axisDirection>
<CS_UnitOfMeasure:unitOfMeasure>
```

```text
<RS_Identifier:name>
```

```text
<code>Metre</code>
</RS_Identifier:name>
<symbol>m</symbol>
<type>length</type>
</CS_UnitOfMeasure:unitOfMeasure>
</CS_CoordinateSystemAxis:axis>
<!-- The vertical datum (referenced to S-57 Attribute Catalogue) -->
<CD_VerticalDatum:datum>
```

```text
<RS_Identifier:name>
```

```text
<code>Mean low water springs</code>
</RS_Identifier:name>
```

## 官方 PDF 第 251 页

```text
<RS_Identifier:identifier>
```

```text
<CI_Citation:authority>
```

```text
<title>
```

IHO 数字九氢数据传输标准-附件A </title > <edition > 3.1 </edition > <CI_日期:日期 >

```text
<date>200011</date>
<dateType>publication</dateType>
</CI_Date:date>
</CI_Citation:authority>
<code>VERDAT 1</code>
</RS_Identifier:identifier>
<scope>Hydrography</scope>
</CD_VerticalDatum:datum>
</CS_VerticalCS:coordinateSystem>
```

```text
</SCVerticalCRS:component>
</SC_CompoundCRS:example4>
```

## 官方 PDF 第 252 页

本页特意留空
