# Catkin文档

---

[toc]



---

### 1. 基本概念

#### 1.1 catkin

catkin   元编译系统（meta-buildsystem）

最初目的是用于编译ROS社区中多个相互依赖的CMake工程

#### 1.2 catkin工作空间

catkin工作空间是一个目录，可以在其中修改、构建和安装 catkin 包

推荐和典型的[catkin工作空间](http://wiki.ros.org/catkin/workspaces#Catkin_Workspaces)布局：

```shell
workspace_folder/         -- WORKSPACE
  src/                    -- SOURCE SPACE
    CMakeLists.txt        -- The 'toplevel' CMake file
    package_1/
      CMakeLists.txt
      package.xml
      ...
    package_n/
      CATKIN_IGNORE       -- Optional empty file to exclude package_n from being processed
      CMakeLists.txt
      package.xml
      ...
  build/                  -- BUILD SPACE
    CATKIN_IGNORE         -- Keeps catkin from walking this directory
  devel/                  -- DEVELOPMENT SPACE (set by CATKIN_DEVEL_PREFIX)
    bin/
    etc/
    include/
    lib/
    share/
    .catkin
    env.bash
    setup.bash
    setup.sh
    ...
  install/                -- INSTALL SPACE (set by CMAKE_INSTALL_PREFIX)
    bin/
    etc/
    include/
    lib/
    share/
    .catkin             
    env.bash
    setup.bash
    setup.sh
    ...
```

#### 1.3 源空间

+ 源空间包含catkin包的源码
+ 源空间下的每个目录都包含一个或多个 catkin 包

#### 1.4 构建空间



catkin：将 C++ 程序放入 ROS 框架中，以 ROS 标准形式编译



编译流程（抽象程度）：

https://blog.csdn.net/sinat_16643223/article/details/113935412

catkin_ws -> CmakeLists.txt -> Makefile

catkin -> cmake -> make

