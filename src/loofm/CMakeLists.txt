cmake_minimum_required(VERSION 2.8.11)

project(loofm)

# Find includes in corresponding build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)
# Instruct CMake to run moc automatically when needed.
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt5Widgets)
qt5_wrap_ui(UIS_HDRS fileview.ui)
qt5_add_resources(QRCS_CPPS resource.qrc)
# find_package(Qt5LinguistTools)

# qt5_add_translation(filemanager_zh.qm filemanager_zh.ts)

# Tell CMake to create the helloworld executable
add_executable(loofm fileview.cpp main.cpp ${UIS_HDRS} ${QRCS_CPPS})

# Use the Widgets module from Qt 5.
target_link_libraries(loofm Qt5::Widgets)

INSTALL (TARGETS loofm RUNTIME DESTINATION /usr/bin)
