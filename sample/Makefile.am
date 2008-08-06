SUBDIRS = gconf gnomevfs 

if ENABLE_GNOME
GNOME_TARGETS=gnome-hello-world.exe canvas-example.exe fifteen.exe
GNOME_ASSEMBLY=../art/art-sharp.dll ../gnome/gnome-sharp.dll
else
GNOME_TARGETS=
GNOME_ASSEMBLY=
endif

if ENABLE_GNOMEVFS
GNOMEVFS_TARGETS=testvfs.exe
GNOMEVFS_ASSEMBLY=../gnomevfs/gnome-vfs-sharp.dll
else
GNOMEVFS_TARGETS=
GNOMEVFS_ASSEMBLY=
endif

TARGETS = $(GNOMEVFS_TARGETS) $(GNOME_TARGETS)

DEBUGS = $(addsuffix .mdb, $(TARGETS))

assemblies= $(GNOMEVFS_ASSEMBLY) $(GNOME_ASSEMBLY)
references=$(GTKSHARP_LIBS) $(addprefix /r:, $(assemblies))

noinst_SCRIPTS = $(TARGETS)
CLEANFILES = $(TARGETS) $(DEBUGS)

gnome-hello-world.exe: $(srcdir)/GnomeHelloWorld.cs $(assemblies)
	$(CSC)  /out:gnome-hello-world.exe $(references) $(srcdir)/GnomeHelloWorld.cs

canvas-example.exe: $(srcdir)/CanvasExample.cs $(assemblies)
	$(CSC)  /out:canvas-example.exe $(references) $(srcdir)/CanvasExample.cs

fifteen.exe: $(srcdir)/Fifteen.cs $(assemblies)
	$(CSC)  /out:fifteen.exe $(references) $(srcdir)/Fifteen.cs

testvfs.exe: $(srcdir)/TestVfs.cs $(assemblies)
	$(CSC) /debug /out:testvfs.exe $(references) $(srcdir)/TestVfs.cs

EXTRA_DIST = 				\
	GnomeHelloWorld.cs		\
	CanvasExample.cs		\
	Fifteen.cs			\
	TestVfs.cs
