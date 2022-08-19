# Catkin文档

---

[toc]



---

### 1. 基本概念

#### 1.1 Catkin

Catkin   元编译系统（meta-buildsystem）

最初目的是用于编译ROS社区中多个相互依赖的CMake工程

#### 1.3 源空间

+ 源空间包含catkin包的源码
+ 源空间下的每个目录都包含一个或多个 catkin 包

#### 1.4 构建空间



catkin：将 C++ 程序放入 ROS 框架中，以 ROS 标准形式编译



编译流程（抽象程度）：

https://blog.csdn.net/sinat_16643223/article/details/113935412

catkin_ws -> CmakeLists.txt -> Makefile

catkin -> cmake -> make

