# $OpenBSD: Makefile,v 1.17 2018/05/12 10:00:24 espie Exp $

COMMENT=	Commodore 64 music player and SID chip emulator

DISTNAME=	sidplay-base-1.0.9
PKGNAME=	${DISTNAME:S/-base//}
REVISION =	4
CATEGORIES=	audio

MAINTAINER=	Christian Weisgerber <naddy@openbsd.org>

# GPL
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=		c m sidplay>=1 sndio ${COMPILER_LIBCXX}

MASTER_SITES=	https://www.distfiles.pl/
EXTRACT_SUFX=	.tgz

LIB_DEPENDS=	audio/libsidplay

CONFIGURE_STYLE= gnu
CONFIGURE_ARGS=	--with-sidplay-includes=${LOCALBASE}/include \
		--with-sidplay-library=${LOCALBASE}/lib

post-extract:
	@mkdir -p ${WRKSRC}/audio/sndio
	@cp ${FILESDIR}/audiodrv.cpp ${WRKSRC}/audio/sndio
	@cp ${FILESDIR}/audiodrv.h ${WRKSRC}/audio/sndio

.include <bsd.port.mk>
