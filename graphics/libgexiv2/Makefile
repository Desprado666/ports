# $OpenBSD: Makefile,v 1.34 2018/04/28 11:03:20 ajacoutot Exp $

COMMENT=		GObject wrapper around exiv2

GNOME_VERSION=		0.10.8
GNOME_PROJECT=		gexiv2
PKGNAME=		lib${DISTNAME}
REVISION=		3

CATEGORIES=		graphics

SHARED_LIBS +=  gexiv2               3.0      # 2.0

MAINTAINER=		Jasper Lievisse Adriaanse <jasper@openbsd.org>, \
			Antoine Jacoutot <ajacoutot@openbsd.org>

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += ${COMPILER_LIBCXX} exiv2 expat ffi glib-2.0 gobject-2.0
WANTLIB += iconv intl m pcre z

MODULES=		lang/python \
			x11/gnome

MODGNOME_TOOLS=		gobject-introspection vala
MODPY_VERSION=		${MODPY_DEFAULT_VERSION_3}

# C++11
COMPILER =		base-clang ports-gcc
CXXFLAGS +=		-std=c++11

LIB_DEPENDS=		devel/glib2 \
			graphics/exiv2

# import gi
BUILD_DEPENDS=		devel/py-gobject3${MODPY_FLAVOR}
RUN_DEPENDS=		devel/py-gobject3${MODPY_FLAVOR}

CONFIGURE_STYLE=	gnu

# we need support for both python2 and python3
BUILD_DEPENDS +=	lang/python/${MODPY_DEFAULT_VERSION_2} \
			devel/py-gobject3
RUN_DEPENDS +=		lang/python/${MODPY_DEFAULT_VERSION_2} \
			devel/py-gobject3

.include <bsd.port.mk>
