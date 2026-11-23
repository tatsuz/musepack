include_directories(${libmpc_SOURCE_DIR}/include)
include_directories(${libmpc_SOURCE_DIR}/libcuefile/include)

link_directories(${libmpc_BINARY_DIR}/libmpcdec)
link_directories(${libmpc_BINARY_DIR}/libmpcenc)
link_directories(${libmpc_BINARY_DIR}/libcuefile ${libmpc_BINARY_DIR}/libcuefile/src)

add_executable(mpcchap mpcchap.c dictionary.c iniparser.c ${libmpc_SOURCE_DIR}/common/tags.c)

if(SHARED)
  target_link_libraries(mpcchap mpcdec_shared)
else(SHARED)
  target_link_libraries(mpcchap mpcdec_static)
endif(SHARED)

target_link_libraries(mpcchap mpcenc_static)
target_link_libraries(mpcchap cuefile)

if(NOT MSVC)
target_link_libraries(mpcchap m)
endif(NOT MSVC)

install(TARGETS mpcchap RUNTIME DESTINATION bin)
