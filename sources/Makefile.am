EXTRA_DIST =				\
	gnome-sharp-2.20-sources.xml


GNOME_2_20_DOWNLOADS = \
	http://ftp.gnome.org/pub/GNOME/platform/2.20/2.20.0/sources/gnome-vfs-2.20.0.tar.bz2		\
	http://ftp.gnome.org/pub/GNOME/platform/2.20/2.20.0/sources/libgnome-2.20.0.tar.bz2       	\
	http://ftp.gnome.org/pub/GNOME/platform/2.20/2.20.0/sources/libgnomecanvas-2.20.0.tar.bz2 	\
	http://ftp.gnome.org/pub/GNOME/platform/2.20/2.20.0/sources/libgnomeui-2.20.0.tar.bz2     	\
	http://ftp.gnome.org/pub/GNOME/desktop/2.20/2.20.0/sources/libgnomeprint-2.18.2.tar.bz2		\
	http://ftp.gnome.org/pub/GNOME/desktop/2.20/2.20.0/sources/libgnomeprintui-2.18.1.tar.bz2	\
	http://ftp.gnome.org/pub/GNOME/desktop/2.20/2.20.0/sources/gnome-panel-2.20.0.1.tar.bz2		\
	http://ftp.gnome.org/pub/GNOME/platform/2.20/2.20.0/sources/libart_lgpl-2.3.19.tar.bz2

api: api-2.20

api-2.20:
	$(GAPI_PARSER) gnome-sharp-2.20-sources.xml

get-source-code: get-2.20-sources

get-2.20-sources:
	for i in $(GNOME_2_20_DOWNLOADS); do                  \
		wget $$i --output-document=- | tar -xj ;   \
	done;

