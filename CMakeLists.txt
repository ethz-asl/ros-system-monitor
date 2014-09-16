cmake_minimum_required(VERSION 2.6)

include(ReMake)

remake_project(
  starleth-system-monitor-ros-${ROS_DISTRIBUTION}
  VERSION 0.1
  RELEASE alpha
  SUMMARY "A collection of system monitoring tools for the StarlETH robot."
  AUTHOR "Jerome Maye"
  CONTACT "jerome.maye@mavt.ethz.ch"
  HOME "http://github.com/jmaye/starleth-system-monitor-ros"
  LICENSE "GNU Lesser General Public License (LGPL)"
  PREFIX starleth-system-monitor-
  INSTALL /usr
  CONFIGURATION_DESTINATION /etc/starleth-system-monitor
  EXTRA_CXX_FLAGS -std=c++0x
)

remake_var_name(GIT_REVISION_VAR ${REMAKE_PROJECT_NAME} GIT_REVISION)

remake_ros_pack_deb()

if(${ROS_DISTRIBUTION} STREQUAL fuerte)
  remake_ros_distribute_deb(
    DISTRIBUTION lucid
    SECTION libs
    DEPENDS remake pkg-config sysstat hddtemp ntpdate ifstat
    UPLOAD ppa:jmaye/starleth
    PASS CMAKE_BUILD_TYPE ${GIT_REVISION_VAR}
    FORCE_CONSISTENCY
  )
endif()

if(${ROS_DISTRIBUTION} STREQUAL fuerte OR ${ROS_DISTRIBUTION} STREQUAL groovy)
  remake_ros_distribute_deb(
    DISTRIBUTION precise
    SECTION libs
    DEPENDS remake pkg-config sysstat hddtemp ntpdate ifstat
    UPLOAD ppa:jmaye/starleth
    PASS CMAKE_BUILD_TYPE ${GIT_REVISION_VAR}
    FORCE_CONSISTENCY
  )
endif()

if(${ROS_DISTRIBUTION} STREQUAL indigo)
  remake_ros_distribute_deb(
    DISTRIBUTION trusty
    SECTION libs
    DEPENDS remake pkg-config sysstat hddtemp ntpdate ifstat
    UPLOAD ppa:jmaye/starleth
    PASS CMAKE_BUILD_TYPE ${GIT_REVISION_VAR}
    FORCE_CONSISTENCY
  )
endif()
