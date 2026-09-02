# Elite Robots Gazebo Simulation

ROS 2 launch files and controller configuration for simulating Elite Robots
manipulators in Gazebo.

## Dependencies

This package uses:

- `elite_robots_description`
- `elite_robots_moveit_config` when launching MoveIt
- `ros_gz_sim` and `ign_ros2_control`
- `ros2_control`, RViz, and Xacro

Install dependencies from the root of your ROS 2 workspace:

```bash
rosdep install --from-paths src --ignore-src -r -y
```

## Build

```bash
colcon build --packages-select elite_robots_simulation_gz
source install/setup.bash
```

## Run the simulation

Start Gazebo and the ROS 2 controllers:

```bash
ros2 launch elite_robots_simulation_gz elite_sim_control.launch.py cs_type:=cs66
```

Start Gazebo together with MoveIt:

```bash
ros2 launch elite_robots_simulation_gz elite_sim_moveit.launch.py cs_type:=cs66
```

Supported `cs_type` values are `cs63`, `cs66`, `cs612`, `cs616`, `cs618f`,
`cs620`, `cs625`, `cs66a`, `cs68`, `cs520h`, and `ls65`.

Useful launch arguments include:

- `launch_rviz`: launch RViz with the control-only simulation
- `start_joint_controller`: start the initial controller in the active state
- `initial_joint_controller`: select the controller to load
- `controllers_file`: override the controller configuration
- `prefix`: add a prefix to joint names for multi-robot setups

Use `ros2 launch ... --show-args` to list every available argument.

## Send an example trajectory

After starting the control simulation:

```bash
ros2 run elite_robots_simulation_gz gz_control.py --example
```

To load waypoints from a YAML file:

```bash
ros2 run elite_robots_simulation_gz gz_control.py --from-yaml /path/to/waypoints.yaml
```

Each waypoint must contain six joint positions and may specify its duration:

```yaml
- positions: [0.0, -1.57, 0.0, -1.57, 0.0, 0.0]
  duration: 2.0
```

## License

Apache License 2.0. See [LICENSE](LICENSE).
