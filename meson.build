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

project('libbacktrace', 'c', version: '1.0.0',
  meson_version : '>=0.57.0',
)

mod = import('unstable_external_project')

p = mod.add_project (
  'configure',
  configure_options: [
    '--prefix=@PREFIX@',
    '--libdir=@PREFIX@/@LIBDIR@',
    '--includedir=@PREFIX@/@INCLUDEDIR@',
    ],
  env: {
    'CFLAGS': '-fPIC',
    }
)

libbacktrace_dep = p.dependency('backtrace')

