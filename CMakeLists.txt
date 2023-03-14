cmake_minimum_required(VERSION 3.12)
project(tinyspline_vendor)

find_package(ament_cmake REQUIRED)

include(FetchContent)
fetchcontent_declare(
  tinyspline
  GIT_REPOSITORY https://github.com/msteinbeck/tinyspline.git
  GIT_TAG        5f0e8fad34e86771cfae3dac4beef5f1858d5610 # v0.6.0
)
set(BUILD_SHARED_LIBS ON)
fetchcontent_makeavailable(tinyspline)

install(
  DIRECTORY
    ${tinyspline_BINARY_DIR}/src/CMakeFiles/Export/lib64/cmake/tinyspline/
  DESTINATION
    share/${PROJECT_NAME}/cmake
)
install(
  DIRECTORY
    ${tinyspline_BINARY_DIR}/src/CMakeFiles/Export/lib64/cmake/tinysplinecxx/
  DESTINATION
    share/${PROJECT_NAME}/cmake
)
install(
  FILES
    ${tinyspline_BINARY_DIR}/tinyspline-config.cmake
    ${tinyspline_BINARY_DIR}/tinyspline-config-version.cmake
    ${tinyspline_BINARY_DIR}/tinysplinecxx-config.cmake
    ${tinyspline_BINARY_DIR}/tinysplinecxx-config-version.cmake
  DESTINATION
    share/${PROJECT_NAME}/cmake
)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package(CONFIG_EXTRAS tinyspline_vendor-extras.cmake)
