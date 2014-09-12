remake_ros_package(
  starleth_system_monitor
  RUN_DEPENDS rospy std_msgs diagnostic_msgs
  DESCRIPTION "System monitor for StarlETH."
  EXTRA_RUN_DEPENDS sysstat hddtemp ntpdate ifstat
)
remake_ros_package_config_generate(PACKAGE starleth_system_monitor)
