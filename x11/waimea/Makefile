# $OpenBSD: Makefile,v 1.24 2017/10/23 17:11:06 sthen Exp $

COMMENT=		virtual desktop manager for X11

VERSION=		0.4.0
DISTNAME=		waimea-${VERSION}
REVISION =		8
CATEGORIES=		x11

HOMEPAGE=		http://www.freedesktop.org/wiki/Software/waimea

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=		${MASTER_SITE_SOURCEFORGE:=waimea/}

WANTLIB += ICE SM X11 Xau Xdmcp Xext Xft Xinerama Xrandr Xrender
WANTLIB += c expat fontconfig freetype m ${COMPILER_LIBCXX}
WANTLIB += xcb z

AUTOCONF_VERSION=	2.52
CONFIGURE_STYLE=	autoconf
CONFIGURE_ARGS=		--disable-pixmap

.include <bsd.port.mk>
