# $OpenBSD: Makefile,v 1.13 2017/11/21 00:13:04 naddy Exp $

COMMENT =		async i/o library

DISTNAME =		eio-1.7.10
REVISION =		0

SHARED_LIBS +=	eio                  2.0      # 8.10

# LGPL v2.1
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =  crypto ecore eet eina glib-2.0 iconv intl jpeg m pcre pthread
WANTLIB += ssl z

LIB_DEPENDS =		x11/e17/ecore>=1.7.10v2

CONFIGURE_ARGS =	--disable-doc

.include <bsd.port.mk>
