# 使用CMake Tools插件（可选，如果这个项目去到一个没有这个插件的机器也同样可以生成项目）
include(CMakeToolsHelpers OPTIONAL)

# CMake 最低版本号要求
cmake_minimum_required(VERSION 2.8)

# 项目名称
project(TEST)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

# 查找当前目录下的所有源文件,并将名称保存到 DIR_ROOT_SRCS变量 a
aux_source_directory(. DIR_ROOT_SRCS)

# 添加 Lib子目录
add_subdirectory(datalib)

# 指定生成目标 TEST
add_executable(TEST ${DIR_ROOT_SRCS})

# 添加链接库
target_link_libraries(TEST datalib)