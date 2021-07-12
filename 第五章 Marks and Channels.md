## 第五章 Marks and Channels

### 5.2 Why Marks and Channels?

- 抽象的可视化 具体化之后的结果

### 5.3 Defining Marks and Channels

- 标记(marks)类似于下定义- 什么是什么（点线面体等）
- 通道(channel)类似于拿现成的定义做排列 - 什么比什么怎么样（这个点比那个高/大/远等）

	- 5.3.1 Channel Types

		- 多种多样，如长度，面积，颜色，亮暗等，可供比较的属性（A比B怎么样）

	- 5.3.2 Mark Types

		- 多种多样，点线面体之间的变换

### 5.4 Using Marks and Channels

- 同一组数据用不同的视觉通道，会表现出不一样的信息结果
- 选择之前应该先分析表达性与有效性（expressiveness and effectiveness），最后选择最好的那个

	- Expressiveness 表达性原则：可视化设计表达且仅表达数据集中的所有数据
	-  Effectiveness 有效性原则： 最重要的属性用最有效的通道表达，次要属性可以用次要通道

- 通道排名 图5.6

	- 排序属性可以用量级通道（Magnitude Channels），position的优先级最高
	- 类别属性可以用标识通道（Identity Channels）

### 5.5 Channel Effectiveness

- Accuracy 精确度，长期的实验可得图5.7结论，后来也发现长度和角度的比值是一样的。S=I^n，S是感知，I是物理强度

	-  aligned position  common scale
	- unaligned position  identical scale
	- length
	- angle
	- area

- Discriminability 辨识度  图5.9

	- 有限的更改某一标记的长宽等，可以有很高辨识度，图为飞机客流量，线宽可以很好地显示三四个不同的值，但如果是成百上千就很糟糕了

- Separability 可分离性 图5.10，但在某些特定情况下，可能次的却是最优解

	- position + color 最优，辨识度max
	- size + color 次之，因为小圆的颜色不太好分辨
	- width + height 再次之，因为我们只能感受到面积的变化，会认为竖条和横条是一种东西
	- red + green 最差，我们只能看到一堆颜色了

- Popout 脱颖而出

	- 某单个物体popout取决于干扰器对象
	- channel越好popout的效果越好，绝对不可能超过三个channel

- Grouping 分组

	- 链接标记
	- 标识通道（Identity Channels）
	- 接近性（proximity）

### 5.6 Relative versus Absolute Judgements

- 人的知觉系统是基于相对判断，而不是绝对判断——韦伯定律
