cmake_minimum_required(VERSION 3.27.0-rc4)

project(Demo)

include_directories(${PROJECT_SOURCE_DIR}/include) #包含头文件

file(GLOB SRC_LIST ${CMAKE_CURRENT_SOURCE_DIR}/src/test.c)
#搜索文件 搜索当前目录的src目录下所有的源文件，并存储到变量中 

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)

# 包含静态库路径
link_directories(${PROJECT_SOURCE_DIR}/lib)
# 链接静态库
link_libraries(calc)

add_executable(app  ${SRC_LIST})
