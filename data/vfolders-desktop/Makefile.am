desktop_files = \
 Accessories.directory   Graphics.directory    Root.directory      \
 Applications.directory  Internet.directory    Root.order          \
 Development.directory   Multimedia.directory  Settings.directory  \
 Games.directory         Office.directory      System.directory    

EXTRA_DIST = $(desktop_files)

if !WANT_PDA_FOLDERS
  vfoldersdir = $(pkgdatadir)/vfolders
  vfolders_DATA = $(desktop_files)
endif
