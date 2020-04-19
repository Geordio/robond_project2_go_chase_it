# Udacity Robitics Software Engineer - Project 2 - Go Chase it


## Purpose

This project is my solution to the Udacity Robotics Software Engineer Project 2, "Go Chase it"

The task was to implement a robot in ROS that is able to follow a white ball.
The robot can be viewed in Gazebo and RViz. The ball is normally static, but can be moved by the user, and located in positions that will cause the robot to follow it, and take the appropriate action. The direction control is basic, with basic steering control that does have proportional steering. The actions that can be taken are, move forward, turn left whilst moving forward, turn right whilst moving forward, and stop.

Although the robot has both camera and LIDAR, only the camera is used. A basic ball detection and location implementation is used which does not attempt to measure the distance to the ball. The detection uses a simple RGB method, and relies upon the ball being the only white object in the scene.

### Background

This project was developed on a local virtual machine rather than the Udacity online workspace.
The original virtual machine is available from the course website.

### To run
To execute:

Launch gazebo, Rviz and the model
In a terminal from the projects catkin_ws directory, run:

>source devel/setup.bash\
roslaunch my_robot world.launch


Run the image processing  and robot driver controller software
In a new terminal, from the projects catkin_ws directory, run:

>source devel/setup.bash\
roslaunch ball_chaser ball_chaser.launch



Once Gazebo has loaded, position the ball into suitable locations by selecting the ball and using the translation tool to move it.
The Robot should (hopefully) follow the ball.
If the ball is positioned where the robot cannot see it, the robot will stop.

## Robot
Note that the robot appears as all white in gazebo, but is coloured correctly in Rviz

The robot was changed from the one in the lessons. I experimented with many designs,with the wheels at the front and rear but had issues with manoeuvrability, so reverted to centrally positioned wheels. The wheel size, castor size and locations, camera and lidar positions were all changed. The chassis was modelled to resemble a rudimentary tank with the camera positioned on the end of the "barrel".

The robot has a tendancy to oscilate when following a ball that has been moved off centre. This is due to the fairly basic controller thats implemented. It could be improved by estimating the distance to the ball, and the error from the robots current trajectory and implementing a PID. This exceeds the project rubric so I did not implement this.
