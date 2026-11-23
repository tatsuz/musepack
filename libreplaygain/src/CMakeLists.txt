include_directories(${libmpc_SOURCE_DIR}/libreplaygain/include)

if(SHARED)
  add_library(replaygain-shared SHARED gain_analysis.c)
  set_target_properties(replaygain-shared PROPERTIES OUTPUT_NAME replaygain CLEAN_DIRECT_OUTPUT 1 VERSION 1.0.0 SOVERSION 1)
  install(TARGETS replaygain-shared LIBRARY DESTINATION "lib${LIB_SUFFIX}" ARCHIVE DESTINATION "lib${LIB_SUFFIX}")
else(SHARED)
  add_library(replaygain-static STATIC gain_analysis.c)
  set_target_properties(replaygain-static PROPERTIES OUTPUT_NAME replaygain CLEAN_DIRECT_OUTPUT 1)
  install(TARGETS replaygain-static LIBRARY DESTINATION "lib${LIB_SUFFIX}" ARCHIVE DESTINATION "lib${LIB_SUFFIX}")
endif(SHARED)

