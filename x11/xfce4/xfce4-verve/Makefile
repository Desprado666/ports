# $OpenBSD: Makefile,v 1.28 2017/10/23 17:11:06 sthen Exp $

COMMENT=	Xfce4 command line panel plugin

XFCE_VERSION=	1.1.0
XFCE_PLUGIN=	verve
REVISION =	1

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

MODULES=	x11/xfce4

WANTLIB += ICE SM X11 X11-xcb Xcomposite Xcursor Xdamage
WANTLIB += Xext Xfixes Xi Xinerama Xrandr Xrender
WANTLIB += atk-1.0 c cairo dbus-1 dbus-glib-1 exo-1 expat
WANTLIB += ffi fontconfig freetype gdk-x11-2.0 gdk_pixbuf-2.0
WANTLIB += gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0 gthread-2.0
WANTLIB += gtk-x11-2.0 m pango-1.0 pangocairo-1.0 pangoft2-1.0
WANTLIB += pcre pixman-1 png pthread startup-notification-1
WANTLIB += xcb xcb-util xcb-render xcb-shm xfce4util z
WANTLIB += harfbuzz graphite2 xfce4ui-1 iconv intl

.include <bsd.port.mk>
