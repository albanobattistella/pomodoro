project('com.github.oowoosh0.pomodoro', 'vala', 'c')

gnome = import('gnome')
i18n = import('i18n')

add_global_arguments('-DGETTEXT_PACKAGE="@0@"'.format (meson.project_name()), language:'c')

gresources = gnome.compile_resources(
    'as-resources', 'data/css.gresource.xml',
    source_dir: 'data',
    c_name: 'as'
)

executable(
    meson.project_name(),
    gresources,
    'src/Application.vala',
    'src/MainWindow.vala',
    'src/NotificationManager.vala',
    'src/Widgets/TimerLabel.vala',
    'src/Widgets/PreferencesDialog.vala',
    'src/Timer/Interval.vala',
    'src/Timer/IntervalState.vala',
    'src/Timer/WorkInterval.vala',
    'src/Timer/BreakInterval.vala',
    'src/Timer/LongBreakInterval.vala',
    dependencies : [
        dependency('glib-2.0'),
        dependency('gtk+-3.0'),
        dependency('granite', version: '>=6.0.0'),
        dependency('libhandy-1', version: '>= 0.90.0')
    ],
    install: true
)


subdir('data')
subdir('po')

meson.add_install_script('meson/post_install.py')
