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


### Set our required libraries
libraries = [
'GL',
'GLEW',
'pthread',
'gtk-x11-2.0',
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
cpp_paths.append('/usr/include/pixman-1')
cpp_paths.append('/usr/include/freetype2')
cpp_paths.append('/usr/include/libpng12')
cpp_paths.append('/usr/include/harfbuzz')


### Create our environment
env = Environment(ENV = os.environ, CCFLAGS=[]) 

### Set our environment variables
env.Append( CPPFLAGS = cpp_flags )
env.Append( CPPDEFINES = cpp_defines )
env.Append( CPPPATH = cpp_paths )

env.SetOption('num_jobs', multiprocessing.cpu_count())



# Tell SCons the library to build
env.StaticLibrary('build/berkelium2', source_files, LIBS = libraries, LIBPATH = library_paths)
