cmake_minimum_required(VERSION 3.2.0)

# 设置项目名称
project(WebServer)

# 设置 C++ 标准
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# 包含头文件目录
include_directories(${PROJECT_SOURCE_DIR})

# 查找所有源文件
file(GLOB SOURCES
    "${PROJECT_SOURCE_DIR}/*.cpp"
    "${PROJECT_SOURCE_DIR}/Logger/*.cpp"
)

# 生成可执行文件
add_executable(webserver ${SOURCES})

# 链接库 (如果需要的话，例如 pthread)
target_link_libraries(webserver pthread)