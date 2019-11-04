SET(mpcdec_VERSION_MAJOR 7)
SET(mpcdec_VERSION_MINOR 0)
SET(mpcdec_VERSION_PATCH 1)

set(mpcdec_VERSION ${mpcdec_VERSION_MAJOR}.${mpcdec_VERSION_MINOR}.${mpcdec_VERSION_PATCH})

install(FILES
	${libmpc_SOURCE_DIR}/include/mpc/mpcdec.h
	${libmpc_SOURCE_DIR}/include/mpc/reader.h
	${libmpc_SOURCE_DIR}/include/mpc/streaminfo.h
	${libmpc_SOURCE_DIR}/include/mpc/mpc_types.h
	DESTINATION include/mpc COMPONENT headers)

include_directories(${libmpc_SOURCE_DIR}/include)
if(SHARED)
  add_library(mpcdec_shared SHARED huffman mpc_decoder mpc_reader streaminfo mpc_bits_reader mpc_demux requant synth_filter ${libmpc_SOURCE_DIR}/common/crc32)
  set_target_properties(mpcdec_shared PROPERTIES OUTPUT_NAME mpcdec CLEAN_DIRECT_OUTPUT 1 VERSION ${mpcdec_VERSION} SOVERSION ${mpcdec_VERSION_MAJOR})
  install(TARGETS mpcdec_shared LIBRARY DESTINATION "lib${LIB_SUFFIX}" ARCHIVE DESTINATION "lib${LIB_SUFFIX}" COMPONENT libraries)
  target_link_libraries(mpcdec_shared m)
else(SHARED)
  add_library(mpcdec_static STATIC huffman mpc_decoder mpc_reader streaminfo mpc_bits_reader mpc_demux requant synth_filter ${libmpc_SOURCE_DIR}/common/crc32)
  set_target_properties(mpcdec_static PROPERTIES OUTPUT_NAME mpcdec CLEAN_DIRECT_OUTPUT 1)
  install(TARGETS mpcdec_static LIBRARY DESTINATION "lib${LIB_SUFFIX}" ARCHIVE DESTINATION "lib${LIB_SUFFIX}" COMPONENT libraries)
  target_link_libraries(mpcdec_static m)
endif(SHARED)

