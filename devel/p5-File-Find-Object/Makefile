# $OpenBSD: Makefile,v 1.5 2017/11/02 15:00:21 bluhm Exp $

COMMENT =	object oriented File::Find replacement

# Most versions start with v, some do not and confuse portroach, skip those.
PORTROACH =	skipv:0.0.1,0.0.2,0.3.0

VERSION =	0.3.2
DISTNAME =	File-Find-Object-v${VERSION}
PKGNAME =	p5-File-Find-Object-${VERSION}

CATEGORIES =	devel

CPAN_AUTHOR =		SHLOMIF

MAINTAINER =		Alexander Bluhm <bluhm@openbsd.org>

# Artistic 2
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		cpan
RUN_DEPENDS =		devel/p5-Class-XSAccessor

PKG_ARCH =		*

# v0.3.2 tar ball contains emacs backup files, they make review harder, remove
post-extract:
	find ${WRKDIST} -name '*~' | xargs rm --

.include <bsd.port.mk>
