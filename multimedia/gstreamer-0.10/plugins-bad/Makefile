# $OpenBSD: Makefile,v 1.101 2018/07/06 06:04:43 espie Exp $

COMMENT-main=		bad elements for GStreamer
COMMENT-neon=		neon element for GStreamer (plugins-bad)
COMMENT-mjpeg=		mplex+mpeg2enc elements for GStreamer (plugins-bad)

V=			0.10.23
DISTNAME=		gst-plugins-bad-${V}
PKGNAME=		gstreamer-plugins-bad-${V}

PKGNAME-main=		gstreamer-plugins-bad-${V}
PKGNAME-neon=		gstreamer-neon-${V}
PKGNAME-mjpeg=		gstreamer-mjpeg-${V}

REVISION-main=		30
REVISION-mjpeg=		13
REVISION-neon=		14

SHARED_LIBS +=  gstphotography-0.10       1.0 # 23.0
SHARED_LIBS +=  gstsignalprocessor-0.10   1.0 # 23.0
SHARED_LIBS +=  gstbasevideo-0.10         1.0 # 23.0
SHARED_LIBS +=  gstbasecamerabinsrc-0.10  0.0 # 23.0
SHARED_LIBS +=  gstcodecparsers-0.10      0.0 # 23.0

MULTI_PACKAGES =	-main -neon -mjpeg

MASTER_SITES =		${MASTER_SITE_GST:=gst-plugins-bad/}

MODULES =		devel/dconf

WANTLIB += glib-2.0 gmodule-2.0 gobject-2.0 gthread-2.0 iconv intl xml2
WANTLIB += lzma pthread z m pcre gstreamer-0.10 ffi

WANTLIB-main += ${WANTLIB}
WANTLIB-main += SDL SoundTouch X11 Xext Xrender
WANTLIB-main += ass bz2 cairo cdaudio croco-0.6 crypto
WANTLIB-main += curl dca dvdnav dvdread expat fontconfig freetype
WANTLIB-main += fribidi gdk_pixbuf-2.0 gio-2.0 gsm gstapp-0.10 gstaudio-0.10
WANTLIB-main += gstbase-0.10 gstcontroller-0.10 gstfft-0.10 gstinterfaces-0.10
WANTLIB-main += gstpbutils-0.10 gstriff-0.10 gstrtp-0.10 gstsdp-0.10
WANTLIB-main += gsttag-0.10 gstvideo-0.10 jasper jpeg lrdf mms
WANTLIB-main += mpcdec nghttp2 opus orc-0.4 pango-1.0 pangocairo-1.0 pangoft2-1.0
WANTLIB-main += pixman-1 png raptor2 rsvg-2
WANTLIB-main += sndfile sndio spandsp ssl ${COMPILER_LIBCXX} tiff usbhid vpx xcb
WANTLIB-main += xcb-render xcb-shm xslt harfbuzz
WANTLIB-main += yajl FLAC graphite2 ogg vorbis vorbisenc

WANTLIB-neon += ${WANTLIB} crypto expat gstbase-0.10 neon proxy ssl

WANTLIB-mjpeg += ${WANTLIB}
WANTLIB-mjpeg += gstbase-0.10 mjpegutils mpeg2encpp mplex2 ${COMPILER_LIBCXX}

BUILD_DEPENDS=		audio/ladspa \
			graphics/libexif
LIB_DEPENDS=		${P}/core
RUN_DEPENDS=		${BUILD_PKGPATH}

LIB_DEPENDS-main=	${LIB_DEPENDS} \
			${P}/plugins-base \
			audio/gsm \
			audio/libcdaudio \
			audio/libdca \
			audio/libsndfile \
			audio/musepack \
			audio/opus \
			audio/soundtouch \
			devel/sdl \
			graphics/jasper \
			multimedia/libass \
			multimedia/libdvdnav \
			multimedia/libmms \
			multimedia/libvpx \
			telephony/spandsp \
			textproc/liblrdf \
			x11/gnome/librsvg
RUN_DEPENDS-main=	${MODDCONF_RUN_DEPENDS}

LIB_DEPENDS-neon=	${LIB_DEPENDS} \
			net/neon

LIB_DEPENDS-mjpeg=	${LIB_DEPENDS} \
			multimedia/mjpegtools

CONFIGURE_ARGS=		--disable-acm \
			--disable-celt \
			--disable-cog \
			--disable-dc1394 \
			--disable-dirac \
			--disable-divx \
			--disable-dvb \
			--disable-dvdspu \
			--disable-faac \
			--disable-faad \
			--disable-fbdev \
			--disable-gme \
			--disable-kate \
			--disable-lv2 \
			--disable-mimic \
			--disable-modplug \
			--disable-musicbrainz \
			--disable-mythtv \
			--disable-nas \
			--disable-ofa \
			--disable-openal \
			--disable-opencv \
			--disable-quicktime \
			--disable-real \
			--disable-rtmp \
			--disable-schro \
			--disable-spc \
			--disable-vcd \
			--disable-vdpau \
			--disable-wildmidi \
			--disable-wininet \
			--disable-xvid \
			--disable-zbar \
			--disable-timidity \
			--disable-swfdec

# http://scarybeastsecurity.blogspot.it/2016/11/0day-exploit-compromising-linux-desktop.html
# https://bugs.launchpad.net/ubuntu/+source/gst-plugins-bad0.10/+bug/1641700
CONFIGURE_ARGS+=	--disable-nsf

preconfigure:
	perl -pi -e 's,/dev/dvd,/dev/rcd0c,g' \
		${WRKSRC}/ext/resindvd/resindvdbin.c \
		${WRKSRC}/ext/resindvd/resindvdsrc.c
	perl -pi -e 's,/dev/cdrom,/dev/rcd0c,g' \
		${WRKSRC}/ext/cdaudio/gstcdaudio.c \
		${WRKSRC}/sys/vcd/vcdsrc.c

.include <bsd.port.mk>
