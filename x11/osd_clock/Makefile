# $OpenBSD: Makefile,v 1.15 2015/11/24 09:11:07 jasper Exp $

COMMENT=	xosd based clock
DISTNAME=	osd_clock-0.5
REVISION=	2

CATEGORIES=	x11
MASTER_SITES=	https://distfiles.nl/

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

NO_TEST=	Yes

LIB_DEPENDS=	x11/xosd
WANTLIB=	X11 Xext Xt c pthread xosd

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/osd_clock ${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/osd_clock.1 ${PREFIX}/man/man1

.include <bsd.port.mk>
