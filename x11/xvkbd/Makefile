# $OpenBSD: Makefile,v 1.19 2015/11/17 09:05:54 ajacoutot Exp $

COMMENT=		virtual keyboard for X Window System

DISTNAME=		xvkbd-3.7
CATEGORIES=		x11
HOMEPAGE=		http://homepage3.nifty.com/tsato/xvkbd/

MAINTAINER=		Yozo TODA <yozo@v007.vaio.ne.jp>

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += ICE SM X11 Xau Xaw3d Xdmcp Xext Xmu Xpm Xt Xtst c

MASTER_SITES=		${HOMEPAGE}

LIB_DEPENDS=		x11/Xaw3d

CONFIGURE_STYLE=	imake
NO_TEST=		Yes

.include <bsd.port.mk>
