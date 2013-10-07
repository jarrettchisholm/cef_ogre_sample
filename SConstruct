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


#library_paths.append('/home/jarrett/projects/berkelium2/cef3/Release')
library_paths.append('./lib')

### Set our required libraries
libraries = [
'cef',
'cef_dll_wrapper',
'OgreMain'
]

# pkg-config --cflags gtk+-2.0
#cpp_paths.append('/home/jarrett/projects/berkelium2/cef3')
#cpp_paths.append('/home/jarrett/projects/berkelium2/cef3/include')
cpp_paths.append('/usr/local/include/cef3')
cpp_paths.append('/home/jarrett/projects/ogre')
cpp_paths.append('/usr/include/gtk-2.0')
cpp_paths.append('/usr/lib/x86_64-linux-gnu/gtk-2.0/include')
cpp_paths.append('/usr/include/atk-1.0')
cpp_paths.append('/usr/include/cairo')
cpp_paths.append('/usr/include/gdk-pixbuf-2.0')
cpp_paths.append('/usr/include/pango-1.0')
cpp_paths.append('/usr/include/glib-2.0')
cpp_paths.append('/usr/lib/x86_64-linux-gnu/glib-2.0/include')


cpp_flags.append('-std=c++11')

### Create our environment
env = Environment(ENV = os.environ, CCFLAGS=[]) 

### Set our environment variables
env.Append( CPPFLAGS = cpp_flags )
env.Append( CPPDEFINES = cpp_defines )
env.Append( CPPPATH = cpp_paths )

env.SetOption('num_jobs', multiprocessing.cpu_count())

### Set our runtime library locations
env.Append( RPATH = env.Literal(os.path.join('\\$$ORIGIN', os.pardir, 'lib')))



# Tell SCons the library to build
env.Program('build/berkelium2', source_files, LIBS = libraries, LIBPATH = library_paths)
