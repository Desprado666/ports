# $OpenBSD: Makefile,v 1.37 2018/07/01 18:33:36 espie Exp $

ONLY_FOR_ARCHS=	${GCC4_ARCHS} ${CLANG_ARCHS}

COMMENT=	photorealistic 3D rendering solution

V=		1.8.2
DISTNAME=	aqsis-${V}
REVISION=	8
CATEGORIES=	graphics

SO_VERSION=	1.0 # 1.6
.for _lib in aqsis_core aqsis_math aqsis_ri2rib aqsis_riutil \
aqsis_shadervm aqsis_slcomp aqsis_slxargs aqsis_tex aqsis_util
SHARED_LIBS+=	${_lib} ${SO_VERSION}
.endfor

HOMEPAGE=	http://www.aqsis.org/

# GPLv2 - LGPLv2
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=aqsis/}

WANTLIB += GL Half Iex IlmImf IlmThread Imath boost_filesystem-mt
WANTLIB += boost_iostreams-mt boost_program_options-mt boost_regex-mt
WANTLIB += boost_system-mt boost_thread-mt boost_wave-mt c
WANTLIB += lib/qt4/QtCore lib/qt4/QtGui lib/qt4/QtOpenGL
WANTLIB += m png pthread ${COMPILER_LIBCXX} tiff tiffxx z

MODULES=	devel/cmake

RUN_DEPENDS=	devel/desktop-file-utils \
		misc/shared-mime-info \
		x11/gtk+3,-guic
BUILD_DEPENDS=	textproc/libxslt \
		devel/bison
LIB_DEPENDS=	devel/boost \
		graphics/tiff \
		graphics/openexr \
		x11/qt4

NO_TEST=	Yes
MODCMAKE_WANTCOLOR=No
SEPARATE_BUILD=	Yes

CXXFLAGS+=	-pthread -I${X11BASE}/include
.include <bsd.port.arch.mk>
.if ${PROPERTIES:Mclang}
CXXFLAGS+=	-std=gnu++11
.endif

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/aqsis
	${INSTALL_DATA} ${WRKBUILD}/aqsisrc \
		${PREFIX}/share/examples/aqsis/

.include <bsd.port.mk>
