SET(SHARED $ENV{HOME}/learn_cpp/cmake/06/shared)

# 解决找不到头文件的问题
INCLUDE_DIRECTORIES(${SHARED})
# 提供链接库的位置
LINK_DIRECTORIES(${SHARED})


ADD_EXECUTABLE(main main.cpp)

# 具体链接库信息
TARGET_LINK_LIBRARIES(main libhello.so)