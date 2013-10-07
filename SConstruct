#! /bin/python
# Graphics Language Renderer (glr) SConstruct file
import subprocess, sys, os
import glob
import multiprocessing



# Tell SCons to create our build files in the 'build' directory
VariantDir('build', 'src', duplicate=0)



### Set our source files
source_files = Glob('build/*.cpp', 'build/*.h')


cpp_paths = []
cpp_defines = []
cpp_flags = []
library_paths = []


library_paths.append('/home/jarrett/projects/berkelium2/cef3/Release')

### Set our required libraries
libraries = [
'cef',
'GL',
'GLU',
'GLEW',
'Xmu',
'Xt',
'SM',
'ICE',
'pthread',
'gthread-2.0',
'gtkglext-x11-1.0',
'gdkglext-x11-1.0',
'gtk-x11-2.0',
'pangox-1.0',
'X11',
'gmodule-2.0',
'gdk-x11-2.0',
'atk-1.0',
'gio-2.0',
'pangoft2-1.0',
'pangocairo-1.0',
'gdk_pixbuf-2.0',
'cairo',
'pango-1.0',
'freetype',
'fontconfig',
'gobject-2.0',
'glib-2.0'
]

cpp_paths.append('/home/jarrett/projects/berkelium2/cef3')
cpp_paths.append('/usr/include/gtk-2.0')
cpp_paths.append('/usr/lib/x86_64-linux-gnu/gtk-2.0/include')
cpp_paths.append('/usr/include/atk-1.0')
cpp_paths.append('/usr/include/cairo')
cpp_paths.append('/usr/include/gdk-pixbuf-2.0')
cpp_paths.append('/usr/include/pango-1.0')
cpp_paths.append('/usr/include/gio-unix-2.0')
cpp_paths.append('/usr/include/glib-2.0')
cpp_paths.append('/usr/lib/x86_64-linux-gnu/glib-2.0/include')
cpp_paths.append('/usr/include/pixman-1')
cpp_paths.append('/usr/include/freetype2')
cpp_paths.append('/usr/include/libpng12')
cpp_paths.append('/usr/include/harfbuzz')
cpp_paths.append('/usr/include/gtkglext-1.0')
cpp_paths.append('/usr/lib/gtkglext-1.0/include')

#cpp_paths.append('/usr/include/gtkglext-1.0')
#cpp_paths.append('/usr/lib/gtkglext-1.0/include')

### Create our environment
env = Environment(ENV = os.environ, CCFLAGS=[]) 

### Set our environment variables
env.Append( CPPFLAGS = cpp_flags )
env.Append( CPPDEFINES = cpp_defines )
env.Append( CPPPATH = cpp_paths )

env.SetOption('num_jobs', multiprocessing.cpu_count())



# Tell SCons the library to build
env.Program('build/berkelium2', source_files, LIBS = libraries, LIBPATH = library_paths)
