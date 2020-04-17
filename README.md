robond_project2_go_chase_it


Purpose

This project is my solution to the Udacity Robotics Software Engineer Project 2, "Go Chase it"

The task was to implement a robot in ROS that is able to follow a white ball.
The robot can be viewed in Gazebo and RViz. The ball is normally static, but can be moved by the user, and located in positions that will cause the robot to follow it, and take the appropriate action. The direction control is basic, with basic steering control that does have proportional steering. The actions that can be taken are, move forward, turn left whilst moving forward, turn right whilst moving forward, and stop.

Although the robot has both camera and LIDAR, only the camera is used. A basic ball detection and location implementation is used which does not attempt to measure the distance to the ball. The detection uses a simple RGB method, and relies upon the ball being the only white object in the scene.

How to run

This project was developed on a local virtual machine rather than the Udacity online workspace.

The original virtual machine is available at:

To execute:


run:



In a new terminal run:

Once Gazebo has loaded, position the ball into suitable locations by selecting the ball and using the translation tool to move it.
The Robot should (hopefully) follow the ball.
If the ball is positioned where the robot cannot see it, the robot will stop.




Useful info
sample xacro

<link name="link_1">
    <inertial>
      <origin xyz="0 0 0.4" rpy="0 0 0"/>
      <mass value="${mass1}"/>
      <inertia ixx="30" ixy="0" ixz="0" iyy="50" iyz="0" izz="50"/>
    </inertial>
    <visual>
      <origin xyz="0 0 0" rpy="0 0 0"/>
      <geometry>
        <mesh filename="package://kuka_arm/meshes/kr210l150/visual/link_1.dae"/>
      </geometry>
      <material name="">
        <color rgba="0.75294 0.75294 0.75294 1"/>
      </material>
    </visual>
    <collision>
      <origin xyz="0 0 0" rpy="0 0 0"/>
      <geometry>
        <mesh filename="package://kuka_arm/meshes/kr210l150/collision/link_1.stl"/>
      </geometry>
    </collision>
  </link>


  link name - "camera"
  link origin - "[0, 0, 0, 0, 0, 0]"
  geometry - box with size "[0.05, 0.05, 0.05]"

  mass - "0.1"
  box_inertia - m="0.1" x="0.05" y="0.05" z="0.05"
  inertia - ixx="1e-6" ixy="0" ixz="0" iyy="1e-6" iyz="0" izz="1e-6"

  joint name - "camera_joint"

  joint type - "fixed"
  joint axis - "[0, 1, 0]"
  joint origin - "[0.2, 0, 0, 0, 0, 0]"
  joint parent link - "chassis"
  joint child link - "camera"



  <link name='camera'>
    <inertial>
      <mass value="0.1"/>
      <origin xyz="0.05 0.05 0.05" rpy="0 0 0"/>
      <inertia
         ixx="1e-6" ixy="0" ixz="0" iyy="1e-6" iyz="0" izz="1e-6"
      />
    </inertial>

    <collision name='camera_collision'>
      <origin xyz="0 0 0" rpy="0 0 0"/>
      <geometry>
          <box size="0.05 0.05 0.05"/>
      </geometry>
    </collision>

    <visual name='camera_visual'>
      <origin xyz="0 0 0" rpy="0 0 0"/>
      <geometry>
          <box size="0.05 0.05 0.05"/>
      </geometry>
    </visual>
  </link>
