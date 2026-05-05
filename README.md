# ROS Programming

## Learning points
- Assisted in research work on Simultaneous Localization and Mapping (SLAM) algorithms by implementing RTAB-Map on a robot
- Improved path planning and obstacle detection accuracy by enhancing the quality of odometry data coming from sensors using robot_localization package
- Got acquainted with Robot Operating System (ROS) and modified source codes of packages to improve accuracy of experiments
- Compared the maps produced by robots with different SLAM algorithms running on them

## Revision
Terminal 1
- `source /opt/ros/jazzy/setup.zsh`
- `ros2 run demo_nodes_cpp talker`

Terminal 2
- `source /opt/ros/jazzy/setup.zsh`
- `ros2 run demo_nodes_py listener`

`echo "source /opt/ros/jazzy/setup.zsh" >> ~/.zshrc`

Turtlesim
- To start the simulator node: `ros2 run turtlesim turtlesim_node`
- To start the controller node: `ros2 run turtlesim turtle_teleop_key`

RQT
rqt is a graphical user interface (GUI) tool for ROS 2. Everything done in rqt can be done on the command line, but rqt provides a more user-friendly way to manipulate ROS 2 elements.
`rqt --force-discover`

How to control 2 turtles?
We can create a new turtle by `/spawn` in `rqt`
`ros2 run turtlesim turtle_teleop_key --ros-args --remap turtle1/cmd_vel:=turtle2/cmd_vel`

### Nodes and Topics
[Nodes](https://docs.ros.org/en/jazzy/Tutorials/Beginner-CLI-Tools/Understanding-ROS2-Nodes/Understanding-ROS2-Nodes.html):
- Run all commands in new terminal
- Run command: `ros2 run <package_name> <executable_name>`: `ros2 run turtlesim turtlesim_node`, `ros2 run turtlesim turtle_teleop_key`
- Name of all nodes: `ros2 node list`
- Remapping allows you to reassign default node properties, like node name, topic names, service names, etc., to custom values: `ros2 run turtlesim turtlesim_node --ros-args --remap __node:=my_turtle`
- Node info: `ros2 node info <node_name>`

[Topics](https://docs.ros.org/en/jazzy/Tutorials/Beginner-CLI-Tools/Understanding-ROS2-Topics/Understanding-ROS2-Topics.html):
- Topic list: `ros2 topic list -t`
- Echo command: `ros2 topic echo /turtle1/cmd_vel`
- Topic info: `ros2 topic info /turtle1/cmd_vel`
- Publish to the topic: `ros2 topic pub /turtle1/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 2.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 1.8}}"`

// TODO