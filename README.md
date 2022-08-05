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

