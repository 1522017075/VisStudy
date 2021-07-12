## 第七章 Arrange Tables

### 7.2 Why Arrange?

- 空间通道是最关键的视觉编码选择

### 7.3 Arrange by Keys and Values

- 键

	- 分类或排序的唯一性值

- 值

	- 分类、排序和数字类型的依赖属性

### 7.4 Express: Quantitative Values

- 例子：散点图

	- What: Data

		- 2个value：可计数quantitative

	- How: Encode

		- xy轴上的的位置标识一个点

	- Why: Task

		- 发现趋势、异常值、分布、相关性；定位集群

	- Scale 几百上千

### 7.5 Separate, Order, and Align:
Categorical Regions

- 分成区域

	- 根据分类属性（categorical）进行分离区域

- 排序区域

	- 根据排序属性（ordered）进行排序和对齐

- 对齐区域（可选）
- 7.5.1 List Alignment: One Key

	- 条形图（柱状图）

		- What: Data

			- key：分类categorical 
			- value：可计数quantitative

		- How: Encode

			- 1D 线Mark，用对齐的垂直位置表示值属性，用水平位置分隔键属性

		- Why: Task

			- 查找与比较

		- Scale 几十到几百

	- 堆叠条形图（柱状上进行编码）

		- What: Data

			- 2个key：分类categorical 
			- value：可计数quantitative

		- How: Encode

			- 每个二级键属性类别的值属性的长度编码子组件的条形（柱状图的柱子）。其他的同条形图

		- Why: Task

			- 查找与比较

		- Scale 几十到几百

	- 流图

		- What: Data

			- key：分类categorical 
			- value：有序ordered
			- value：可计数quantitative

		- What: Derived

			- One quantitative attribute (for layer ordering).

		- How: Encode

			- Use derived geometry showing artist layers across
time, layer height encodes counts

		- Scale

			- 关键key，横向时间轴，数百个时间点
			- 关键value，竖向高度，几十到几百

	- 点和折线图

		- What: Data

			- key：有序ordered
			- value：可计数quantitative

		- How: Encode

			- 横轴为key竖轴值

		- 点图连起来就成了折线图，折线图可以显示trend
		- Scale 几百

- 7.5.2 Matrix Alignment: Two Keys

	- 热图

		- What：Data

			- 2个key：类别属性categorical
			- value：可计数quantitative

		- How: Encode

			- 2D矩阵对齐面积，发散颜色图

		- Why: Task

			- Find clusters, outliers; summarize，找到聚类，离群点，总结

		- Scale

			- Items：百万级别
			- Categorical attribute levels：上百
			- Quantitative attribute levels：3~11

	- 集群热图

		- What: Derived

			- T wo cluster hierarchies for table rows and columns

		- How: Encode

			- Heatmap: 2D matrix alignment, ordered by both cluster hierarchies. 
			- Dendrogram: connection line marks for parent–child relationships in tree.

- 3个及以上key就太臃肿了，不好设计

### 7.6 Spatial Axis Orientation

- 空间轴的方向：直线，平行，还是径向
- 平行坐标图

	- What: Data

		- 很多value属性

	- How: Encode

		- 平行布局:水平空间位置用于分隔轴，垂直空间位置用于表示沿每个对齐轴的值，连接线标记作为它们之间的线段。

	- Why: T asks

		- 找出趋势、异常值、极端值、相关性。

	- Scale

		- 属性:沿副轴数十。项目:数百个。

- 径向条形图

	- What: Data

		- one quantitative attribute, one categorical attribute

	- How: Encode

		- 1D线为Mark，放射状布局

- 饼图

	- What: Data

		- one quantitative attribute, one categorical attribute.

	- Why: T ask

		- 部分-整体 关系

	- How: Encode

		- 带角度通道的2D Mark，放射状布局

	- Scale

		- One dozen categories.

- 极坐标图

	- What: Data

		- one quantitative attribute, one categorical attribute.

	- Why: T ask

		- 部分-整体 关系

	- How: Encode

		- 带角度通道的2D Mark，放射状布局

	- Scale

		- One dozen categories.

- 标准堆叠条形图

	- What: Data

		- one quantitative attribute, two categorical attribute.

	- What: Derived

		- One quantitative value attribute

	- Why: T ask

		- 部分-整体 关系

	- How: Encode

		- 带长度通道的1D Mark，放射状布局

	- Scale

		- 十几个 categories for 堆叠 attribute. 
		- 几十个categories for 轴 attribute.

### 7.7 Spatial Layout Density

- 7.7.1 Dense密集

	- vs的代码整体预览框

- 7.7.2 Space-Filling

	- 填充空间中的空白，三种属性均可
