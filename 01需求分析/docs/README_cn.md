# VAD01

欢迎来到VAD01 GitHub。

## 安装
请安装GitHub Desktop进行VAD01项目协同开发管理
建议安装Sublime Text进行VAD01项目开发编辑
\\Apollo采用bazel作为代码编译构建工具，编译c++代码
\\每个源码文件夹下有一个BUILD文件，作用是按照bazel的格式来编译代码
\\OS:Ubuntu Linux 14.04

## 文档
顶层文档架构要求如下，
**docs文档树**：

[......]
[01需求分析]
   ┝[docs](01需求分析/docs/)此目录下可以找到VAD01文档
       ┝[demo_guide](01需求分析/docs/demo_guide/):演示指南
       ┝[FAQs](01需求分析/docs/FAQs/):常见问题
       ┝[howto](01需求分析/docs/howto/):编译、运行、修改代码教程
       ┝[quickstart](01需求分析/docs/quickstart/):快速入门手册   
       ┝[specs](01需求分析/docs/specs/):VAD01 v1.0 技术文档
       └[standards](01需求分析/docs/standards/):法规标准
   └[......]
[......]

**文档模版**
(01需求分析/)《00-Document Name-v1.0-(Drafter)-(Project No)-YYYY-MM-DD.doc》

**整体流程**
首先，用户输入目的地，routing模块就可以根据终点位置计算出具体的导航信息。激光雷达、毫米波雷达和摄像头拍摄到的数据配合高精度地图由percepting模块计算出3D的障碍物信息并识别交通标志及交通信号，这些数据进入perdiction模块，计算出障碍物的可能轨迹，如此就可以结合以上信息并根据车辆定位模块localizationg提供的车辆位置由planning模块得到车辆应该走的具体车道。
得到车道后车辆control模块结合车辆的当前状态计算加速、刹车和方向的操作信号，此信号进入CAN卡后输出到车内，如此实现了车辆的自动驾驶。
在整个流程中，monitor模块会及时监测硬件及系统的健康状况，出现问题肯定就会中止驾驶过程。对于驾驶中的信息，用户可以通过web应用dreamview来查看，下图就是实际驾驶过程中的dreamview界面。

## 咨询

非常欢迎您随时提出疑问或提交bug报告

## 版权


## 免责声明
请参考免责声明
