# ROS软件包

---

[toc]



---



### 1. catkin软件包组成

最简单的catkin软件包组成：

```shell
my_package/
  CMakeLists.txt
  package.xml
```



最简单的catkin软件包规则：

+ 必须有一个catkin版本的package.xml文件
  + `package.xml` 文件提供该软件包的元信息
+ 必须有一个catkin版本的package.xml文件
  + 如果catkin软件包是源包，则需要有一个 `CMakeList.txt` 文件的相关样板
+ 同一个目录下只能有一个catkin软件包

