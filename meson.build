project('com.github.skarva.lockbox', 'vala', 'c', meson_version: '>= 0.43', version: '1.2')

i18n = import('i18n')

add_project_arguments(['--vapidir', join_paths(meson.current_source_dir(), 'vapi')], language: 'vala')
add_project_arguments([
        '-DGETTEXT_PACKAGE="@0@"'.format(meson.project_name())
    ],
    language: 'c',
)

dependencies = [
    dependency('libsecret-1'),
    dependency('granite'),
    meson.get_compiler('vala').find_library('posix'),
    meson.get_compiler('c').find_library('m', required : false)
]

subdir('data')
subdir('src')
subdir('po')

meson.add_install_script('meson/post_install.py')
