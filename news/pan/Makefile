# $OpenBSD: Makefile,v 1.58 2018/06/27 21:04:01 espie Exp $

COMMENT=	powerful newsreader

V=		0.140
DISTNAME=	pan-${V}
CATEGORIES=	news x11
REVISION=	4

HOMEPAGE=	http://pan.rebelbase.com/

MAINTAINER=	Pierre-Emmanuel Andre <pea@openbsd.org>

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += atk-1.0 c cairo cairo-gobject enchant gdk-3 gdk_pixbuf-2.0
WANTLIB += gio-2.0 glib-2.0 gmime-2.6 gmodule-2.0 gnome-keyring
WANTLIB += gnutls gobject-2.0 gthread-2.0 gtk-3 gtkspell3-3 iconv
WANTLIB += intl m notify pango-1.0 pangocairo-1.0 pthread ${COMPILER_LIBCXX}
WANTLIB += z fribidi

USE_GMAKE= 	Yes

MASTER_SITES=	http://pan.rebelbase.com/download/releases/${V}/source/

MODULES=	textproc/intltool

LIB_DEPENDS=	devel/libnotify \
		mail/gmime \
		security/gnutls \
		textproc/gtkspell3 \
		x11/gnome/libgnome-keyring
RUN_DEPENDS=	devel/desktop-file-utils

CONFIGURE_STYLE=gnu
CONFIGURE_ENV=	CPPFLAGS="-I${LOCALBASE}/include" \
		LDFLAGS="-L${LOCALBASE}/lib -liconv"
CONFIGURE_ARGS=	--with-gtk3 --enable-libnotify --enable-gkr --with-gnutls

.include <bsd.port.mk>
