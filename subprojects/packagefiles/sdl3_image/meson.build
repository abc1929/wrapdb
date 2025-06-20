project('sdl3_image', 'c', version: '3.2.4')

sdl_dep = dependency('sdl3', version: '>=3.2.4', required: true)

png_dep = dependency('libpng')
jpg_dep = dependency('libjpeg', required: false)

img_args = [
  '-DLOAD_BMP',
  '-DLOAD_GIF',
  '-DLOAD_JPG',
  '-DLOAD_PNG',
  '-DLOAD_SVG',
  '-DUSE_STBIMAGE',
]

img_args += [
  '-DSDL_IMAGE_SAVE_PNG=1',
  '-DSDL_IMAGE_SAVE_JPG=1',
]

subdir('src')
img_lib = library(
  'sdl3_image',
  img_src,
  c_args: img_args,
  include_directories: 'include',
  dependencies: [png_dep, sdl_dep] + (jpg_dep.found() ? [jpg_dep] : []),
)

sdl3_image_dep = declare_dependency(include_directories: 'include', link_with: img_lib)