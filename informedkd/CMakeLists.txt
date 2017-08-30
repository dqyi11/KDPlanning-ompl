FILE(GLOB_RECURSE LibFiles "include/*.h")
add_custom_target(headers SOURCES ${LibFiles})

include_directories("${CMAKE_CURRENT_SOURCE_DIR}/informedkd/include")
add_subdirectory("src")
add_subdirectory("test")
