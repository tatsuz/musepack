include_directories(${libmpc_SOURCE_DIR}/include)
include_directories(${libmpc_SOURCE_DIR}/libreplaygain/include)

link_directories(${libmpc_BINARY_DIR}/libmpcdec_shared)
link_directories(${libmpc_BINARY_DIR}/libreplaygain ${libmpc_BINARY_DIR}/libreplaygain/src)

add_executable(mpcgain mpcgain.c)

target_link_libraries(mpcgain replaygain)

if(SHARED)
  target_link_libraries(mpcgain mpcdec_shared)
else(SHARED)
  target_link_libraries(mpcgain mpcdec_static)
endif(SHARED)

if(NOT MSVC)
target_link_libraries(mpcgain m)
endif(NOT MSVC)

install(TARGETS mpcgain RUNTIME DESTINATION bin)
