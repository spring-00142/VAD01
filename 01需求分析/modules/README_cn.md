# VAD01

欢迎来到VAD01 modules。

## 安装
请安装GitHub Desktop进行VAD01项目协同开发管理
建议安装Sublime Text进行VAD01项目开发编辑
\\Apollo采用bazel作为代码编译构建工具，编译c++代码
\\每个源码文件夹下有一个BUILD文件，作用是按照bazel的格式来编译代码
\\OS:Ubuntu Linux 14.04

## 文档
顶层文档架构要求如下，
**modules文档树参考apollo-2.0.0文档树**：

[......]
[01需求分析]
   ┝[......]
   ┝[modules](01需求分析/modules/)：模块化设计
       ┝[calibration](01需求分析/modules/calibration/):标定校准模块
      *┝[canbus](01需求分析/modules/canbus/):CAN总线，收发指令，控制底盘并反馈状态
       ┝[common](01需求分析/modules/commmon/):公有的源码模块
      *┝[control](01需求分析/modules/control/):主控制模块 ，基于车道规划和车辆当前状态，输出转向、加速和制动控制信号到CAN卡
       ┝[data](01需求分析/modules/data/):收集、存储、处理收集到的各种数据
       ┝[dreamview](01需求分析/modules/dreamview/):一个Web应用，帮助用户随时掌握系统的输出数据，包括车道、位置、车身等情况
       ┝[drivers](01需求分析/modules/drivers/):CAN卡、雷达、GPS等驱动程序
       ┝[e2e](01需求分析/modules/e2e/):端到端的深度学习  
       ┝[elo](01需求分析/modules/elo/):百度的车辆自身定位，前向摄像头、全球定位系统、百度高精地图      
      *┝[localization](01需求分析/modules/localization/):车辆定位服务
      *┝[map](01需求分析/modules/map/):地图      
       ┝[monitor](01需求分析/modules/monitor/):监测硬件状态及整个系统的健康程度  
      *┝[perception](01需求分析/modules/perception):障碍物和红绿灯等交通信号感知
      *┝[planning](01需求分析/modules/planning/):根据车辆位置和车辆状态、地图、障碍物、导航信息等计算具体的车道
      *┝[prediction](01需求分析/modules/prediction/):计算障碍物的可能轨迹
      *┝[routing](01需求分析/modules/routing/):路径规划，根据地图和起点终点位置计算出具体的导航信息
       ┝[third_party_perception](01需求分析/modules/third_party_perception/):第三方感知
       └[tools](01需求分析/modules/tools/):通用监控与可视化工具
   └[......]
[......]

**整体流程**
首先，用户输入目的地，routing模块就可以根据终点位置计算出具体的导航信息。激光雷达、毫米波雷达和摄像头拍摄到的数据配合高精度地图由percepting模块计算出3D的障碍物信息并识别交通标志及交通信号，这些数据进入perdiction模块，计算出障碍物的可能轨迹，如此就可以结合以上信息并根据车辆定位模块localizationg提供的车辆位置由planning模块得到车辆应该走的具体车道。
得到车道后车辆control模块结合车辆的当前状态计算加速、刹车和方向的操作信号，此信号进入CAN卡后输出到车内，如此实现了车辆的自动驾驶。
在整个流程中，monitor模块会及时监测硬件及系统的健康状况，出现问题肯定就会中止驾驶过程。对于驾驶中的信息，用户可以通过web应用dreamview来查看，下图就是实际驾驶过程中的dreamview界面。

## 咨询

非常欢迎您随时提出疑问或提交bug报告

## 版权


## 免责声明
请参考免责声明

