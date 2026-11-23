add_definitions(-DYY_NEVER_INTERACTIVE)
include_directories(${libmpc_SOURCE_DIR}/libcuefile/include)

if(SHARED)
  add_library(cuefile-shared SHARED cd.c cdtext.c cue_parse.c cue_print.c cue_scan.c cuefile.c time.c toc_parse.c toc_print.c toc_scan.c)
  set_target_properties(cuefile-shared PROPERTIES OUTPUT_NAME cuefile CLEAN_DIRECT_OUTPUT 1 VERSION 0.0.0 SOVERSION 0)
  install(TARGETS cuefile-shared LIBRARY DESTINATION "lib${LIB_SUFFIX}" ARCHIVE DESTINATION "lib${LIB_SUFFIX}")
else(SHARED)
  add_library(cuefile-static STATIC cd.c cdtext.c cue_parse.c cue_print.c cue_scan.c cuefile.c time.c toc_parse.c toc_print.c toc_scan.c)
  set_target_properties(cuefile-static PROPERTIES OUTPUT_NAME cuefile CLEAN_DIRECT_OUTPUT 1)
  install(TARGETS cuefile-static LIBRARY DESTINATION "lib${LIB_SUFFIX}" ARCHIVE DESTINATION "lib${LIB_SUFFIX}")
endif(SHARED)

