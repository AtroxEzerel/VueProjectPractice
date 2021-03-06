# 数据可视化

## 1.数据可视化前言

### 1.项目介绍演示

### 2.数据可视化概念

#### 1.什么是数据可视化

- 把数据以更直观的形式展示

#### 2.数据可视化的好处

- 清晰有效地传达与沟通信息
- 隐藏在数据中的信息

#### 3.可视化的实现方式

- 报表类
  - Excel
  - 水晶报表
- 商业智能BI
  - Microsoft BI
  - Power-BI
- 编码类
  - ECharts
  - D3.js

## 2.ECharts的基本使用

### 1.ECharts的介绍

ECharts是一个使用JavaScript实现的开源可视化库，兼容性强，底层依赖矢量图形库ZRender，提供直观，交互丰富，可高度个性化定制的数据可视化图表。

- 开源免费
- 功能丰富
- 社区活跃

### 2.ECharts特点

- 丰富的可视化类型
- 多种数据格式支持
- 流数据的支持
  - 流数据的动态渲染
  - 增量渲染技术
- 移动端优化
- 跨平台使用
- 炫丽的特效
- 三维可视化

ECharts能满足绝大多数可视化图表实现

- 兼容性强
- 使用方便
- 功能强大

实现数据可视化的最佳选择之一

### 3.ECharts的基本使用

- 步骤1:引入echarts.js文件
- 步骤2:准备一个呈现图表的盒子
- 步骤3:初始化echarts实例对象步骤
- 步骤4∶准备配置项
- 步骤5:将配置项设置给echarts实例对象

### 4.相关配置讲解

- xAixs:直角坐标系中的x轴
- yAixs:直角坐标系中的y轴
- series:系列列表。每个系列通过type决定自己的图标类型

## 3.Echarts常用图表

- 柱状图
- 折线图
- 散点图
- 饼图
- 地图
- 雷达图
- 仪表盘图

通用配置：指的是任何图表都能使用的配置

- 标题:title
  - 文字样式：textStyle
  - 标题边框：borderWidth,borderColor,borderRadius
  - 标题位置：left,top,right,bottom
- 提示：tooltip ==>提示框组件，用于配置鼠标滑过或点击图标时的显示框
  - 触发类型：trigger ==> item axis
  - 触发时机：triggerOn
  - 格式化：formatter
- 工具按钮：toolbox ==>ECharts提供的工具栏
  - 内置有导出图片，数据视图，动态类型切换，数据区域缩放，重置五个工具
  - 显示工具栏按钮 ：feature
- 图例：legend ：用于筛选系列，需要和series配合使用
  - legend中的data是一个数据
  - lengend中的data的值需要和series数组中的某组数据的name一致

### 1.柱状图

#### 1.步骤

- ECharts最基本的代码结构;引入js文件，DOM容器，初始化对象，设置option
- x轴数据：['杰斯', '伊泽', '亚托', '维尔', '凯特', '沃里', '婕拉', '雷克']
- y轴数据：[88, 92, 63, 74, 94, 85, 72, 96]
- 图表类型：type==>bar

#### 2.常见效果

- 标记：最大值、最小值、平均值==>markPoint markLine
- 显示：数值显示 柱宽度 横向柱状图

柱状图描述的是分类数据，呈现的是每一个分类中有多少，通过柱状图，可以很清晰的看出每个分类数据的排名情况。

### 2.折线图

#### 1.步骤

- ECharts最基本的代码结构;引入js文件，DOM容器，初始化对象，设置option
- x轴数据：['1', '2', '3', '4', '5', '6', '7', '8']
- y轴数据：[880, 920, 630, 740, 940, 850, 720, 960]
- 图表类型：type==>line

#### 2.常见效果

- 标记：最大值、最小值、平均值、标注区间==>markPoint markLine markArea
- 线条控制：平滑、风格 ==>smooth、lineStyle
- 填充风格 ==>areaStyle
- 紧挨边缘 ==>boundaryGap
- 缩放：脱离0值比例
- 堆叠图：stack

折线图常用来分析数据随时间变化的趋势。

### 3.散点图

散点图可以帮助我们推断出变量间的相关性

#### 1.步骤
- ECharts最基本的代码结构;引入js文件，DOM容器，初始化对象，设置option
- x轴的数据和y轴的数据：二维数组
  - 数组1[[身高,体重],[身高,体重],[身高,体重]...]

- 图表类型：在series下设置type:scatter
- xAxis和yAixs的type都要设置为value
- 调整：将坐标轴都设置为脱离0值比例,scale

#### 2.常见效果

- 气泡效果
  - 散点的大小不同 symbolSize
  - 散点的颜色不同 itemStyle.color
- 涟漪动画效果
  - type:effectScatter
  - showEffectOn:'emphasis'
  - rippleEffect:{}

特点：散点图可以帮助我们推断出不同维度数据之间的相关性

### 4.直角坐标系通用配置

直接坐标系图表：柱状图 折线图 散点图

- 1.网格grid
- 2.坐标轴axis
- 3.区域缩放dataZoom

#### 1.网格grid

- grid是用控制直角坐标系的布局和大小
- x轴和y轴就是在grid的基础上绘制的
  - 显示grid：show
  - grid的边框：borderWidth borderColor
  - grid的位置和大小：width height top left right bottom

#### 2.坐标轴axis

坐标轴分为x轴和y轴

一个grid中最多有两种位置的x轴和y轴

- 坐标轴类型type
  - value：数值轴，自动会从目标数据中读取数据
  - category：类目轴，该类型必须通过data设置类目数据
- 显示位置position
  - xAxis:可取值top或者bottom
  - xAxis:可取值left或者right

#### 3.区域缩放dataZoom

-  dataZoom用于区域缩放，对数据范围过滤，x轴和y轴都可以拥有
- dataZoom是一个数组，意味着可以配置多个区域缩放器
  - 类型type
    - silder:滑块
    - inside:内置，艺考鼠标滚轮或者双指缩放
  - 指明产生作用的轴
    - xAsisIndex：设置缩放组件控制的是哪个x轴，一般写0
    - yAsisIndex：设置缩放组件控制的是哪个y轴，一般写0
  - 指明初始状态的缩放情况
    - start:数据窗口范围的起始百分比
    - end:数据窗口范围的结束百分比


## 4.ECharts的高级使用

## 5.电商平台数据可视化实时监控系统

  - 1.后台搭建

  - 2.结合Vue开发图表组件

  - 3.WebSocket实现数据推送

  - 4.主题切换\页面切换\全屏切换......