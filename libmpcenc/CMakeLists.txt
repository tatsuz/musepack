include_directories(${libmpc_SOURCE_DIR}/include)
add_library(mpcenc_static STATIC analy_filter.c bitstream.c encode_sv7.c huffsv7.c quant.c ${libmpc_SOURCE_DIR}/common/crc32.c)
