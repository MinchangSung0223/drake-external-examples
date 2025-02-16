# out of memory 문제
```bash
cd $HOME
gedit .bazelrc
  ##
   build --jobs=HOST_CPUS*0.4
  ##
```


# Catkin Project with an Installed Drake

This example uses the [`catkin`](https://wiki.ros.org/catkin) build system, as
used by the Robot Operating System (ROS), with an installed instance of the
Drake [binary packages](https://drake.mit.edu/from_binary.html).

## Instructions

If you wish use `catkin` from the Ubuntu package archive, without ROS Melodic,
install the required packages as follows:
```
sudo ../scripts/setup/linux/ubuntu/bionic/install_prereqs
```

If you wish use `catkin` from ROS Melodic package archive, install the required
packages and configure your environment as follows:
```
sudo ../scripts/setup/linux/ubuntu/bionic/install_prereqs --ros-melodic
source /opt/ros/melodic/setup.bash
```

To build the `drake_catkin_installed` library:
```
catkin_make --cmake-args "-DCMAKE_PREFIX_PATH=/path/to/drake;$CMAKE_PREFIX_PATH"
```

To build and run the `drake_catkin_installed_test` test executable:
```
catkin_make run_tests --cmake-args "-DCMAKE_PREFIX_PATH=/path/to/drake;$CMAKE_PREFIX_PATH"
```

*If the Drake binary package is installed to `/opt/drake`, you may omit the
`--cmake-args <args>` argument.*
