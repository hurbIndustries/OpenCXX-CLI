##  opencxx_cli
##  ./src/meson.build
##  Copyright 2024 - hurbIndustries
##  JPD

pkg = import('pkgconfig')

source_files = [
    'colors.cpp',
    'cli.cpp'
]

opencxx_cli = library('opencxx-cli',
    source_files,
    include_directories : inc,
)

unitTests = executable('unitTests', 
    'unitTests.cpp',
    include_directories : inc,
    link_with : [opencxx_cli]
)

test('err', unitTests, args : ['-err'])
test('warn', unitTests, args : ['-warn'])
test('info', unitTests, args : ['-info'])
test('addEntryOnce', unitTests, args : ['-addEntryOnce'])
test('addEntryTwice', unitTests, args : ['-addEntryTwice'])
test('testParse1', unitTests, args : ['-testParse', '--test'])
test('testParse2', unitTests, args : ['-testParse', '--t2'])
test('help', unitTests, args : ['-help'])
test('testArgPass', unitTests, args : ['-testArgPass', '--test', ''])
pkg.generate(opencxx_cli)