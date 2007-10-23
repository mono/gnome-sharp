EXTRA_DIST =				\
	sources-2.20.xml


GNOME_2_20_DOWNLOADS = \
	http://ftp.gnome.org/pub/GNOME/desktop/2.20/2.20.0/sources/gnome-desktop-2.20.0.tar.bz2 \
	http://ftp.gnome.org/pub/GNOME/desktop/2.20/2.20.0/sources/libgtop-2.20.0.tar.bz2	\
	http://ftp.gnome.org/pub/GNOME/desktop/2.20/2.20.0/sources/nautilus-cd-burner-2.20.0.tar.bz2

api: api-2.20

api-2.20:
	$(GAPI_PARSER) sources-2.20.xml

get-source-code: get-2.20-sources

get-2.20-sources:
	for i in $(GNOME_2_20_DOWNLOADS); do                  \
		wget $$i --output-document=- | tar -xj ;   \
	done;

