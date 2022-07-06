project('execinfo', 'c', version : '1.0.0')
pkg = import('pkgconfig')

stacktraverse = static_library('stacktraverse', 'stacktraverse.c')
execinfo = library('execinfo', 'execinfo.c',
                   link_with : stacktraverse, install : true)

pkg.generate(execinfo,
             description : 'Clone of the backtrace facility found in glibc')

