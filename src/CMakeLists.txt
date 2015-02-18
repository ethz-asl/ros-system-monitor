remake_ros_package(
  system_monitor
  DEPENDS rospy std_msgs diagnostic_msgs
  EXTRA_RUN_DEPENDS sysstat hddtemp ntpdate ifstat
)
