cmake_minimum_required(VERSION 2.8.11)
project(flightcontroller)

# Modules
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/")

# Packages
find_package(WiringPi REQUIRED)
find_package(Threads REQUIRED)

# Includes
include_directories(
    include
)

# Dependences
add_executable(flightcontroller
    src/main.c
    src/mpu6050_interface.c
)

# Libraries
target_link_libraries(flightcontroller ${WIRINGPI_LIBRARIES}) 
target_link_libraries(flightcontroller ${CMAKE_THREAD_LIBS_INIT}) 
