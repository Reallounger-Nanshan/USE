# PX4 Gazbo仿真_相关指令

## (一) 启动

### 1. 启动四旋翼无人机仿真环境

* ```
  make px4_sitl_default gazebo
  ```

### 2. 启动MAVROS，链接到本地ROS

* ```
  roslaunch mavros px4.launch fcu_url:="udp://:14540@127.0.0.1:14557"
  ```

### 3. 创建外部控制程序包

* ```
  catkin_create_pkg offboard roscpp mavros geometry_msgs
  ```

### 4. 运行外部控制程序

* ```
  rosrun offboard offboard_node
  ```



## (二) 起飞与降落

### 1. 自动起飞

* ```
   commander takeoff
  ```

