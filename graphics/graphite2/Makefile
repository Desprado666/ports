# $OpenBSD: Makefile,v 1.21 2018/08/16 05:31:19 ajacoutot Exp $

COMMENT=	rendering for complex writing systems

DISTNAME=	graphite2-1.3.12
EXTRACT_SUFX=	.tgz

SHARED_LIBS=	graphite2 2.0 # 3.0.1

CATEGORIES=	graphics

HOMEPAGE=	http://scripts.sil.org/cms/scripts/page.php?site_id=projects&item_id=graphite_home

MAINTAINER=	Antoine Jacoutot <ajacoutot@openbsd.org>

# LGPLv2.1
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += c m ${COMPILER_LIBCXX}

MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=silgraphite/}

MODULES=	devel/cmake \
		lang/python

# c++11
COMPILER=	base-clang ports-gcc

MODPY_BUILDDEP=	No
MODPY_RUNDEP=	No

TEST_DEPENDS=${MODPY_RUN_DEPENDS}

# XXX push upstream: collides with swap32(3)
pre-configure:
	sed -i 's,swap32,gr_swap32,g' ${WRKSRC}/tests/comparerenderer/FeatureParser.h

# regress tests need python
pre-test:
	ln -sf ${MODPY_BIN} ${WRKDIR}/bin/python

.include <bsd.port.mk>
