qom_ss = ss.source_set()
qom_ss.add(genh)
qom_ss.add(files(
  'container.c',
  'object.c',
  'object_interfaces.c',
  'qom-qobject.c',
))

qmp_ss.add(files('qom-qmp-cmds.c'))
softmmu_ss.add(files('qom-hmp-cmds.c'))

qom_ss = qom_ss.apply(config_host, strict: false)
libqom = static_library('qom', qom_ss.sources() + genh,
                        dependencies: [qom_ss.dependencies()],
                        name_suffix: 'fa')

qom = declare_dependency(link_whole: libqom)
