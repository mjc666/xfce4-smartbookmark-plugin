@SET_MAKE@

SUBDIRS = \
	po \
	src

distclean-local:
		rm -rf *.cache *~ 

.PHONY: ChangeLog

ChangeLog: Makefile
	(GIT_DIR=$(top_srcdir)/.git git log > .changelog.tmp \
	&& mv .changelog.tmp ChangeLog; rm -f .changelog.tmp) \
	|| (touch ChangeLog; echo 'Git directory not found: installing possibly empty changelog.' >&2)

dist-hook: ChangeLog

EXTRA_DIST = \
        README \
        intltool-extract.in \
        intltool-merge.in \
        intltool-update.in

DISTCLEANFILES = \
        intltool-extract \
        intltool-merge \
        intltool-update
