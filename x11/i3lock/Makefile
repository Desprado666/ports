# $OpenBSD: Makefile,v 1.3 2018/03/14 17:30:00 jasper Exp $

COMMENT =		improved screen locker

GH_ACCOUNT =		i3
GH_PROJECT =		i3lock
GH_TAGNAME =		2.10

CATEGORIES =		x11

HOMEPAGE =		https://i3wm.org/i3lock/

MAINTAINER =		Jasper Lievisse Adriaanse <jasper@openbsd.org>

# BSD
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += c cairo ev m xcb xcb-image xcb-shm xcb-randr
WANTLIB += xcb-util xcb-xinerama xcb-xkb xkbcommon xkbcommon-x11

LIB_DEPENDS =		devel/libev \
			graphics/cairo \
			x11/xkbcommon

USE_GMAKE =		Yes

NO_TEST =		Yes

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/i3lock ${PREFIX}/bin/i3lock
	${INSTALL_MAN} ${WRKSRC}/i3lock.1 ${PREFIX}/man/man1

.include <bsd.port.mk>
