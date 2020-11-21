CMAKE_MINIMUM_REQUIRED(VERSION 3.6)
PROJECT(simhash)

add_subdirectory(example)

ADD_DEFINITIONS(-O3 -Wall -g)
add_library(${PROJECT_NAME} INTERFACE)
add_library(sub::simhash ALIAS ${PROJECT_NAME})

target_include_directories(${PROJECT_NAME} 
  INTERFACE 
    ${PROJECT_SOURCE_DIR}/include
)
target_link_libraries(${PROJECT_NAME} 
  INTERFACE 
    sub::cppjieba
)

# INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/deps ${PROJECT_SOURCE_DIR}/include)

# IF(APPLE) 
#     ADD_DEFINITIONS(-std=c++11)
# endif()

# ADD_SUBDIRECTORY(example)
# ADD_SUBDIRECTORY(test)

# ENABLE_TESTING()
# ADD_TEST(NAME ./test/test.run COMMAND ./test/test.run)
# ADD_TEST(NAME ./test/load_test COMMAND ./test/load_test)
# ADD_TEST(NAME ./demo COMMAND ./demo)
