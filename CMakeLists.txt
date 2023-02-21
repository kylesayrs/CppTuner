# cmake settings
cmake_minimum_required(VERSION 3.25.2)

# set up project
project(CppTuner)
set(CMAKE_CXX_STANDARD 20)

# executables
add_executable(MyProgram src/main.cpp)
add_executable(MyProgramTest tests/dumbtest.cpp)


# include and libraries
find_package(GTest REQUIRED)
include_directories(${GTEST_INCLUDE_DIRS}/include)

# link libraries
target_link_libraries(MyProgram PUBLIC GTest::GTest GTest::Main)
target_link_libraries(MyProgramTest PUBLIC GTest::GTest GTest::Main)
