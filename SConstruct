import os

sources = Split("""
	recognitionTest.cpp""")

# Setup options
opts = Options()
opts.AddOptions(
	PathOption('extra_include_path', 'Additional include directory', '.'), 
	PathOption('extra_lib_path', 'Additional lib directory', '.'))

env = Environment(ENV = os.environ,
		options = opts,
		LIBS = ['jvm'])

if env['PLATFORM'] == 'irix':
	env.Append(CXXFLAGS = ['-ansi', '-LANG:std', '-n32'])

env.Append(CPPPATH = env['extra_include_path'], 
	LIBPATH = env['extra_lib_path'])

# Generate command line help text
env.Help(opts.GenerateHelpText(env))

env.Program(sources)
