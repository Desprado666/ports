# $OpenBSD: Makefile,v 1.28 2018/06/27 21:03:43 espie Exp $

COMMENT=	Night Stalker clone for X

DISTNAME=	afternoonstalker-1.1.5
REVISION=	1

CATEGORIES=	games

HOMEPAGE=	http://sarrazip.com/dev/afternoonstalker.html

# GPLv2+
PERMIT_PACKAGE_CDROM=   Yes

WANTLIB += SDL SDL_image SDL_mixer c flatzebra-0.1 m pthread ${COMPILER_LIBCXX}

MASTER_SITES=	http://sarrazip.com/dev/

LIB_DEPENDS =	devel/flatzebra>=0.1.6
RUN_DEPENDS=	devel/desktop-file-utils

CONFIGURE_STYLE= gnu

.include <bsd.port.mk>
