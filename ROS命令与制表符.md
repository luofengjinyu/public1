# ROS命令与制表符

---

[toc]



---



```shell
ROS命令：



rospack
rospack find 包名              //查找指定包的路径
rospack depends 包名           //递归列出包的所有依赖包
rospack depends1 包名          //列出指定包的一级依赖包



roscd 
roscd 目录名                   //跳转到指定目录下
roscd 目录名/子目录名           //跳转到指定目录下
roscd log                     //跳转到日志目录下



rosls 目录名                  //直接通过目录名而不是绝对路径列出指定目录下所有子目录和文件



roscp 包名 被拷贝文件路径 拷贝文件路径     //将文件从一个包复制到另一个包



roscore                      //运行roscore



rosnode                      //显示当前正在运行的ROS节点信息
rosnode list                 //列出当前正在运行的ROS节点
rosnode info /节点名          //显示指定节点的信息
rosnode ping 节点名           //测试指定节点



rosrun 包名 节点名                   //运行指定包中的节点
rosrun 包名 节点名 __name:=节点名     //运行指定包中的节点（使用重映射参数改变节点名）



rostopic echo 话题名                //显示在指定话题中发布的数据
rostopic list -v                   //列出所有发布和订阅的主题及其详细信息
rostopic type 话题名                //查看所发布话题的消息类型
rostopic type 话题名 | rosmsg show   //查看消息类型并显示消息详细信息
rostopic pub 话题名 消息类型 参数列表  //把数据发布到指定一个当前正在广播的话题上
rostopic pub -1 话题名 消息类型 参数列表  //把数据发布到指定一个当前正在广播的话题上，只发布一条消息就退出
rostopic pub 话题名 消息类型 -- 参数列表  //-- 表明这之后的是参数不是选项（如果参数带有-，那 -- 是必须的）
rostopic hz 话题名                  //显示数据发布的速率



rosmsg show 消息类型                //查看消息内容
rosmsg show 消息名                  //查看消息类型和消息内容
rossrv show 服务类型                //查看服务内容
rossrv show 服务名                  //查看服务类型和服务内容



rosservice list                    //输出活跃服务的信息
rosservice call /服务名 参数列表     //用给定的参数调用服务
rosservice type /服务名             //输出服务的类型
rosservice type /服务名 | rossrv show  //查看指定服务的信息
rosservice find                    //按服务的类型查找服务
rosservice uri                     //输出服务的ROSRPC uri



rosparam：在ROS参数服务器（Parameter Server）上存储和操作数据

rosparam set 参数名 参数值            //设置参数
rosparam get 参数名                  //获取参数
rosparam load 文件名 命名空间         //从文件中加载参数
rosparam dump 文件名 命名空间         //向文件中转储参数
rosparam delete 参数名               //删除参数
rosparam list                       //列出所有参数名



roslaunch：                         //用来启动定义在launch（启动）文件中的节点

roslaunch 包名 launch文件名          //启动定义在launch（启动）文件中的节点



rosbag record -a                   //将发布的所有话题录制到一个bag文件中
rosbag record -0 袋名 话题名 话题名   //将数据记录到指定名称的袋中，且只能订阅指定的两个话题
rosbag info 袋名                    //查看袋文件中包含话题的名称、类型和消息数量
rosbag play 袋名                    //回放bag文件以再现系统运行过程
time rosbag info 袋名               //查看所有已发布的话题和每个话题发布的消息



roswtf                             //检查系统并显示问题



rosdep install 包名                 //xiazaib
------------------------------------------------------------------------

制表符：

roscd tur <TAB>键                          //补全第一个匹配tur的单词turtle
roscd turtle <TAB>键<TAB>键<TAB>键         //列出所有turtle开头的目录
roscd turtles <TAB>键                      //补全唯一匹配turtles的目录turtlesim/
roscd turtlesim/ <TAB>键<TAB>键            //列出turtlesim目录下所有子目录

rosls <TAB>键<TAB>键                       //列出ROS安装目录（/opt/ros/kinetic/share）下所有子目录

-----------------------------------------------------------------------

Catkin命令：

catkin_make                          //在工作空间目录下使用，创建和构建catkin工作空间

catkin_create_pkg 包名 依赖包列表      //在当前目录下新建catkin包


```



```shell
常用节点命令：

roscore
rosrun turtlesim turtlesim_node             //运行turtlesim节点
rosrun turtlesim turtle_teleop_key          //运行键盘节点
rosrun rqt_graph rqt_graph                  //查看通信状态（节点与话题）
rosrun rqt_console rqt_console              //
rosrun rqt_logger_level rqt_logger_level

rosservice call /clear                      //清除turtlesim_node背景上的轨迹
rosservice call /spawn 2 2 0.2 ""           //在给定的位置和角度生成一只新的乌龟

rosparam set /background_r 150              //修改背景颜色的红色通道值
rosparam get /                              //显示参数服务器上的所有内容

rosbag play -s 5 袋名                       //从指定时间开始再现系统运行过程
rosbag play -r 2 袋名                       //以两倍速再现系统运行过程
```



