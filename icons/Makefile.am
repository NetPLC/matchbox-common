xpms =  mbadd.xpm   mbfolder.xpm      mbnoapp.xpm   mbup.xpm \
        mbdown.xpm  mbfolderprev.xpm  mbremove.xpm

pngs = mbadd.png   mbfolder.png      mbnoapp.png   mbup.png \
       mbdown.png  mbfolderprev.png  mbremove.png

EXTRA_DIST = $(pngs) $(xpms) 

if WANT_PNG
imgs = $(pngs)
else
imgs = $(xpms)
endif

pixmapsdir  = $(datadir)/pixmaps
pixmaps_DATA = $(imgs)
