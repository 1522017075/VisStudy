## 第九章 Arrange Networks and Trees

### 概述

- 节点-链接图
- 临街矩阵图
- 树结构

### 9.2 Connection: Link Marks

- 概念

	- 树和网络数据最常见的视觉编码习惯用法是节点链接图
	- 垂直树-垂直空间可表现树高，水平方向无编码，只确保最大信息密度。通道是空间位置
	- 径向树-树根为圆心，其余相同
	- 图9.3 5161个节点的两种树表示

		- a) 矩形水平节点-链接布局（Rectangular horizontal node–link layout）
		- b)气泡树节点-链接图（BubbleTree node–link
layout）

	-  跳数（离散量）

		- 从一个节点到另一个节点必须经过的单个链路的数量
		- ○——○  这种单个链接直接连接的节点，是最紧密的分组
		- 跳数越大，说明这两个节点越不紧密

- Force-Directed Placement（力导向放置图）

	- 概述

		- 从0开始随机放置节点与链接，根据物理力的模拟来定位网络元件，其中节点彼此推开，而链路像弹簧一样将它们的端点节点拉得彼此更近
		- 通常用节点大小或颜色，或链接的线宽作通道编码
		- 不足：

			- 有时一些节点会巧合的在空间上接近，看起来像是有分组关系，但其实没有，这会误导用户。
			- 随机性，每次运行算法时他们看起来都不太一样
			- 个数多的话，就会看起来一团糟

	- 总结

		- What: Data

			- Network. 网络

		- How: Encode

			- Point marks for nodes, connection marks for links（0D点作节点，链接Mark作为连接）

		- Why：task

			- 探索拓扑，找到路径

				- 拓扑任务的示例包括查找从一个节点到另一个节点的所有可能路径、查找两个节点之间的最短路径、查找距离目标节点一跳的所有相邻节点

		- Scale

			- 节点：几十上百
			- 节点/链接 的比值：Link < 4Node(图9.5)

### 9.3 Matrix Views

-  Adjacency Matrix View（邻接矩阵视图）

	- 概述：两个维度来表示节点-链接图，有向图和无向图均可
	- What: Data

		- Network. 网格

	- How: Encode

		- 2D矩阵排列中的区域标记。

	- What: Derived

		- Table：节点作为键，两个节点之间的链接状态作为值

	- Scale

		- 节点：上千
		- 链接：百万

### 9.4 Costs and Benefits: Connection
versus Matrix

- 链接

	- 优点：直观，可以看到大体结构
	- 缺点：链接数量有限，会相互遮挡，多的话就会变成毛球
	- 适合小型网络

- 矩阵

	- 优点：完全消除了遮挡，并且可以预测需要用到多大的屏幕像素空间，稳定
	- 缺点：需要解释成本，要有预备知识（矩阵）等。对研究拓扑任务等不如链接直观
	- 适合大型网络

### 9.5 Containment: Hierarchy Marks

- Treemaps

	- 概述：用包含代替链接
	- What: Data

		- Tree

	- How: Encode

		- 2D面积，包含

	- Why: T asks

		- 叶节点上的查询属性

	- Scale

		- 叶节点:一百万
		- 链接:一百万

- GrouseFlocks

	- 概述：一张图中既有连接关系，又有层级关系的时候
	- What: Data

		- Network. 网络

	- What: Derived

		- 原始网络上的集群层次结构

	- What: Encode

		- Connection marks for original network。对原始网络使用连接标记
		- Containment marks for cluster hierarchy。对层次结构使用包含标记
