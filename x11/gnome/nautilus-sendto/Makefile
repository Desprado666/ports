# $OpenBSD: Makefile,v 1.69 2017/11/01 18:41:34 ajacoutot Exp $

COMMENT=		applications integration into Nautilus

GNOME_PROJECT=		nautilus-sendto
GNOME_VERSION=		3.8.6

CATEGORIES=		mail net

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += c gio-2.0 glib-2.0 gobject-2.0 intl

MODULES=		devel/meson \
			x11/gnome

MODGNOME_TOOLS=		gobject-introspection

BUILD_DEPENDS=		devel/appstream-glib # XXX check if needed next release
LIB_DEPENDS=		devel/glib2

# fix build with clang (see patch-src_nautilus-sendto_c)
CFLAGS +=		-Wno-error=format-nonliteral

.include <bsd.port.mk>
