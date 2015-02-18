cmake_minimum_required(VERSION 2.6)

include(ReMake)

remake_project(
  ros-${ROS_DISTRIBUTION}-system-monitor
  VERSION 0.1
  RELEASE beta
  SUMMARY "System monitoring tools for ROS."
  AUTHOR "Ralf Kaestner"
  AUTHOR "Jerome Maye"
  CONTACT "ralf.kaestner@gmail.com"
  HOME "http://github.com/ethz-asl/ros-system-monitor"
  LICENSE "BSD License (BSD)"
  PREFIX system-monitor-
  INSTALL /usr
  README README.md
)

remake_ros_pack_deb(DEFAULT system_monitor)

remake_ros_distribute_deb(
  DISTRIBUTION lucid
  SECTION libs
  DEPENDS remake pkg-config sysstat hddtemp ntpdate ifstat
  UPLOAD ppa:jmaye/starleth
  PASS CMAKE_BUILD_TYPE ROS_${ROS_DISTRIBUTION}_SYSTEM_MONITOR_GIT_REVISION
  FORCE_CONSISTENCY
  IF ${ROS_DISTRIBUTION} STREQUAL fuerte
)
remake_ros_distribute_deb(
  DISTRIBUTION precise
  SECTION libs
  DEPENDS remake pkg-config sysstat hddtemp ntpdate ifstat
  UPLOAD ppa:jmaye/starleth
  PASS CMAKE_BUILD_TYPE ROS_${ROS_DISTRIBUTION}_SYSTEM_MONITOR_GIT_REVISION
  FORCE_CONSISTENCY
  IF ${ROS_DISTRIBUTION} STREQUAL fuerte OR ${ROS_DISTRIBUTION}
    STREQUAL groovy
)
remake_ros_distribute_deb(
  DISTRIBUTION trusty
  SECTION libs
  DEPENDS remake pkg-config sysstat hddtemp ntpdate ifstat
  UPLOAD ppa:jmaye/starleth
  PASS CMAKE_BUILD_TYPE ROS_${ROS_DISTRIBUTION}_SYSTEM_MONITOR_GIT_REVISION
  FORCE_CONSISTENCY
  IF ${ROS_DISTRIBUTION} STREQUAL indigo
)
