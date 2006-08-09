EXTRA_DIST =				\
	gnome-sharp-2.16-sources.xml	\
	gtkhtml-font-style-enum.patch


GNOME_2_16_DOWNLOADS = \
	http://ftp.gnome.org/pub/GNOME/platform/2.15/2.15.4/sources/gnome-vfs-2.15.3.tar.bz2		\
	http://ftp.gnome.org/pub/GNOME/platform/2.15/2.15.4/sources/libgnome-2.15.1.tar.bz2       	\
	http://ftp.gnome.org/pub/GNOME/platform/2.15/2.15.4/sources/libgnomecanvas-2.14.0.tar.bz2 	\
	http://ftp.gnome.org/pub/GNOME/platform/2.15/2.15.4/sources/libgnomeui-2.15.2.tar.bz2     	\
	http://ftp.gnome.org/pub/GNOME/platform/2.10/2.10.0/sources/libgnomeprint-2.10.0.tar.bz2		\
	http://ftp.gnome.org/pub/GNOME/platform/2.10/2.10.0/sources/libgnomeprintui-2.10.0.1.tar.bz2	\
	http://ftp.gnome.org/pub/GNOME/desktop/2.15/2.15.4/sources/gnome-panel-2.14.2.tar.bz2		\
	http://ftp.gnome.org/pub/GNOME/desktop/2.6/2.6.0/sources/libart_lgpl-2.3.16.tar.bz2	\
	http://ftp.gnome.org/pub/GNOME/desktop/2.6/2.6.0/sources/librsvg-2.6.4.tar.bz2         	\
	http://ftp.gnome.org/pub/GNOME/desktop/2.15/2.15.90/sources/vte-0.13.4.tar.bz2

GTKHTML_SOURCEFILES = \
        gtkhtml-3.0.10/src/gtkhtml.c \
        gtkhtml-3.0.10/src/gtkhtml.h \
        gtkhtml-3.0.10/src/gtkhtml-types.h \
        gtkhtml-3.0.10/src/gtkhtml-enums.h \
        gtkhtml-3.0.10/src/gtkhtml-embedded.c \
        gtkhtml-3.0.10/src/gtkhtml-embedded.h \
        gtkhtml-3.0.10/src/gtkhtml-stream.c \
        gtkhtml-3.0.10/src/gtkhtml-stream.h

api: api-2.16

api-2.16:
	$(GAPI_PARSER) gnome-sharp-2.16-sources.xml

get-source-code: get-2.16-sources get-gtkhtml-code

get-gtkhtml-code:
	wget http://ftp.gnome.org/pub/GNOME/sources/gtkhtml/3.0/gtkhtml-3.0.10.tar.bz2 --output-document=- | tar -xj $(GTKHTML_SOURCEFILES)
	patch -p0 < gtkhtml-font-style-enum.patch

get-2.16-sources:
	for i in $(GNOME_2_16_DOWNLOADS); do                  \
		wget $$i --output-document=- | tar -xj ;   \
	done;

