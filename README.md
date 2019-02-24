# MOBRO_ROS
Robot navigation using offline SLAM with Cartographer and move_base

# Map building

## Manual navigation to create a bag file

The virtual environment is the Turtlebot3 House with Burger model. Running `gazebo.launch` will bring up the simulator, a bag file should be created with:

 `rosbag record /clock /joint_states /odom /scan /tf /tf_static`
 
Teleop or RQT steering plugin can be used to navigate the robot in the environment.
 
The resulting bag file should be linked to `bag/house.bag`. All programs should then be quit.

## Offline SLAM with Cartographer

Two launch files allow generating a map: `offline_slam` and `offline_fast_slam` that tries to do it faster than real-time.
Once the map has been built, it should be saved with `rosrun map_server map_saver -f house.map`

# Robot navigation

The robot navigation requires gazebo to be run again with gazebo.launch.

Calling `navigation.launch` will bring up the classical RViz GUI where 2D Pose Goal can be set by hand. It can use Cartographer or AMCL (`use_cartographer:={true,false}`). Navigation is done with move_base.
