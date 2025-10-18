project(
	'pixdecor',
    'c',
	'cpp',
	version: '0.1',
	license: 'MIT',
	meson_version: '>=0.51.0',
	default_options: [
		'cpp_std=c++17',
        'c_std=c11',
		'warning_level=2',
		'werror=false',
	],
)

add_project_arguments(['-DWLR_USE_UNSTABLE'], language: ['cpp', 'c'])
add_project_arguments(['-DWAYFIRE_PLUGIN'], language: ['cpp', 'c'])
add_project_link_arguments(['-rdynamic','-fPIC'], language:'cpp')

pixdecor = shared_module(
	'pixdecor', [
		'decoration.cpp', 
		'deco-subsurface.cpp', 
		'deco-button.cpp', 
		'deco-layout.cpp', 
		'deco-theme.cpp', 
		'deco-effects.cpp',
	],

    dependencies: [
        wayfire = dependency('wayfire', version: '>=0.10.0')
		glm    = dependency('glm')
    ],

    install: true,
    install_dir: join_paths( get_option( 'libdir' ), 'wayfire' )
)

install_data( 'pixdecor.xml', install_dir: wayfire.get_variable( pkgconfig: 'metadatadir' ) )

summary = [
	'',
	'----------------',
	'wayfire-plugin-pixdecor @0@'.format( meson.project_version() ),
	'----------------',
	''
]
message('\n'.join(summary))
