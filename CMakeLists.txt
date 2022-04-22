cmake_minimum_required(VERSION 2.8.3)
project(system_monitor)

find_package(catkin REQUIRED)

catkin_package()

catkin_install_python(PROGRAMS
  	scripts/cpu_monitor.py
	scripts/hdd_monitor.py
	scripts/mem_monitor.py
	scripts/net_monitor.py
	scripts/ntp_monitor.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY
    config
    launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
