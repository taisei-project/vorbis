project('vorbis', 'c', version : '1.3.6', license : 'bsd-style')

# Based on https://github.com/mesonbuild/vorbis/blob/1.3.5/meson.build

ogg_dep = dependency('ogg', fallback : ['ogg', 'libogg_dep'])
m_dep = meson.get_compiler('c').find_library('m', required : false)

incdir = include_directories('include')
subdir('lib')
