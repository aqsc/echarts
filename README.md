# echarts

## ECharts: A Declarative Framework for Rapid Construction of Web-based Visualization.
## Echarts is a very good tool to show the data.

## ECharts implements a 2D vector drawing library named ZRender, which supports
display of visual forms in HTML5 canvas and manages graphic elements,
rendering as well as events.
#  Declarative Visualization Design
ECharts employs an all-in-one JSON format option to declare the compo130
nents, styles, data and interactions, resulting in a logicless and stateless mode.
The main advantage of JSON format lies in that it is safe to store, transmit and
execute, and is easy to do further validation.
Following the conventions of well-known tools like Microsoft Excel, ECharts
uses series to abstract a group of graphic elements that are mapped and encoded
135 from data. For example, all lines or bars in a cartesian coordinate system
form a series. Similarly, pie chart, treemap, graph or other chart types can
be abstracted as a series. In other words, a series is an instance of a type of
chart. Besides, ECharts uses component to name the functional unit like data
zooming, visual encoding and toolbox.
140 ECharts provides a method setOption to create or update the components
and series from the accepted option. If the setOption is to update the data,
ECharts employs a key-based diff algorithm to find the difference of data and
use proper transitions to display it.
# 3.1. Declarative Options
145 The declarative option is a hierarchical JSON object. On the top level,
all components, series and global settings are declared. In particular, global
settings, such as color palette, font and animation, are universal settings that
are posed on different series and components. ECharts checks whether the
key in the top level is registered as a component, then creates all components.
150 Otherwise the values are set as global settings.
Components like legend, tooltip, brushing, visualMap etc, are all optional.
Different components can be composed for different visualization purposes.
7
On the component level, properties are configured subject to associated com155
ponents, including layout, styles and states. Most states in ECharts components
are stored in the global option and change synchronously when a user interaction
happens. After getting the current global option including components states,
the view can be easily repeated in another environment. This is very useful for
debugging, replay and automated testing.
160 There is also a series field that contains one or more series of datasets and
their chart types. Most of the chart types have a coordinate system, like cartesian,
polar and geographic. A coordinate system is also defined as a component
on the top level. For a series, there are three ways to index the corresponding
coordinate system: index, ID and name, which are common for indexing any
165 other component.


## Coordinates Systems
195 In ECharts, the coordinate systems can be configured within the declarative
object model. The basic coordinate systems are Cartesian coordinate
system and Polar coordinate system. The former can be used through the
configuration xAxis and yAxis; while the latter is specified with: polar, radiusAxis
and angleAxis; Both coordinate systems can receive more than two
200 axes, which are identified by the index. ECharts Cartesian coordinate system
supports three kinds of axes: value, category and time.
ECharts provides two special coordinate systems: calendar and geomap. In
addition, ECharts automatically maps temporal or spatial information in the
data to corresponding coordinate systems. These systems can receive arbitrary
205 graphic elements targeted at specific positions. That means, other charts, such
as pie chart, can be drawn within the coordinate system.

## attention：
ECharts，一个使用 JavaScript 实现的开源可视化库，可以流畅的运行在 PC 和移动设备上，兼容当前绝大部分浏览器（IE8/9/10/11，Chrome，Firefox，Safari等），底层依赖轻量级的矢量图形库 ZRender，提供直观，交互丰富，可高度个性化定制的数据可视化图表。

ECharts 提供了常规的折线图、柱状图、散点图、饼图、K线图，用于统计的盒形图，用于地理数据可视化的地图、热力图、线图，用于关系数据可视化的关系图、treemap、旭日图，多维数据可视化的平行坐标，还有用于 BI 的漏斗图，仪表盘，并且支持图与图之间的混搭。

除了已经内置的包含了丰富功能的图表，ECharts 还提供了自定义系列，只需要传入一个renderItem函数，就可以从数据映射到任何你想要的图形，更棒的是这些都还能和已有的交互组件结合使用而不需要操心其它事情。
