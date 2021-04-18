cmake_minimum_required(VERSION 3.10)
project(Tutorial_step3 VERSION 1.0)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

message("USE_MYMATH equals ${USE_MYMATH}")
# add the MathFunctions library
if(USE_MYMATH)
  add_subdirectory(libs)
  list(APPEND EXTRA_LIBS MathFunctions)
  list(APPEND EXTRA_INCLUDES "${PROJECT_SOURCE_DIR}/libs")
endif()

configure_file(TutorialConfig.h.in TutorialConfig.h)

add_executable(Tutorial_step3 main.cc)

target_link_libraries(Tutorial_step3 PUBLIC "${EXTRA_LIBS}")

target_include_directories(Tutorial_step3 PUBLIC
                           "${PROJECT_BINARY_DIR}"
                           ${EXTRA_INCLUDES}
                           )

