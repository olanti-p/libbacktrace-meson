# Copyright (C) 2021 Alexandros Theodotou <alex at zrythm dot org>
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU Affero General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU Affero General Public License for more details.
#
# You should have received a copy of the GNU Affero General Public License
# along with this program.  If not, see <https://www.gnu.org/licenses/>.

project (
  'libbacktrace', ['c'],
  version: '1.0.0',
  license: 'BSD',
  meson_version: '>= 0.55.0',
  default_options: [
    'buildtype=debug',
    'c_std=gnu11',
    ],
  )

cc = meson.get_compiler ('c')

# detect OS
os_darwin = false
os_linux = false
os_freebsd = false
os_windows = false
if host_machine.system() == 'darwin'
  os_darwin = true
elif host_machine.system() == 'linux'
  os_linux = true
elif host_machine.system() == 'freebsd'
  os_freebsd = true
elif host_machine.system() == 'windows'
  os_windows = true
endif

inc = [
  include_directories ('.'),
  ]

srcs = files ([
  'alloc.c',
  'atomic.c',
  'elf.c',
  'instrumented_alloc.c',
  'mmap.c',
  'pecoff.c',
  'print.c',
  'simple.c',
  'state.c',
  'ttest.c',
  'unknown.c',
  'allocfail.c',
  'backtrace.c',
  'dwarf.c',
  'edtest2.c',
  'fileline.c',
  'macho.c',
  'mmapio.c',
  'nounwind.c',
  'posix.c',
  'read.c',
  'sort.c',
  'stest.c',
  ])

libbacktrace = static_library (
  'libbacktrace',
  sources: srcs,
  include_directories: inc,
  install: false)

# this is so that it can be used as a meson
# subproject
libbacktrace_dep = declare_dependency (
  include_directories: inc,
  link_with: libbacktrace)
