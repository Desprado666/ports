# $OpenBSD: Makefile,v 1.40 2018/06/29 22:16:37 espie Exp $

V=		5.0.0
COMMENT=	virtual sticky pad system
DISTNAME=	xpad-${V}
EXTRACT_SUFX=	.tar.bz2
CATEGORIES=	x11
REVISION=	1

HOMEPAGE=	http://xpad.sourceforge.net/
MAINTAINER=	Brian Callahan <bcallah@openbsd.org>

# GPLv3+
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += ICE SM atk-1.0 c cairo cairo-gobject gdk-3 gdk_pixbuf-2.0
WANTLIB += gio-2.0 glib-2.0 gobject-2.0 gtk-3 gtksourceview-3.0
WANTLIB += intl pango-1.0 pangocairo-1.0 pthread

MASTER_SITES=	http://launchpad.net/xpad/trunk/${V}/+download/

MODULES=	textproc/intltool

BUILD_DEPENDS=	${MODGNU_AUTOCONF_DEPENDS} \
		${MODGNU_AUTOMAKE_DEPENDS}

LIB_DEPENDS=	x11/gtksourceview3

RUN_DEPENDS=	devel/desktop-file-utils \
		x11/gtk+3,-guic

CONFIGURE_STYLE=gnu
CONFIGURE_ENV=	CPPFLAGS="-I${LOCALBASE}/include" \
		LDFLAGS="-L${LOCALBASE}/lib"

USE_GMAKE=	Yes

AUTOCONF_VERSION=	2.69
AUTOMAKE_VERSION=	1.9

pre-configure:
	cd ${WRKSRC} && ${SETENV} AUTOCONF_VERSION=${AUTOCONF_VERSION} \
		AUTOMAKE_VERSION=${AUTOMAKE_VERSION} ./autogen.sh

.include <bsd.port.mk>
