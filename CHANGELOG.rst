^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package elite_robots_simulation_gz
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1.0.1 (2026-09-18)
------------------
* Remove the unnecessary CMake lookup for ``rclpy`` to fix configuration failures in ROS build farm builds
* Retain ``rclpy`` as a runtime dependency for the Python control script

1.0.0 (2026-07-29)
------------------
* Split the Gazebo simulation into a standalone ROS 2 package
* Rename the package to ``elite_robots_simulation_gz``
* Update the MoveIt configuration dependency to ``elite_robots_moveit_config``
* Add launch, controller configuration, and Gazebo trajectory-control files
* Add package documentation
* Contributors: Chen Shichao
