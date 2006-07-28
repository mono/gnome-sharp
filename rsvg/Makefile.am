if ENABLE_RSVG
pkg = rsvg
pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = rsvg-sharp-2.0.pc
else
pkg = 
endif

INCLUDE_API = ../art/art-api.xml
METADATA = Rsvg.metadata
SYMBOLS =
references = ../art/art-sharp.dll

sources =			\
	Tool.cs

customs = 			\
	Handle.custom		\
	Pixbuf.custom		\
	State.custom

add_dist = rsvg-sharp-2.0.pc.in

include ../Makefile.include

