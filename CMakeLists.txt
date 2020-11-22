cmake_minimum_required(VERSION 3.15)
project(asio)

set(CMAKE_CXX_STANDARD 17)

include_directories(/home/fenghl/software/boost_1_73_0)
FIND_LIBRARY(BOOST_LIB boost_coroutine boost_context boost_system boost_chrono /home/fenghl/software/boost_1_73_0/stage/lib)
FIND_LIBRARY(GNU_LIB rt /usr/lib/x86_64-linux-gnu)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pthread")
link_libraries(${BOOST_LIB} ${GNU_LIB})



add_executable(asio main.cpp)