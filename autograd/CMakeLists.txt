cmake_minimum_required(VERSION 2.8)
project(autograd)

include_directories( /usr/local/cuda/include )
include_directories( /usr/local/cuda/lib64 )

#set(CMAKE_PREFIX_PATH ${CMAKE_PREFIX_PATH} "/home/hlx/libtorch")
#set(TORCH_LIBRARIES ${Torch_DIR}/lib/)

#include_directories( ${Torch_DIR} )
#include_directories( ${Torch_DIR}/include )
#include_directories( ${Torch_DIR}/include/torch/csrc/api/include/ )
#include_directories( ${Torch_DIR}/include/torch)

find_package(Torch REQUIRED)

add_executable(autograd "autograd.cpp")

target_link_libraries(autograd "${TORCH_LIBRARIES}")
set_property(TARGET autograd PROPERTY CXX_STANDARD 14)