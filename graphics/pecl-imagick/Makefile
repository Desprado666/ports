# $OpenBSD: Makefile,v 1.34 2018/04/26 15:08:56 sthen Exp $

COMMENT=	PHP support for the ImageMagick library

DISTNAME=	imagick-3.4.3
CATEGORIES=	graphics
REVISION=	1

# PHP
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += ICE MagickCore-6.Q16 MagickWand-6.Q16 SM X11 Xext Xt
WANTLIB += bz2 c djvulibre expat fftw3 fontconfig freetype iconv jbig
WANTLIB += jpeg lcms2 lzma m openjp2 png pthread
WANTLIB += tiff webp xcb xml2 z

MODULES=	lang/php/pecl
CONFIGURE_STYLE= gnu

LIB_DEPENDS=	converters/libiconv \
		graphics/ImageMagick

.include <bsd.port.mk>
