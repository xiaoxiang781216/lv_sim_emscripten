cmake_minimum_required(VERSION 3.12)
project (lvgl)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O2 -s USE_SDL=2")

include_directories(${PROJECT_SOURCE_DIR})

file(GLOB_RECURSE INCLUDES "./*.h")
file(GLOB_RECURSE SOURCES "./*.c")

add_executable(lvgl ${SOURCES} ${INCLUDES})

set(CMAKE_EXECUTABLE_SUFFIX ".html")
set_target_properties(lvgl PROPERTIES LINK_FLAGS "--shell-file ${PROJECT_SOURCE_DIR}/lvgl_shell.html")
