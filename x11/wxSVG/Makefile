# $OpenBSD: Makefile,v 1.43 2018/04/26 21:03:29 ajacoutot Exp $

COMMENT=		C++ library to create, manipulate and render SVG files

DISTNAME=		wxsvg-1.5.13
EPOCH=			0
CATEGORIES=		x11 graphics
MASTER_SITES=		${MASTER_SITE_SOURCEFORGE:=wxsvg/}
EXTRACT_SUFX=		.tar.bz2

SHARED_LIBS+=		wxsvg	3.3

HOMEPAGE=		http://wxsvg.sourceforge.net/

# Modified LGPL
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += ${COMPILER_LIBCXX} ICE SDL SM X11 Xcomposite Xcursor
WANTLIB += Xdamage Xext Xfixes Xi Xinerama Xrandr Xrender Xxf86vm
WANTLIB += atk-1.0 avcodec avformat avutil bz2 c cairo crypto
WANTLIB += exif expat ffi fontconfig freetype gdk-x11-2.0 gdk_pixbuf-2.0
WANTLIB += gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0 graphite2
WANTLIB += gsm gthread-2.0 gtk-x11-2.0 harfbuzz iconv intl iodbc
WANTLIB += jpeg m mp3lame mspack ogg opus pango-1.0 pangocairo-1.0
WANTLIB += pangoft2-1.0 pcre pixman-1 png pthread fribidi
WANTLIB += sndio speex ssl swresample swscale tiff usbhid vorbis
WANTLIB += vorbisenc vpx wx_base wx_base_net wx_base_odbc wx_base_xml
WANTLIB += wx_gtk2_adv wx_gtk2_aui wx_gtk2_core wx_gtk2_dbgrid
WANTLIB += wx_gtk2_html wx_gtk2_qa wx_gtk2_richtext wx_gtk2_xrc
WANTLIB += x264 x265 xcb xcb-render xcb-shm xvidcore z

# comes from multimedia/libvpx using lang/clang MODULE on i386|amd64 only
# which includes gcc4 MODULE with adds gcc-libs in dependency scope
.if ${MACHINE_ARCH:Mi386} || ${MACHINE_ARCH:Mamd64}
WANTLIB += $(LIBECXX)
.endif

LIB_DEPENDS=		graphics/cairo \
			graphics/ffmpeg \
			graphics/libexif \
			x11/wxWidgets

CONFIGURE_STYLE=	gnu

NO_TEST=		Yes

.include <bsd.port.mk>
