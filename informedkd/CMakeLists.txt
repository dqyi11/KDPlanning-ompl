FILE(GLOB_RECURSE LibFiles "include/*.h")
add_custom_target(headers SOURCES ${LibFiles})

find_package(DART REQUIRED)
include_directories(${DART_INCLUDE_DIRS})

find_package(aikido REQUIRED COMPONENTS
  constraint
  control
  control_ros
  distance
  perception
  control
  control_ros
  planner_ompl
  planner_parabolic
  rviz
  statespace
  util)
include_directories(${aikido_INCLUDE_DIRS})

find_package(libherb REQUIRED)
include_directories(${libherb_INCLUDE_DIRS})
if(libherb_FOUND)
  message(" FOUND LIBHERB: " ${libherb_INCLUDE_DIRS})
endif()

find_package(pr_ordata REQUIRED)
include_directories(${pr_ordata_INCLUDE_DIRS})

find_package(pr_tsr REQUIRED)
include_directories(${pr_tsr_INCLUDE_DIRS})


include_directories("${CMAKE_CURRENT_SOURCE_DIR}/informedkd/include")
add_subdirectory("src")
add_subdirectory("test")
