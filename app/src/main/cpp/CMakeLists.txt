cmake_minimum_required(VERSION 2.8.7)
project(mdl)
#include_directories(include /usr/local/include)

# Add all headers and source files.
file(GLOB_RECURSE MDL_CPP baidu/src/*.cpp baidu/third-party/*.cpp)
file(GLOB_RECURSE MDL_H *.h)


# include headers
include_directories(baidu/include/)
include_directories(baidu/third-party/)

message("MDL_CPP=${MDL_CPP}")
message("MDL_H=${MDL_H}")
# gen so
ADD_LIBRARY(mdl SHARED ${MDL_CPP}  ${MDL_H} )

# gen static
ADD_LIBRARY(mdl-static STATIC ${MDL_CPP} ${MDL_H})





