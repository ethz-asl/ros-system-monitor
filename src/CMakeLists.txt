remake_ros_package(
  system_monitor
  RUN_DEPENDS rospy std_msgs diagnostic_msgs
  EXTRA_RUN_DEPENDS sysstat hddtemp ntpdate ifstat
)
