#
#  Copyright 2019 Northern.tech AS
#
#  This file is part of CFEngine 3 - written and maintained by Northern.tech AS.
#
#  This program is free software; you can redistribute it and/or modify it
#  under the terms of the GNU General Public License as published by the
#  Free Software Foundation; version 3.
#
#  This program is distributed in the hope that it will be useful,
#  but WITHOUT ANY WARRANTY; without even the implied warranty of
#  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#  GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA  02111-1307, USA
#
# To the extent this program is licensed as part of the Enterprise
# versions of CFEngine, the applicable Commercial Open Source License
# (COSL) may apply to this file if you as a licensee so wish it. See
# included file COSL.txt.
#
noinst_LTLIBRARIES = libutils.la

# TODO remove the openssl dependency! It's only there for base64 encoding.
AM_CFLAGS   = $(PCRE_CFLAGS) $(OPENSSL_CFLAGS)
AM_CPPFLAGS = $(PCRE_CPPFLAGS) $(OPENSSL_CPPFLAGS)
AM_LDFLAGS  = $(PCRE_LDFLAGS) $(OPENSSL_LDFLAGS)

libutils_la_LIBADD = ../libcompat/libcompat.la
libutils_la_LIBS   = $(PCRE_LIBS) $(OPENSSL_LIBS)

libutils_la_SOURCES = \
	alloc.c alloc.h \
	array_map.c array_map_priv.h \
	bool.h \
	buffer.c buffer.h \
	cleanup.c cleanup.h \
	compiler.h \
	csv_writer.c csv_writer.h \
	csv_parser.c csv_parser.h \
	definitions.h \
	deprecated.h \
	dir.h dir_priv.h \
	encode.c encode.h \
	file_lib.c file_lib.h \
	hash.c hash.h \
	hash_map.c hash_map_priv.h \
	hash_method.h \
	ip_address.c ip_address.h \
	json.c json.h json-priv.h \
	json-utils.c json-utils.h \
	json-yaml.c json-yaml.h \
	known_dirs.c known_dirs.h \
	libcrypto-compat.c libcrypto-compat.h \
	list.c list.h \
	logging.c logging.h logging_priv.h \
	man.c man.h \
	map.c map.h map_common.h \
	misc_lib.c misc_lib.h \
	mustache.c mustache.h \
	mutex.c mutex.h \
	passopenfile.c passopenfile.h \
	path.c path.h \
	pcre_include.h \
	pcre_wrap.c pcre_wrap.h \
	platform.h condition_macros.h \
	printsize.h \
	proc_keyvalue.c proc_keyvalue.h \
	queue.c queue.h \
	rb-tree.c rb-tree.h \
	refcount.c refcount.h \
	regex.c regex.h \
	ring_buffer.c ring_buffer.h \
	sequence.c sequence.h \
	set.c set.h \
	stack.c stack.h \
	statistics.c statistics.h \
	string_lib.c string_lib.h \
	threaded_deque.c threaded_deque.h \
	threaded_queue.c threaded_queue.h \
	unicode.c unicode.h \
	writer.c writer.h \
	xml_writer.c xml_writer.h

if !NT
  libutils_la_SOURCES += unix_dir.c
endif
if CYGWIN
  libutils_la_SOURCES += unix_dir.c
endif

CLEANFILES = *.gcno *.gcda

#
# Some basic clean ups
#
MOSTLYCLEANFILES = *~ *.orig *.rej

#
# Get everything removed down to where rebuilding requires:
# "aclocal; autoconf; autoheader; automake --add-missing"
# "configure; make; make install"
#
MAINTAINERCLEANFILES = config.h.in
