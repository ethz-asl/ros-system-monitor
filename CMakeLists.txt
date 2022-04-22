cmake_minimum_required(VERSION 2.8.3)
project(system_monitor)

find_package(catkin REQUIRED)

catkin_package()

catkin_install_python(PROGRAMS
  	bin/cpu_monitor.py
	bin/hdd_monitor.py
	bin/mem_monitor.py
	bin/net_monitor.py
	bin/ntp_monitor.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY
    config
    launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
