# $OpenBSD: Makefile,v 1.1.1.1 2018/01/17 20:18:53 bcallah Exp $

COMMENT =	chess database software
DISTNAME =	scid-4.6.4
EXTRACT_SUFX =	.zip
CATEGORIES =	games x11

HOMEPAGE =	http://scid.sourceforge.net/
MAINTAINER =	Brian Callahan <bcallah@openbsd.org>

# GPLv3+
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} ${MODTCL_WANTLIB} c m z

MASTER_SITES =	${MASTER_SITE_SOURCEFORGE:=scid/}

# C++11
COMPILER =	base-clang ports-gcc ports-clang

MODULES =	lang/python \
		x11/tk
MODTK_VERSION =	8.6
MODPY_ADJ_FILES =	scripts/pgnfix.py

LIB_DEPENDS =	${MODTCL_LIB_DEPENDS}

RUN_DEPENDS =	${MODTK_RUN_DEPENDS}

CONFIGURE_STYLE =	simple

USE_GMAKE =	Yes
MAKE_FLAGS =	CXX="${CXX}"

TEST_DEPENDS =	devel/cmake \
		devel/gtest

pre-configure:
	@${MODTCL_TCLSH_ADJ} ${WRKSRC}/configure
	sed -i -e 's,$${CXX},${CXX},g' -e 's,$${CXXFLAGS},${CXXFLAGS},g' -e \
		's,$${LOCALBASE},${LOCALBASE},g' ${WRKSRC}/configure
	sed -i 's,$${CXXFLAGS},${CXXFLAGS},g' \
		${WRKSRC}/engines/togaII1.2.1a/src/Makefile

post-configure:
	@${MODTCL_TCLSH_ADJ} ${WRKSRC}/scripts/spf2spi.tcl
	@${MODTCL_TCLSH_ADJ} ${WRKSRC}/tcl/contrib/ezsmtp/install.tcl
	@${MODTCL_TCLSH_ADJ} ${WRKSRC}/tcl/lang/checklangs.tcl
	@${MODTCL_TCLSH_ADJ} ${WRKSRC}/tcl/lang/propagatelang.tcl
	@${MODTCL_TCLSH_ADJ} ${WRKSRC}/tcl/lang/removetoken.tcl

.include <bsd.port.mk>
