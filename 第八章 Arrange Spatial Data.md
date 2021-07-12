## 第八章 Arrange Spatial Data

### 概述

- 某些具有空间意义的数据集，通常使用空间信息来指导布局，而不用其他的
- 两种主要的空间数据类型是几何和空间字段，几何通常是地图，或者空间场（张量向量）

### 8.2 Why Use Given?

- 为什么使用给定的空间类型的数据做主要可视化设计。
- 因为空间数据 的常见情况是，给定的空间位置是最重要的属性，中心任务围绕着理解空间关系。也遵循着有效性原则

### 8.3 Geometry

- 几何数据不一定有与之相关的属性:它通过其元素的空间位置直接传达形状信息
- 8.3.1 Geographic Data

	- 等值线图

		- What: Data

			- 地理几何数据。每个区域只能有一个定量属性

		- How: Encode

			- 空间:使用给定的几何图形作为区域标记边界。颜色:顺序分段颜色图

### 8.4 Scalar Fields: One Value 

- 等值线/等高线（最明显的是地形图，图8.3b给出了牙齿透视图，用了五个不同的等值面）

	- 地形图

		- What: Data

			- 2D空间场；地理数据

		- What: Derived

			- 几何图形:根据字段计算的等值线集 

		- How: Encode

			- 在地图上，把一样高的地方画成线，可以看出地形

		- Why: T asks

			-  查询形状

		- Scale

			-  几十个高度

	- 灵活的等值面

		- What: Data

			- 空间场

		- What: Derived

			- 几何图形:曲面
			- 树：简化等高线树

		- How: Encode

			- 外观：给定数据
			- 树：1DMark，垂直空间位置编码等值

		- Why: T asks

			-  查询形状

		- Scale

			-  十几个等高线

	- 直接体绘制

		- What: Data

			- 3D空间场

		- What: Derived

			- 三维空间场
			- 原始场的梯度
			- T able: two key attributes, values binned from min to max for both data and derived data. One derived quantitative value attribute (item count per bin)

		- How: Encode

			- 3D视图：使用多维传递函数给定的空间场数据，颜色，和透明度
			- 联合直方图视图：2DMark在矩阵中对齐的区域标记，灰度顺序彩色图

		- 例图：8.6，人脑图，直接在截面上画对应的剖面。直接体绘制的一个重要视觉编码设计选择是选择将标量值的变化映射到不透明度和颜色的传递函数。手动找到正确的传递函数通常需要大量的尝试和错误，因为空间域中感兴趣的特征可能很难隔离:空间中不感兴趣的区域可能包含与感兴趣的区域相同范围的数据值

### 8.5 Vector Fields: Multiple Values

- 箭头矢量场图

	- 画这种图的三个主要任务：
	- 1.找到所有的临界点并确定他们的类型
	- 2.识别特定位置的临界点类型
	- 3.预测从特定点开始的粒子最终被输送到哪里

- 8.5.1 Flow Glyphs

	- 流动图示符，基本使用箭头标识矢量场，最好是2D，因为3D会存在遮挡问题

- 8.5.2 Geometric Flow

	- 相似性聚类流线（Similarity-Clustered Streamlines）

		- What: Data

			- 3D向量场

		- What: Derived

			- 几何：流线或路径线
			- 一个属性 per 流线或路径线
			- 流线/路径线的集群层次结构

		- How: Encode

			- 根据聚类使用线条、颜色和不透明度的衍生几何图形

		- Why: Tasks

			- 找到特征，查询形状

		- Scale

			- 场：数百万样本
			- 几何：数百条流线

- 8.5.3 Texture Flow

	- 纹理流习惯用法也依赖于粒子追踪，但是覆盖了整个领域，而不是从一组精心选择的种子点
	- 常用于2D场

- 8.5.4 Feature Flow

	- 特征流/拓扑流

### 8.6 Tensor Fields: Many Value

- 椭球张量图示符（Ellipsoid Tensor Glyphs）

	- 名词解释

		- 各向同性：从原点向各个方向扩散的速率相同
		- 各向异性：从原点向某几个方向扩散的速率相同
		- 完全各项同性的模型是一个球，部分各项同性的模型是一个2D椭圆（扁平），完全各向异性是1D线性的

	- What:Data

		- 3D张量场

	- What：Derived

		- Three quantitative attributes: tensor shape. 三个可数属性：张量形状                          
Three vectors: tensor orientation.                                                     三个向量：张量的方向

	- How：Encode

		- Glyph showing six derived attributes, color and opacity according to cluster.(图示符根据集群显示了六个派生属性，颜色和透明度)
