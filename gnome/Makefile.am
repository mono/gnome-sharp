SUBDIRS = . glue

if ENABLE_GNOME
pkg = gnome
pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = gnome-sharp-2.0.pc
else
pkg = 
endif

INCLUDE_API = ../art/art-api.xml ../gnomevfs/gnome-vfs-api.xml
METADATA = Gnome.metadata
SYMBOLS =
references = ../art/art-sharp.dll ../gnomevfs/gnome-vfs-sharp.dll
glue_includes = gnome.h
POLICY_VERSIONS=

sources =					\
	BonoboUIVerb.cs				\
	IconTheme.cs				\
	Modules.cs

customs =					\
	About.custom				\
	App.custom				\
	DateEdit.custom				\
	CanvasBpath.custom			\
	CanvasClipgroup.custom			\
	Canvas.custom				\
	CanvasEllipse.custom			\
	CanvasGroup.custom			\
	CanvasItem.custom			\
	CanvasLine.custom			\
	CanvasPathDef.custom			\
	CanvasPixbuf.custom			\
	CanvasPoints.custom			\
	CanvasPolygon.custom			\
	CanvasRect.custom			\
	CanvasRE.custom				\
	CanvasRichText.custom			\
	CanvasShape.custom			\
	CanvasText.custom			\
	CanvasWidget.custom			\
	Client.custom				\
	Druid.custom				\
	DruidPageEdge.custom			\
	IconList.custom				\
	IconTextItem.custom			\
	Popup.custom				\
	Program.custom				\
	Scores.custom				\
	UIInfo.custom

add_dist = gnome-sharp-2.0.pc.in

include ../Makefile.include

