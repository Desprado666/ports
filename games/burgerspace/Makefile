# $OpenBSD: Makefile,v 1.33 2018/06/27 21:03:44 espie Exp $

COMMENT=	burgertime clone for X

DISTNAME =	burgerspace-1.9.2
REVISION =	1

CATEGORIES=	games

HOMEPAGE=	http://sarrazip.com/dev/burgerspace.html

# GPLv2+
PERMIT_PACKAGE_CDROM=   Yes

WANTLIB += FLAC SDL SDL_image SDL_mixer c flatzebra-0.1
WANTLIB += iconv jpeg m mikmod ogg png pthread smpeg sndio ${COMPILER_LIBCXX} tiff
WANTLIB += usbhid vorbis vorbisfile z webp

MASTER_SITES=	http://sarrazip.com/dev/

LIB_DEPENDS=	converters/libiconv \
		devel/flatzebra>=0.1.6
RUN_DEPENDS=	devel/desktop-file-utils

CONFIGURE_STYLE= gnu

.include <bsd.port.mk>
