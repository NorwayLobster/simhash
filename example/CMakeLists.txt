cmake_minimum_required(VERSION 3.6)
project(simhash_example_bin)
add_executable(${PROJECT_NAME} demo.cc)
target_link_libraries(${PROJECT_NAME}
  PUBLIC
    sub::simhash # need to link its include dir?
)

# target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_SOURCE_DIR}/include)