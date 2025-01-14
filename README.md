# gz_ros2_control

ROS2 Distro | Build Status | Package build |
:---------: | :----: | :----------: |
[![Licence](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) |  [![Build Status](https://build.ros2.org/buildStatus/icon?job=Idev__gz_ros2_control__ubuntu_jammy_amd64)](https://build.ros2.org/job/Idev__gz_ros2_control__ubuntu_jammy_amd64/) |  [![Build Status](https://build.ros2.org/buildStatus/icon?job=Ibin_uJ64__gz_ros2_control__ubuntu_jammy_amd64__binary)](https://build.ros2.org/job/Ibin_uJ64__gz_ros2_control__ubuntu_jammy_amd64__binary/) |

This is a ROS 2 package for integrating the `ros2_control` controller architecture with the [Gazebo](http://gazebosim.org/) simulator.
More information about `ros2_control` can be found here: https://control.ros.org/

This package provides a Gazebo-Sim system plugin which instantiates a `ros2_control` controller manager and connects it to a Gazebo model.

ROS version | Gazebo version | Branch | Binaries hosted at | APT key
-- | -- | -- | -- | --
Humble | Fortress | [humble](https://github.com/ros-controls/gz_ros2_control/tree/humble) | https://packages.ros.org | `ros-humble-ign-ros2-control`
Iron | Edifice | [iron](https://github.com/ros-controls/gz_ros2_control/tree/iron) | only from source |
Iron | Fortress | [iron](https://github.com/ros-controls/gz_ros2_control/tree/iron) | https://packages.ros.org | `ros-iron-gz-ros2-control`
Iron | Garden | [iron](https://github.com/ros-controls/gz_ros2_control/tree/iron) | only from source |
Iron | Harmonic | [iron](https://github.com/ros-controls/gz_ros2_control/tree/iron) | only from source |
Jazzy | Harmonic | [master](https://github.com/ros-controls/gz_ros2_control/tree/master) | https://packages.ros.org | `ros-jazzy-gz-ros2-control`
Rolling | Harmonic | [master](https://github.com/ros-controls/gz_ros2_control/tree/master) | https://packages.ros.org | `ros-rolling-gz-ros2-control`

## Build status

ROS 2 Distro | Branch | Build status | Documentation
:----------: | :----: | :----------: | :-----------:
**Rolling** | [`master`](https://github.com/ros-controls/gz_ros2_control/tree/master) | [![gazebo_ros2_control CI - Rolling](https://github.com/ros-controls/gz_ros2_control/actions/workflows/ci-rolling.yaml/badge.svg?branch=master)](https://github.com/ros-controls/gz_ros2_control/actions/workflows/ci-rolling.yaml) | [Documentation](https://control.ros.org/master/index.html) <br /> [API Reference](https://control.ros.org/master/doc/api/index.html)
**Iron** | [`iron`](https://github.com/ros-controls/gz_ros2_control/tree/iron) | [![gazebo_ros2_control CI - Iron](https://github.com/ros-controls/gz_ros2_control/actions/workflows/ci-iron.yaml/badge.svg?branch=master)](https://github.com/ros-controls/gz_ros2_control/actions/workflows/ci-iron.yaml) | [Documentation](https://control.ros.org/iron/index.html) <br /> [API Reference](https://control.ros.org/iron/doc/api/index.html)
**Humble** | [`humble`](https://github.com/ros-controls/gz_ros2_control/tree/humble) | [![ign_ros2_control CI - Humble](https://github.com/ros-controls/gz_ros2_control/actions/workflows/ci-humble.yaml/badge.svg?branch=humble)](https://github.com/ros-controls/gz_ros2_control/actions/workflows/ci-humble.yaml) | [Documentation](https://control.ros.org/humble/index.html) <br /> [API Reference](https://control.ros.org/humble/doc/api/index.html)
## Documentation
See the [documentation file](doc/index.rst) or [control.ros.org](https://control.ros.org/master/doc/gz_ros2_control/doc/index.html)

# Compile from source

If you want compile this from source, you should choose the Gazebo version. The default one is `garden`:

```bash
export GZ_VERSION=fortress
export GZ_VERSION=garden
export GZ_VERSION=harmonic
```

Then create a workspace, clone the correct branch of this repo and compile it:

```bash
mkdir -p ~/gz_ros2_control_ws/src
cd ~/gz_ros2_control_ws/src
git clone https://github.com/ros-controls/gz_ros2_control -b iron
rosdep install -r --from-paths . --ignore-src --rosdistro $ROS_DISTRO -y
cd ~/gz_ros2_control_ws
colcon build
```
