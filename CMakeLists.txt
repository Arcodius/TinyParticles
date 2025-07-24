# CMakeLists.txt
cmake_minimum_required(VERSION 3.10)
project(VulkanParticleSystem VERSION 1.0)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(GLFW_INCLUDE_DIR "C:/Users/Tiracolate/libraries/GLFW/include")
set(GLFW_LIBRARY "C:/Users/Tiracolate/libraries/GLFW/lib/glfw3.lib")

find_package(Vulkan REQUIRED)

# 添加可执行文件
# add_executable(目标名称 源文件)
add_executable(TinyParticles src/main.cpp)

target_include_directories(TinyParticles PRIVATE
    ${Vulkan_INCLUDE_DIR}
    ${GLFW_INCLUDE_DIR}
    ${PROJECT_SOURCE_DIR}
)

target_link_libraries(TinyParticles PRIVATE
    ${Vulkan_LIBRARY}
    ${GLFW_LIBRARY}
)