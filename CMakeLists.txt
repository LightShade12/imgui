#========================================================================
# IMGUI
#========================================================================
cmake_minimum_required(VERSION 3.27)

project(IMGUI VERSION 1.0 LANGUAGES C CXX)

add_library(imgui STATIC)

target_sources(imgui PRIVATE
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_demo.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_draw.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_tables.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_widgets.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_opengl3.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_glfw.cpp"
)

target_link_libraries(imgui PUBLIC compiler_flags)

if(CMAKE_SYSTEM_NAME MATCHES "Windows")
    target_include_directories(imgui PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/../glfw/include")
endif()

target_include_directories(imgui PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}" "${CMAKE_CURRENT_SOURCE_DIR}/backends")

