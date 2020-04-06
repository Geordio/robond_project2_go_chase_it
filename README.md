robond_project2_go_chase_it


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
