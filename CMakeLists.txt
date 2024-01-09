cmake_minimum_required(VERSION 3.12)

# Define our project with the name "TowerDefence"
project(FarmDefence)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)



# Find SFML
find_package(SFML 2.5 COMPONENTS network system window graphics audio REQUIRED)

# Add the include directories for SFML to our project
include_directories(${SFML_INCLUDE_DIRS})

# Tell cmake what the main executable file for the project is, i.e. what has the main() function
add_executable(FarmDefence src/FarmDefence.cpp
                src/Cell.cpp
                src/Game.cpp
                src/Graphics.cpp
                src/Enemy.cpp
                src/Tower.cpp
                src/Grid.cpp
                src/BombTower.cpp
                src/YLaserTower.cpp
                src/XLaserTower.cpp
                src/ArrowTower.cpp
                src/Button.cpp
                src/Projectile.cpp
                src/Obstacle.cpp
)

# Link the SFML library into our executable
target_link_libraries(FarmDefence sfml-network sfml-system sfml-window sfml-graphics sfml-audio)

# enable debugging
set(CMAKE_BUILD_TYPE Debug)

install(TARGETS FarmDefence DESTINATION bin)
