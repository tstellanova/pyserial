import os

env = Environment(ENV = os.environ, tools=['default', 'mb_install'])

source = env.MBMagicPythonGlob('serial')

build = env.Command('pyserial/build', 'setup.py', 'python setup.py build')
env.Clean(build, '#/build')

pyserial_egg = env.MBDistEgg('dist/pyserial-2.7_mb2.1', source)
env.MBInstallEgg(pyserial_egg)
env.Clean(pyserial_egg, '#/dist')
env.Clean(pyserial_egg, '#/pyserial.egg-info')

if env.MBIsMac():
    pyserial_egg26 = env.MBDistEgg(
        'dist/pyserial-2.7_mb2.1',
        source,
        python = 'python2.6',
        version = '2.6')
    env.MBInstallEgg(pyserial_egg26)
    env.Clean(pyserial_egg26, '#/dist')
    env.Clean(pyserial_egg26, '#/pyserial.egg-info')

env.MBCreateInstallTarget()
