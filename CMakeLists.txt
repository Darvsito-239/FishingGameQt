cmake_minimum_required(VERSION 3.31)
project(COP_II_Project LANGUAGES CXX)

# C++20
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Enable automatic MOC, UIC, and RCC handling
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTORCC ON)

# Find Qt6 components
find_package(Qt6 REQUIRED COMPONENTS Core Gui Widgets)

# Add executable
add_executable(COP_II_Project
        main.cpp
        # <-- Include the Qt resource file
)

# Add Qt resources
qt_add_resources(RESOURCES resources.qrc)

# Include resources in the executable
target_sources(COP_II_Project PRIVATE ${RESOURCES})

# Link Qt libraries
target_link_libraries(COP_II_Project
        Qt6::Core
        Qt6::Gui
        Qt6::Widgets
)


