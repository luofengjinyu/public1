# Catkin工作空间与Catkin包

---

[toc]



---

### 1. Catkin工作空间

#### 1.1 基本概念

Catkin工作空间是一个目录，可以在其中创建、构建、修改和安装 catkin 包

#### 1.2 Catkin工作空间组成

推荐和典型的Catkin工作空间文档树：

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



#### 1.3 创建并构建 Catkin 工作空间

创建工作空间

```shell
$ mkdir 工作空间名
```

进入工作空间 `catkin_ws` 目录下

```shell
$ cd ~/catkin_ws/
```

构建工作空间（构建并生成build、devel、src目录和相关文件）

```shell
$ catkin_make
```

将工作空间添加到 ROS 环境中（将工作空间中所有包添加到 ROS 环境中）

```shell
$ source ~/catkin_ws/devel/setup.bash
```







### 2. Catkin 包

#### 2.1 Catkin 包组成

最简单的catkin包组成：

```shell
my_package/
  CMakeLists.txt
  package.xml
```

最简catkin软件包的规则：

+ 必须有一个 `CMakeList.txt` 文件（ROS项目编译相关）
  + 如果catkin软件包是源包，则需要有一个 `CMakeList.txt` 文件的相关样板
+ 必须有一个catkin版本的 `package.xml` 文件（ROS项目依赖包与配置相关）
  + `package.xml` 文件提供该软件包的元信息
+ 一个目录下就是一个catkin包，一个目录下不能嵌套多个catkin包

#### 2.2  创建并构建 Catkin 包

切换到工作空间 catkin_ws 的 src 目录下：

```shell
$ cd ~/catkin_ws/src
```

##### 2.2.1 使用命令创建并构建catkin包

创建并构建一个名为 `beginner_tutorials` 的包，这个包依赖于`std_msgs`、`roscpp`和`rospy`：

```shell
$ catkin_create_pkg beginner_tutorials std_msgs rospy roscpp
```

##### 2.2.2 手动创建并构建catkin包

创建一个名为 `foobar` 的包

```shell
$ mkdir -p src/foobar
```

在 foobar 包目录下创建配置文件 package.xml 并编辑

```shell
<package>
  <name>foobar</name>
  <version>1.2.4</version>
  
  <!-- 包描述 -->
  <description>This package provides foo capability</description>
  
  <!-- 包维护者邮箱 包维护者姓名 -->
  <maintainer email="foobar@foo.bar.willowgarage.com">PR-foobar</maintainer>
  
  <!-- 许可证 -->
  <license>BSD</license>

  <!-- 构建工具依赖 -->
  <buildtool_depend>catkin</buildtool_depend>

  <!-- 构建包依赖 -->
  <build_depend>roscpp</build_depend>
  <build_depend>std_msgs</build_depend>

  <!-- 运行包依赖 -->
  <run_depend>roscpp</run_depend>
  <run_depend>std_msgs</run_depend>
</package>
```

在 foobar 包目录下新建 CMakeLists.txt 并编辑

```shell
cmake_minimum_required(VERSION 2.8.3)
project(foobar)
find_package(catkin REQUIRED roscpp std_msgs)
catkin_package()
```







