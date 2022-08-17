# arlo_simulations
This meta package simulates the Parallax Arlo Robot with an Interbotix WX250S arm in Gazebo. The inertial values for simulation were obtained from a solidworks model.  

Please use `Gazebo Version> 9.19.x+`

Download the following packages and place them in your workspace.

|Required Packages    |  Link                                                                                   |
|--------------       | ----------                                                                              |
| aws-house           | [repository](https://github.com/aws-robotics/aws-robomaker-small-house-world)           |
| interbotix_ros_*    | [repository](https://github.com/aws-robotics/aws-robomaker-small-house-world)           |

Install the interbotix packages by running the install script from [here](https://github.com/Interbotix/interbotix_ros_manipulators/tree/main/interbotix_ros_xsarms/install/amd64). Its easiest to put all the packages into one workspace like this:

```
src
├── arlo_simulations
├── aws-robomaker-small-house-world
├── interbotix_ros_core
├── interbotix_ros_manipulators
└── interbotix_ros_toolboxes
```


# Running the Simulation
run simulation of ArloRobot (no external dependencies)
```bash
roslaunch arlo_gazebo arlo_sim.launch paused:=True
```
# Simulating Arlo & WX250S 
Launch the [xsarm_moveit.launch](https://github.com/Interbotix/interbotix_ros_manipulators/blob/main/interbotix_ros_xsarms/interbotix_xsarm_moveit/launch/xsarm_moveit.launch) file like this ([video](https://youtu.be/k3zkgN7TYTE?t=455)) to verify the interbotix packages are correctly installed.

* Start the simulation with the following command:
```bash
roslaunch arlo_gazebo arlo_sim.launch
```
Press tab to see the available options.

![This is an image](/resources/images/Press_tab_to_view_launch_args.png)

There are 19 args are available in the launch file to modify as in command line.

Please visit the [launch folder](/launch/README.md) for more information.

|Argument               | description                           | default                   |
|-----------------------|:-------------------------------------:|--------------------------:|
|x_pos, y_pos, z_pos    | Set robot spawn location              | (-1.33, 0.55, 0.02)       |
|use_rtabmapviz         | Enable rtabmap GUI visualization      | false                     |
|ns                     | Namespace for the entire robot        | wx250s                    |
|arlo_rviz              | Visualize the Arlo Robot in RViz      | true                      |
|isolate                | Minimal startup                       | false                     |
|teleop                 | Launch teleop_keyboard node           | false                     |




## View of the Arlo Robot running in RViz.
![This is an image](/resources/images/rviz_gazebo.png)

## Example of populated rtabmap/MapData in RViz.
![This is an image](/resources/images/MapData_after_mapping.png)

## View of Rtabmap in GUI.
Set the `use_rtabmapviz` argument to `true` in the launch file.

In Rtabmap-GUI, enable mapping to populate the rtabmap/MapData as shown in the image below.

![This is an image](/resources/images/rtabmapviz_enable_mapping.jpg)


