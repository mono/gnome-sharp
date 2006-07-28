if ENABLE_GTKHTML
pkg = gtkhtml
pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = gtkhtml-sharp-2.0.pc
else
pkg = 
endif
INCLUDE_API = ../art/art-api.xml ../gnome/gnome-api.xml
METADATA = Gtk.metadata
SYMBOLS =
references = ../art/art-sharp.dll ../gnome/gnome-sharp.dll

sources =

customs =			\
	HTML.custom		\
	HTMLStream.custom

add_dist = gtkhtml-sharp-2.0.pc.in

include ../Makefile.include

