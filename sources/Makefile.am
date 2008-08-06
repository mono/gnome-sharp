EXTRA_DIST =				\
	gnome-sharp-2.24-sources.xml


GNOME_2_24_DOWNLOADS = \
	http://ftp.gnome.org/pub/GNOME/platform/2.23/2.23.5/sources/gnome-vfs-2.22.0.tar.bz2		\
	http://ftp.gnome.org/pub/GNOME/platform/2.23/2.23.5/sources/libgnome-2.23.4.tar.bz2       	\
	http://ftp.gnome.org/pub/GNOME/platform/2.23/2.23.5/sources/libgnomecanvas-2.20.1.1.tar.bz2 	\
	http://ftp.gnome.org/pub/GNOME/platform/2.23/2.23.5/sources/libgnomeui-2.23.4.tar.bz2     	\
	http://ftp.gnome.org/pub/GNOME/platform/2.23/2.23.5/sources/libart_lgpl-2.3.20.tar.bz2

api: api-2.24

api-2.24:
	$(GAPI_PARSER) gnome-sharp-2.24-sources.xml

get-source-code: get-2.24-sources

get-2.24-sources:
	for i in $(GNOME_2_24_DOWNLOADS); do                  \
		wget $$i --output-document=- | tar -xj ;   \
	done;

