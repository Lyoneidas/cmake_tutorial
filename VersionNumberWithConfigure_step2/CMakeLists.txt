cmake_minimum_required(VERSION 3.10)
project(Tutorial_step2 VERSION 1.0)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)
configure_file(TutorialConfig.h.in TutorialConfig.h)
add_executable(Tutorial_step2 main.cc)
target_include_directories(Tutorial_step2 PUBLIC "${PROJECT_BINARY_DIR}")
