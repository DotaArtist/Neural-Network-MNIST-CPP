cmake_minimum_required(VERSION 3.10)
project(Neural_Network_MNIST_CPP)

set(CMAKE_CXX_STANDARD 14)

# 多个main函数编译会报错
#add_executable(Neural_Network_MNIST_CPP training_nn.cpp)
#add_executable(Neural_Network_MNIST_CPP testing_nn.cpp)

# 遍历项目根目录下所有的 .cpp 文件
file (GLOB_RECURSE files *.cpp)
foreach (file ${files})
    string(REGEX REPLACE ".+/(.+)\\..*" "\\1" exe ${file})
    add_executable (${exe} ${file})
    message (\ \ \ \ --\ src/${exe}.cpp\ will\ be\ compiled\ to\ bin/${exe})
endforeach ()