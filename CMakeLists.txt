cmake_minimum_required(VERSION 3.10)
project(learnopengl)

# Set C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Find necessary packages (OpenGL and GLFW)
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

# Include directories
include_directories(${OPENGL_INCLUDE_DIRS})

# Source files
set(SOURCES main.cpp glad.c)

# Executable
add_executable(${PROJECT_NAME} ${SOURCES})

# Link OpenGL and GLFW libraries
target_link_libraries(${PROJECT_NAME} PRIVATE ${OPENGL_LIBRARIES} glfw)

# Link GL library
target_link_libraries(${PROJECT_NAME} PRIVATE GL)

# Link Xrandr library
target_link_libraries(${PROJECT_NAME} PRIVATE Xrandr)

# Link pthread library
target_link_libraries(${PROJECT_NAME} PRIVATE pthread)

# Link X11 library
target_link_libraries(${PROJECT_NAME} PRIVATE X11)

# Link dl library
target_link_libraries(${PROJECT_NAME} PRIVATE dl)

# Link Xi library
target_link_libraries(${PROJECT_NAME} PRIVATE Xi)