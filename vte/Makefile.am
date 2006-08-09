SUBDIRS = . glue

if ENABLE_VTE
pkg = vte
pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = vte-sharp-2.0.pc
else
pkg = 
endif

INCLUDE_API = 
METADATA = Vte.metadata
SYMBOLS =
references = 
glue_includes = vte/vte.h

sources = 

customs =			\
	Bg.custom

add_dist = vte-sharp-2.0.pc.in

include ../Makefile.include

