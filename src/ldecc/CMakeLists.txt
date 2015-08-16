cmake_minimum_required(VERSION 2.8.11)

project(ldecc)

# Find includes in corresponding build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)
# Instruct CMake to run moc automatically when needed.
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)

# Find the QtWidgets library
find_package(Qt5Widgets)

# Tell CMake to create the helloworld executable
add_executable(ldecc descc.cpp gencc.cpp lancc.cpp ldecc.cpp ldeccrc.qrc main.cpp safcc.cpp)

# Use the Widgets module from Qt 5.
target_link_libraries(ldecc Qt5::Widgets)