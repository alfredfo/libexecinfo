project('execinfo', 'c', version : '1.0.0')

pkg = import('pkgconfig')
prog_python = import('python').find_installation('python3')

stacktraverse_c = custom_target(
  'stacktraverse.c',
  output : 'stacktraverse.c',
  input : 'gen.py',
  command : [prog_python, '@INPUT@', '256'],
)

stacktraverse = static_library('stacktraverse', stacktraverse_c)
execinfo = library('execinfo', 'execinfo.c',
                   link_with : stacktraverse, install : true)

pkg.generate(execinfo,
             description : 'Clone of the backtrace facility found in glibc')

