# ROS图

---

[toc]



---

[计算图（Computation Graph）](http://wiki.ros.org/cn/ROS/Concepts#ROS.2Bi6F7l1b.2BXEJrIQ-)是一个由ROS进程组成的点对点网络，它们能够共同处理数据

+ 节点（Nodes）：节点是一个可执行文件，它可以通过ROS来与其他节点进行通信

+ 消息（Messages）：订阅或发布话题时所使用的ROS数据类型

+ 话题（Topics）：节点可以将消息*发布*到话题，或通过*订阅*话题来接收消息
+ 主节点（Master）：ROS的命名服务，例如帮助节点发现彼此
+ rosout：在ROS中相当于 `stdout/stderr（标准输出/标准错误）`
+ roscore：主节点 + rosout + 参数服务器





- [msg](http://wiki.ros.org/msg)（消息）：msg文件就是文本文件，用于描述ROS消息的字段。它们用于为不同编程语言编写的消息生成源代码
- [srv](http://wiki.ros.org/srv)（服务）：一个srv文件描述一个服务。它由两部分组成：请求（request）和响应（response）

msg文件就是简单的文本文件，每行都有一个字段类型和字段名称。可以使用的类型为：

- int8, int16, int32, int64 (以及 uint*)
- float32, float64
- string
- time, duration
- 其他msg文件
- variable-length array[] 和 fixed-length array[C]



消息类型包含两部分：

- `beginner_tutorials` -- 定义消息的软件包
- `Num` -- 消息的名称`Num`



msg文件：

```msg
Header header
string child_frame_id
geometry_msgs/PoseWithCovariance pose
geometry_msgs/TwistWithCovariance twist
```



srv文件：

```srv
//请求部分
int64 A
int64 B

---

//响应部分
int64 Sum
```



