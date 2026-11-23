include_directories(${libmpc_SOURCE_DIR}/include)
add_library(mpcpsy_static STATIC ans.c cvd.c fft4g.c fft_routines.c profile.c psy.c psy_tab.c ${libmpc_SOURCE_DIR}/common/fastmath.c)
