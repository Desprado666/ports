# $OpenBSD: Makefile,v 1.58 2018/07/06 06:04:46 espie Exp $

COMMENT=		GNOME power manager

GNOME_PROJECT=		gnome-power-manager
GNOME_VERSION=		3.26.0
REVISION=		2

# LGPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += c cairo gio-2.0 glib-2.0 gobject-2.0 gtk-3 intl pango-1.0
WANTLIB += pangocairo-1.0 upower-glib

MODULES=		devel/dconf \
			devel/meson \
			x11/gnome

MODGNOME_TOOLS=		desktop-file-utils gtk-update-icon-cache

LIB_DEPENDS=		sysutils/upower \
			x11/gtk+3

.include <bsd.port.mk>
