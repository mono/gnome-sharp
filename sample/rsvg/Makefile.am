assemblies = ../../art/art-sharp.dll ../../rsvg/rsvg-sharp.dll
references = $(GTKSHARP_LIBS) $(addprefix /r:, $(assemblies))

if ENABLE_RSVG
TARGETS = svghelloworld.exe
else
TARGETS = 
endif
CLEANFILES = $(TARGETS)
noinst_SCRIPTS = $(TARGETS)
EXTRA_DIST = svghelloworld.cs sample.svg

SOURCES = $(srcdir)/svghelloworld.cs
svghelloworld.exe: $(SOURCES) $(assemblies)
	$(CSC) /out:svghelloworld.exe $(SOURCES) $(references)

