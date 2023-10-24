

# ROS常用指令

## (一) 创建工作空间

### 1. 创建工作空间

~~~
mkdir -p ~/[workspace name]/src
cd ~/[workspace name]/
catkin_make
~~~

### 2. 添加环境变量

~~~
source devel/setup.bash
~~~

### 2. 检查环境变量是否包含工作空间

~~~
echo $ROS_PACKAGE_PATH
~~~

* ~/.bashrc文件从最后一条ROS的环境变量开始查阅，后面的工作空间会覆盖前面的工作空间



## (二) 创建软件包

### 1. 创建软件包

~~~
cd ~/[workspace name]/src
catkin_create_pkg [package name] std_msgs rospy roscpp [other denpends]
cd ~/[workspace name]
catkin_make
~~~

### 2. 查看一级依赖

~~~
rospack depend1 [package]
~~~

### 3. 查看所有依赖

~~~
rosnode depend [package]
~~~

### 4. 编译单个软件包

```
catkin_make -DCATKIN_WHITELIST_PACKAGES="[package_name]"
```

### 5. 编译多个软件包（非全部）

```
catkin_make -DCATKIN_WHITELIST_PACKAGES="[package_name1];[package_name2]"
```



## (三) 基本指令

### 1. 查看结点

~~~
rospack find [package]
~~~

### 2. 查看结点信息

* roscd不需要知道软件包绝对路径即可进入

* 进入软件包根目录

~~~
roscd [package]
~~~

* 进入软件包子目录

~~~
roscd [package]/[dir]
~~~

* 进入日志存储目录

~~~
roscd log
~~~

### 3. 查看软件包及其子目录下文件

~~~
rosls [package]/[dir]
~~~



## (四) rosnode

### 1. 查看结点

~~~
rosnode list
~~~

### 2. 查看结点信息

~~~
rosnode info [topic]
~~~



## (五) rostopic

### 1. 查看话题类型

~~~
rostopic type [topic]
~~~

### 2. 查看话题参数类型

~~~
rostopic echo [topic]
~~~

### 3. 发布指令

* 发布指令（发布结束不退出指令）

~~~
rostopic pub [topic] [msg_type] [args]
~~~

* 发布一次指令（发布结束退出指令）

~~~
rostopic pub -1  [topic] [msg_type] -- [args]
~~~

* 按一定频率发布指令

```
rostopic pub   [topic] [msg_type] -r [Hz] -- [args]
```

### 4. 查看话题发布频率

~~~
rostopic hz [topic]
~~~



## (六) rosservice

### 1. 调用服务

~~~
rosservice call [service] [args]
~~~



## (七) rosparam

### 1. 设置参数

~~~
rosparam set [param_name]
~~~

### 2. 获取参数

~~~
rosparam get [param_name]
~~~

### 3. 向文件中转储参数

~~~
rosparam dump [file_name] [namespace]
~~~

### 4. 从文件中加载参数

~~~
rosparam load [file_name] [namespace]
~~~



## (八) rosed

### 1. 直接通过软件包编辑包中文件

```
rosed [package_name] [filename]
```



## (九) rosbag

### 1. 记录数据

* 需要新建一个目录用于存储生成的文件
* -a表示记录所有数据

~~~
rosbag record -a
~~~

* 将数据记录到指定文件中（不加.bag尾缀），且只记录指定的话题信息

```
rosbag record -0 [bag name] [topic]
```

### 2. 查看bag文件信息

~~~
rosbag info [bagfile]
~~~

### 3. 回放bag文件信息

~~~
rosbag play -s [time] -d [time] -r [Hz] [bagfile]
~~~

* -s：设置回访开始时间，默认bag文件起始处
* -d：设置公告后发布bag文件内容的等待时间
* -r：设置回放频率

### 

## (十) roswtf

### 1. 检查系统异常

~~~
roswtf
~~~



## (十一) rosdep

### 1. 安装软件包相关依赖

~~~
rosdep install [package]
~~~



## (十二) rqt

### 1. 查看结点关系

~~~
rqt_graph
~~~

### 2. 查看日志

~~~
rosrun rqt_console rqt_console
~~~

### 3. 调整日志内容及等级

~~~
 rosrun rqt_logger_level rqt_logger_level
~~~

### 4. 可视化话题参数变化情况

~~~
 rosrun rqt_plot rqt_plot
~~~



## (十三) TF

### 1. 查看 TF 树

~~~
rosrun rqt_tf_tree rqt_tf_tree
~~~

### 
