cmake_minimum_required(VERSION 3.13)
set(CMAKE_VERBOSE_MAKEFILE on)

set(rnoh_orientation_locker_generated_dir "${CMAKE_CURRENT_SOURCE_DIR}/generated")
file(GLOB_RECURSE rnoh_orientation_locker_generated_SRC "${rnoh_orientation_locker_generated_dir}/**/*.cpp")
file(GLOB rnoh_orientation_locker_SRC CONFIGURE_DEPENDS *.cpp)
add_library(rnoh_orientation_locker SHARED ${rnoh_orientation_locker_SRC} ${rnoh_orientation_locker_generated_SRC})
target_include_directories(rnoh_orientation_locker PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} ${rnoh_orientation_locker_generated_dir})
target_link_libraries(rnoh_orientation_locker PUBLIC rnoh)