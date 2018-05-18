warning_flags = -Wall -Wextra -Wshadow -Wno-unused-parameter
common_cflags = -O3 -ffast-math -fvisibility=hidden $(warning_flags) $(MFLAGS)
AM_CXXFLAGS = -std=c++14 $(common_cflags)

AM_CPPFLAGS = $(VapourSynth_CFLAGS)

lib_LTLIBRARIES = libwaifu2x-w2xc.la

libwaifu2x_w2xc_la_SOURCES = Waifu2x-w2xc/Waifu2x-w2xc.cpp

libwaifu2x_w2xc_la_LDFLAGS = -no-undefined -avoid-version -lw2xc $(PLUGINLDFLAGS)
