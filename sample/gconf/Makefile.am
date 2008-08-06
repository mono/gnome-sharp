if ENABLE_GNOME
TARGET = sample.exe
else
TARGET =
endif

FILES = 		\
	Settings.cs 	\
	$(srcdir)/main.cs

SCHEMA = $(srcdir)/sample.schema
RESOURCES = /resource:$(srcdir)/sample.glade
ASSEMBLIES = ../../art/art-sharp.dll $(GCONFDIR)/GConf/gconf-sharp.dll ../../gnome/gnome-sharp.dll $(GCONFDIR)/GConf.PropertyEditors/gconf-sharp-peditors.dll
REFERENCES = $(GTKSHARP_LIBS) $(GLADESHARP_LIBS) $(addprefix /r:, $(ASSEMBLIES))

top_builddir=../..
GCONFDIR=$(top_builddir)/gconf

noinst_SCRIPTS = $(TARGET)

sample.exe: $(SCHEMA) $(srcdir)/sample.glade $(FILES) $(ASSEMBLIES)
	$(CSC) /out:sample.exe $(FILES) $(REFERENCES) $(RESOURCES)

Settings.cs: $(SCHEMA)
	MONO_PATH=$(top_builddir)/gconf/GConf/gconf-sharp.dll:${MONO_PATH} $(RUNTIME) $(GCONFDIR)/tools/gconfsharp-schemagen.exe Sample $(SCHEMA) > Settings.cs

CLEANFILES = sample.exe Settings.cs

EXTRA_DIST = main.cs sample.schema sample.glade sample.gladep
