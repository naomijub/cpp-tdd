project(retweets)
cmake_minimum_required(VERSION 2.8.12)

enable_testing()
find_package(GTest CONFIG REQUIRED)
find_package(Threads REQUIRED)

add_definitions(-std=c++11)
set(CMAKE_CXX_FLAGS "${CMAXE_CXX_FLAGS} -Wall")

set(sources
    Tweet.h
    RetweetCollection.h)
set(testSources
    TweetsTest.cpp
    RetweetsTest.cpp)
add_executable(test ${testSources} ${sources})
target_link_libraries(test  PRIVATE Threads::Threads GTest::gmock GTest::gtest GTest::gmock_main GTest::gtest_main)
add_test(test-1 test)
