# $OpenBSD: Makefile,v 1.51 2018/01/11 19:27:12 rpe Exp $

COMMENT=	simple login manager

DISTNAME=	slim-1.3.6
REVISION=	21

SHARED_LIBS=	slim	0.0 # 1.3

CATEGORIES=	x11
MAINTAINER =	Landry Breuil <landry@openbsd.org>
HOMEPAGE=	https://github.com/iwamatsu/slim

MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=slim.berlios/}

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

MODULES =	devel/cmake
LIB_DEPENDS=	graphics/jpeg \
		sysutils/consolekit \
		x11/dbus \
		graphics/png

WANTLIB += X11 Xft Xmu Xrandr Xrender c ck-connector dbus-1
WANTLIB += fontconfig freetype jpeg m png pthread ${COMPILER_LIBCXX} z

CONFIGURE_ARGS= -DUSE_CONSOLEKIT:Bool=Yes

pre-configure:
	${SUBST_CMD} ${WRKSRC}/slim.1 ${WRKSRC}/slim.conf

.include <bsd.port.mk>
