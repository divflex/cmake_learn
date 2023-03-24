SET(LIBHELLO_SRC hello.cpp)

ADD_LIBRARY(hello_static STATIC ${LIBHELLO_SRC})
set_target_properties(hello_static PROPERTIES OUTPUT_NAME "hello")
set_target_properties(hello_static PROPERTIES CLEAN_DIRECT_OUTPUT 1)

ADD_LIBRARY(hello SHARED ${LIBHELLO_SRC})
set_target_properties(hello PROPERTIES OUTPUT_NAME "hello")
set_target_properties(hello PROPERTIES CLEAN_DIRECT_OUTPUT 1)

SET(DEST $ENV{HOME}/learn_cpp/cmake/06/shared)

INSTALL(FILES hello.h DESTINATION ${DEST})

INSTALL(TARGETS hello hello_static LIBRARY DESTINATION ${DEST} ARCHIVE DESTINATION ${DEST})