set(DRIVER_NAME multisense-lcm-driver)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -std=c++0x -Wno-deprecated-declarations -Wreturn-type -Wuninitialized -Wunused-variable")

include_directories(${LibMultiSense_INCLUDE_DIRS})

add_executable(${DRIVER_NAME}
  Sensor.cpp
  Imu.cpp
  Laser.cpp
  Camera.cpp
  Driver.cpp
  Main.cpp
)

# I don't know if this is needed:
#add_dependencies(${DRIVER_NAME} ${catkin_EXPORTED_TARGETS})

target_link_libraries(${DRIVER_NAME} ${catkin_LIBRARIES} ${ZLIB_LIBRARIES} ${multisense_lib_LIBRARIES})

#pods_use_pkg_config_packages(${DRIVER_NAME}
#  lcm opencv
#)
#
#pods_install_executables(${DRIVER_NAME})
