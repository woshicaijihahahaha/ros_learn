# ros_learn
记录一下学ros过程中所运行的代码

 ****ROS命令行工具：

1、roscore命令用来打开节点管理器，是我们在运行ROS系统时必须要首先运行的指令

 2、 rosrun命令用来运行某个功能包里的某个结点，后面跟两个参数，第一个参数是功能包名，第二个参数是结点名，在输入功能包名后，按tab键，可以显示该功能包内的节点名。 如：rosrun turtlesim turtlesim_node
 
3、turtlesim中的turtle_teleop_key是键盘控制节点

4、ROS里面有一些rqt开头的工具，这都是一些可视化工具，比如rqt_graph是一个用来显示系统计算图的一个工具，通过这张图我们可以很快的了解这个系统的全貌

5、turtlesim是仿真器节点

6、rosnode工具用来显示系统中所有节点的相关信息

7、rosnode ping指令

8、rosnode list指令用来把系统中所有的节点都列出来

9、rosnode info指令用来查看某一个节点具体的信息是什么，如rosnode info /turtlesim （/turtlesim是节点名）

10、rosnode kill指令

11、rosnode cleanup指令

12、rosout是ros一个默认的话题，用来采集ros节点的运动信息，给上面的界面进行显示

13、rostopic list命令可以查看当前系统所有的列表

14、rostopic pub命令可以用来发布话题，后面跟的第一个参数是话题名，比如/turtle1/cmd_vel 这个时候双击两下tab键可以自动把后面的内容补全，按左右键可以设置输入位置，twist是我们发布的消息结构（数据结构），这个数据结构里包含两个部分一个是线速度linear，单位是m/s ，另一个是角速度angular，单位是rad/s，每个速度都分为xyz三个方向上的分量，若我们将linear的x设为1，则海龟将以1m/s的速度向前运行一次，这是因为rostopic pub命令只会发布一次，若在其后面加上-r 10 ，-r表示设定频率 ，-r 10 就是每秒运行10次循环 ，可以不断的发布，z轴是垂直于屏幕向外的，若将angular的z参数设为1，它就可以按圆的轨迹行走

15、如果我们想要查看某个消息的数据结构可以用 rosmsg show命令，比如rosmsg show geometry_msgs/Twist

16、rosservice list 可以查看当前仿真器下的提供的service服务，/spawn服务产生服务，可以用来产生一个新的海龟，如rosservice call /spawn 然后按tab键补全剩余的，其中call表示请求 ，x、y是产生新海龟的坐标，theta是初始角度，name是产生新海龟的名字

 17、rosbag工具是话题记录工具，记录系统中所有的话题记录并保存起来，下次用的时候再复现出来，例如话题记录命令 rosbag record -a -O cmd_record （其中record是记录的意思，-a是全部保存 -O是保存成压缩包，保存文件命名为cmd_record) 话题复现 命令rosbag play cmd_record.bag （play是表示复现，cmd_record.bag是文件名）在输入记录命令后，它会显示开始订阅一些信息，这时候我们用键盘去控制海龟移动，结束后按ctrl+c，他就会把这些数据保存下来，保存到我们的主文件（主目录）下，这个时候我们把之前打开的终端关掉，只打开节点管理器和仿真器节点，不需要启动键盘控制节点，此时使用话题复现命令，他就可以复现刚才我们保存的运动
 
 ![image](https://user-images.githubusercontent.com/105849204/182982525-5a9b3811-f52f-4993-8cac-f42f70cf6ce8.png)
 ![image](https://user-images.githubusercontent.com/105849204/182982637-c1007926-edf8-4b25-9b11-2f8b42edcfc9.png)

