# alpine-node-mapnik

Minimal Docker image built on Alpine Linux with Node.

# Image contents
- Base image is `mhart/alpine-node:latest`
   - https://github.com/mhart/alpine-node
- Mapnik version 3.1.0
   - https://github.com/mapnik/mapnik/tree/bfb071233eefe96607079d3b41c127a3e3c41b79
   - Compiled with the following flags: `-I/opt/mapnik/include -I/opt/mapnik/include/mapnik/agg -I/opt/mapnik/include/mapnik -I/usr/include -I/usr/include/freetype2 -I/usr/include/cairo -I/usr/include/glib-2.0 -I/usr/lib/glib-2.0/include -I/usr/include/pixman-1 -I/usr/include/libpng16 -DMAPNIK_MEMORY_MAPPED_FILE -DMAPNIK_HAS_DLCFN -DBIGINT -DHAVE_JPEG -DHAVE_PNG -DLINUX -DMAPNIK_THREADSAFE -DBOOST_SPIRIT_NO_PREDEFINED_TERMINALS=1 -DBOOST_PHOENIX_NO_PREDEFINED_TERMINALS=1 -DBOOST_SPIRIT_USE_PHOENIX_V3=1 -DNDEBUG -DHAVE_CAIRO -DGRID_RENDERER -std=c++14 -fvisibility=hidden -fvisibility-inlines-hidden -Wall -pthread -ftemplate-depth-300 -Wsign-compare -O3 -L/opt/mapnik/lib -lmapnik -L/usr/lib -pthread -lboost_filesystem -lboost_regex -lcairo -lpng -lboost_system -lharfbuzz -ljpeg -licuuc -lfreetype -lz -ldl`
- node-mapnik version 3.7.0-dev
   - https://github.com/mapnik/node-mapnik/tree/13f865d762ac8e61521228f50e60bfedc873d34c

# How to use?
Mapnik is installed in /opt and added to `PATH`. You can use `mapnik-render` to render stylesheets in command line. Alternatively, you can use node-mapnik Node module. Note that you should put node-mapnik local dependency to your package.json, like so:
```json
"dependencies": {
  "mapnik": "/opt/node-mapnik"
}
```

This will reference already installed and compiled node-mapnik from /opt instead of installing it from repository.
