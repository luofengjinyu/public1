# ROS命令与制表符

---

[toc]



---



ROS命令：



rospack
rospack find 包名              //查找指定包的路径

roscd 
roscd 目录名                   //跳转到指定目录下
roscd 目录名/子目录名          //跳转到指定目录下
roscd log                     //跳转到日志目录下

rosls 目录名                  //直接通过目录名而不是绝对路径列出指定目录下所有子目录和文件

制表符：

roscd tur <TAB>键                          //补全第一个匹配tur的单词turtle
roscd turtle <TAB>键<TAB>键<TAB>键         //列出所有turtle开头的目录
roscd turtles <TAB>键                      //补全唯一匹配turtles的目录turtlesim/
roscd turtlesim/ <TAB>键<TAB>键            //列出turtlesim目录下所有子目录
rosls <TAB>键<TAB>键                       //列出ROS安装目录（/opt/ros/kinetic/share）下所有子目录