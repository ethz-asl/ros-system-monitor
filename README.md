# ros-system-monitor

## Synopsis

System monitoring tools for ROS.

**Author(s):** Willow Garage, Inc., Jerome Maye, Ralf Kaestner

**Maintainer:** Ralf Kaestner <ralf.kaestner@gmail.com>

**License:** BSD License (BSD)

**Operating system(s):** Debian-based Linux

**Package PPA:** ppa:ethz-asl/ros

## Description

This project provides system monitoring tools for ROS in the form of the
following ROS nodes:

* CPU monitor
* HDD monitor
* Memory monitor
* Network monitor
* NTP monitor

Each node publishes ROS diagnostics which can conveniently be visualized
in the runtime monitor.

## Installation

Here, we assume you intend to build/install the project for the ROS
distribution named `ROS_DISTRO`.

### Installing from packages (recommended for Ubuntu LTS users)

The maintainers of this project provide binary packages for the latest Ubuntu
LTS releases and commonly used system architectures. To install these packages,
you may follow these instructions:

* Add the project PPA to your APT sources by issuing 

  ```
  sudo add-apt-repository ppa:ethz-asl/ros
  ```

  on the command line

* To re-synchronize your package index files, run

  ```
  sudo apt-get update
  ```

* Install all project packages and their dependencies through

  ```
  sudo apt-get install ros-ROS_DISTRO-system-monitor
  ```

  or using your favorite package management tool

### Building from source

This project may be built using the CMake build system with an open-source
macro extension called ReMake.

#### Installing build dependencies

The build dependencies of this project are available from the standard
package repositories of recent Ubuntu and ROS releases. To install them,
simply use the command

```
sudo apt-get install ros-ROS_DISTRO-rospy, ros-ROS_DISTRO-message-generation, ros-ROS_DISTRO-std-msgs, ros-ROS_DISTRO-diagnostic-msgs

```
#### Building with ReMake

##### Preparing the build system

If you already have installed ReMake on your build system, you may
skip this step. Otherwise, before attempting to build this project the
traditional CMake way, you must install ReMake following
[these instructions](https://github.com/kralf/remake).

##### Building with CMake

Once ReMake is available on your build system, you may attempt to build this
project the CMake way. Assuming that you have cloned the project sources into
`PROJECT_DIR`, a typical out-of-source build might look like this:

* Create a build directory using 

  ```
  mkdir -p PROJECT_DIR/build
  ```

* Switch into the build directoy by 

  ```
  cd PROJECT_DIR/build
  ```

* In the build directory, run 

  ```
  cmake -DROS_DISTRIBUTION=ROS_DISTRO PROJECT_DIR
  ```

  to configure the build

* If you want to inspect or modify the build configuration, issue 

  ```
  ccmake PROJECT_DIR
  ```

* Build the project using 

  ```
  make
  ```

* If you intend to install the project, call 

  ```
  make packages_install
  ```

  (from packages on Debian-based Linux only) or 

  ```
  make install
  ```

## API documentation

This project does not yet provide any API documentation.

## Feature requests and bug reports

If you would like to propose a feature for this project, please consider
contributing or send a feature request to the project authors. Bugs may be
reported through the project's issue page.

## Further reading

For additional information of the Robot Operating System (ROS), please refer
to the official [ROS documentation](http://wiki.ros.org).
