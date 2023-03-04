# tinyspline_vendor

CMake wrapper for the [tinyspline](https://github.com/msteinbeck/tinyspline) library.

## Usage

```CMake
find_package(tinyspline_vendor REQUIRED)

# tinyspline c library
find_package(tinyspline REQUIRED)
target_link_libraries(${PROJECT_NAME}
  tinyspline::tinyspline
)

# tinyspline c++ library
find_package(tinysplinecxx REQUIRED)
target_link_libraries(${PROJECT_NAME}
  tinysplinecxx::tinysplinecxx
)
```