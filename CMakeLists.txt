#若版本不够提醒用户升级到新的版本
cmake_minimum_required(VERSION 3.0.2)
#设置项目名称，非必要但是都应加上
project(maincpp)
# set(CMAKE_CXX_FLAGS_DEBUG "{CMAKE_CXX_FLAGS} -o0 -ggbd")    #添加语句
# add_compile_options(-g)                                     #添加语句
# SET(CMAKE_BUILD_TYPE “DEBUG”)                               #添加语句

#c++ 11标准
add_compile_options(-std=c++11)
SET(CMAKE_EXE_LINKER_FLAGS " -no-pie")
#添加宏定义，可以控制程序的输出程序中使用（#define #endif）
# add_definitions(-D PLATFORM_MDC)

# #include文件的路径
# include_directories(
#     ${EIGEN3_INCLUDE_DIR}
#     ${CMAKE_CURRENT_SOURCE_DIR}
#     ${CMAKE_CURRENT_BINARY_DIR}
#     ${CMAKE_CURRENT_SOURCE_DIR}/include
#     ${CMAKE_CURRENT_SOURCE_DIR}/include/common
#     ${CMAKE_CURRENT_SOURCE_DIR}/include/misc

  
# )
#自定义的库在该处放入路径，如果是在usr/lib中存在的库则直接在target_link_libraries中加入库名称就可
# link_directories(
    
#     ${CMAKE_CURRENT_SOURCE_DIR}/lib
# )
#find_package(Eigen3 REQUIRED)


# set (var false)

# if (var)
# add_executable(demo src/main.cpp) # 生成可执行文件
# #生成库文件，也可以不生成。
# #add_library(commath STATIC src/commath.cpp) # 生成静态库.a文件
# #add_library(common SHARED src/commath.cpp) # 生成动态库或共享库.so文件
# #src/下边的所有.cpp文件
# aux_source_directory(src/.  SRC_LIST) # 搜索当前目录下的所有.cpp文件 
# #生成静态库
# add_library(demo1 STATIC ${SRC_LIST}) #默认的.a文件
# #生成动态库
# add_library(demo2 SHARED ${SRC_LIST}) #默认的.a文件
# #将库的名字更改
# SET_TARGET_PROPERTIES (demo2 PROPERTIES OUTPUT_NAME "demo1")
# #GET_TARGET_PROPERTY (OUTPUT_VALUE demo OUTPUT_NAME)

# #MESSAGE (STATUS "This is the demo OUTPUT_NAME: " ${OUTPUT_VALUE})

# #先生成可执行文件再链接库文件
# target_link_libraries(demo
#     #libmain.a
#     libcommath.a
#     libjsoncpp.a
#     #libabsl.a

# )



#直接设置变量的值，追加变量的值
#set(SRC_LIST main.cpp test.cpp)
#add_executable(demo ${SRC_LIST})
#打印信息


# message("build true!")

# else()

# aux_source_directory(src/common/.  SRC_LIST_COM) # 搜索当前目录下的所有.cpp文件
# aux_source_directory(src/misc/.  SRC_LIST_MIS) # 搜索当前目录下的所有.cpp文件
aux_source_directory(src/.  SRC_LIST) # 搜索当前目录下的所有.cpp文件
add_executable(maincpp ${SRC_LIST} ) # 生成可执行文件
#target_link_libraries 要在 add_executable之后
# target_link_libraries(vehicle_model

#     #  libjsoncpp.a
# #    libax_controller.so
# #     #libabsl.a
# )


# message("build false!")

# endif()

#注意顺序 路径->可执行文件->链接库
