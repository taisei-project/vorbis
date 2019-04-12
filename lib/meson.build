
vorbis_overrides = ['c_std=none']

vorbis_sources = files(
    'mdct.c',
    'smallft.c',
    'block.c',
    'envelope.c',
    'window.c',
    'lsp.c',
    'lpc.c',
    'analysis.c',
    'synthesis.c',
    'psy.c',
    'info.c',
    'floor1.c',
    'floor0.c',
    'res0.c',
    'mapping0.c',
    'registry.c',
    'codebook.c',
    'sharedbook.c',
    'lookup.c',
    'bitrate.c'
)

vorbisfile_sources = files(
    'vorbisfile.c',
)

vorbisenc_sources = files(
    'vorbisenc.c',
)

libvorbis = library('vorbis', vorbis_sources,
    include_directories : incdir,
    dependencies : [ogg_dep, m_dep],
    override_options : vorbis_overrides,
    build_by_default : not meson.is_subproject(),
)

libvorbis_dep = declare_dependency(
    link_with : libvorbis,
    include_directories : incdir,
)

libvorbisfile = library('vorbisfile', vorbisfile_sources,
    include_directories : incdir,
    link_with : libvorbis,
    dependencies : [ogg_dep, m_dep],
    override_options : vorbis_overrides,
    build_by_default : not meson.is_subproject(),
)

vorbisfile_dep = declare_dependency(
    dependencies : ogg_dep,
    link_with : libvorbisfile,
    include_directories : incdir
)

libvorbisenc = library('vorbisenc', vorbisenc_sources,
    include_directories : incdir,
    link_with : libvorbis,
    override_options : vorbis_overrides,
    build_by_default : not meson.is_subproject(),
)

vorbisenc_dep = declare_dependency(
    dependencies : ogg_dep,
    link_with : libvorbisenc,
    include_directories : incdir
)
