## 课程链接资料

- 赛事官方资源下载链接：
  http://pan.iflytek.com:80/#/link/5CC9ABB04E4CA6B49523888E31C2AEB9
  访问密码：AaIG 
- ROS Wiki参考链接：
  http://wiki.ros.org/navigation
  http://wiki.ros.org/gmapping 
  http://wiki.ros.org/move_base 
  http://wiki.ros.org/dwa_local_planner 
  http://wiki.ros.org/teb_local_planner 
  http://wiki.ros.org/amcl 
  https://google-cartographer.readthedocs.io/en/latest/ 
- 参考链接：
  https://www.guyuehome.com/5652 
  https://www.guyuehome.com/6560 
  https://www.guyuehome.com/28057 
  https://www.guyuehome.com/28066 
  https://www.guyuehome.com/28068 
  https://www.guyuehome.com/9811 
- 大学生智能车网站
  https://smartcar.cdstm.cn/index 
- 古月学院·智能车竞赛课程专题课程
  https://class.guyuehome.com/all/4622984
- 古月居·智能车竞赛专题博客
  https://www.guyuehome.com/category/column/smartcar 



## 课程指令

- 运行仿真环境

  $ roslaunch gazebo_pkg race.launch

  $ rosrun teleop_twist_keyboard teleop_twist_keyboard.py

- 安装gmapping

  $ sudo apt-get install ros-melodic-gmapping

- 运行gmapping

  $ roslaunch gazebo_pkg race.launch

  $ roslaunch race_navigation gmapping_demo.launch

  $ rosrun teleop_twist_keyboard teleop_twist_keyboard.py

  $ rosrun map_server map_saver -f race
  
- 安装cartographer

  $ sudo apt-get install ros-melodic-cartographer-*
  
- 运行cartographer

  $ roslaunch gazebo_pkg race.launch
  $ roslaunch race_navigation cartographer_demo.launch
  $ rosrun teleop_twist_keyboard teleop_twist_keyboard.py
  
- cartographer保存地图

  $ rosservice call /finish_trajectory 0

  $ rosservice call /write_state "{filename: '${HOME}/race.pbstream'}"

  $ rosrun cartographer_ros cartographer_pbstream_to_ros_map -map_filestem=${HOME}/race

    -pbstream_filename=${HOME}/race.pbstream -resolution=0.05

- 自主导航（DWA）

  $ roslaunch race_navigation dwa_demo.launch

  $ rosrun race_navigation move.py

  $ python move.py 
  
- 自主导航（TEB）

  $ roslaunch race_navigation teb_demo.launch

  $ rosrun race_navigation move.py

- 参数动态调试工具

  $ rosrun rqt_reconfigure rqt_reconfigure
