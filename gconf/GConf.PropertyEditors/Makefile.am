if ENABLE_GNOME
TARGET=$(ASSEMBLY)
pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = gconf-sharp-peditors-2.0.pc
else
TARGET=
endif

ASSEMBLY = $(ASSEMBLY_NAME).dll
ASSEMBLY_NAME = gconf-sharp-peditors
noinst_DATA = $(TARGET) $(POLICY_ASSEMBLIES)
CLEANFILES = $(ASSEMBLY) $(ASSEMBLY).mdb gtk-sharp.snk $(POLICY_ASSEMBLIES) $(POLICY_CONFIGS)
DISTCLEANFILES = gconf-sharp-peditors-2.0.pc

POLICY_ASSEMBLIES = $(addsuffix .$(ASSEMBLY), $(addprefix policy., $(POLICY_VERSIONS)))
POLICY_CONFIGS = $(addsuffix .config, $(addprefix policy., $(POLICY_VERSIONS)))

EXTRA_DIST =				\
	PropertyEditorColorPicker.cs	\
	gconf-sharp-peditors-2.0.pc.in	\
	$(sources)

references = 			\
	$(GTKSHARP_LIBS)	\
	$(GLADESHARP_LIBS)	\
	/r:$(top_builddir)/art/art-sharp.dll /r:$(top_builddir)/gnome/gnome-sharp.dll /r:$(top_builddir)/gconf/GConf/gconf-sharp.dll

sources = 				\
	PropertyEditor.cs 		\
	PropertyEditorBool.cs 		\
	PropertyEditorEnum.cs 		\
	PropertyEditorEntry.cs 		\
	PropertyEditorFileEntry.cs 	\
	PropertyEditorOptionMenu.cs	\
	PropertyEditorRadioButton.cs 	\
	PropertyEditorSpinButton.cs 	\
	PropertyEditorToggleButton.cs 	\
	EditorShell.cs

build_sources = $(addprefix $(srcdir)/, $(sources)) $(top_builddir)/AssemblyInfo.cs

gtk-sharp.snk: $(top_srcdir)/gtk-sharp.snk
	cp $(top_srcdir)/gtk-sharp.snk .

if PLATFORM_WIN32
GAPI_CDECL_INSERT=$(top_srcdir)/gapi-cdecl-insert --keyfile=gtk-sharp.snk $(ASSEMBLY)
else
GAPI_CDECL_INSERT=
endif

$(ASSEMBLY): $(build_sources) gtk-sharp.snk
	@rm -f $(ASSEMBLY).mdb
	$(CSC) $(CSFLAGS) /out:$(ASSEMBLY) /target:library $(references) $(build_sources)
	$(GAPI_CDECL_INSERT)

$(POLICY_ASSEMBLIES): $(top_builddir)/policy.config gtk-sharp.snk
	@for i in $(POLICY_VERSIONS); do	\
	  echo "Creating policy.$$i.$(ASSEMBLY)";	\
	  sed -e "s/@ASSEMBLY_NAME@/$(ASSEMBLY_NAME)/" -e "s/@POLICY@/$$i/" $(top_builddir)/policy.config > policy.$$i.config;	\
	  $(AL) -link:policy.$$i.config -out:policy.$$i.$(ASSEMBLY) -keyfile:gtk-sharp.snk;	\
	done

install-data-local:
	@if test -n '$(TARGET)'; then							\
	  echo "$(GACUTIL) /i $(ASSEMBLY) /f $(GACUTIL_FLAGS)";				\
	  $(GACUTIL) /i $(ASSEMBLY) /f $(GACUTIL_FLAGS) || exit 1;			\
	  if test -n '$(POLICY_VERSIONS)'; then						\
	    for i in $(POLICY_VERSIONS); do						\
	      echo "$(GACUTIL) /i policy.$$i.$(ASSEMBLY) /f $(GACUTIL_FLAGS)";		\
	      $(GACUTIL) /i policy.$$i.$(ASSEMBLY) /f $(GACUTIL_FLAGS) || exit 1;	\
	    done									\
	  fi										\
	fi

uninstall-local:
	@if test -n '$(TARGET)'; then							\
	  echo "$(GACUTIL) /u $(ASSEMBLY_NAME) $(GACUTIL_FLAGS)";			\
	  $(GACUTIL) /u $(ASSEMBLY_NAME) $(GACUTIL_FLAGS) || exit 1;			\
	  if test -n '$(POLICY_VERSIONS)'; then						\
	    for i in $(POLICY_VERSIONS); do						\
	      echo "$(GACUTIL) /u policy.$$i.$(ASSEMBLY_NAME) $(GACUTIL_FLAGS)";	\
	      $(GACUTIL) /u policy.$$i.$(ASSEMBLY_NAME) $(GACUTIL_FLAGS) || exit 1;	\
	    done									\
	  fi										\
	fi

