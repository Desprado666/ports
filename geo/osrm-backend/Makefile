# $OpenBSD: Makefile,v 1.2 2018/07/15 09:39:44 bentley Exp $

COMMENT =		high-performance road network routing engine

GH_ACCOUNT =		Project-OSRM
GH_PROJECT =		osrm-backend
GH_TAGNAME =		v5.18.0
REVISION =		0

CATEGORIES =		geo

HOMEPAGE =		http://project-osrm.org/

# BSD 2-clause
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} ${MODLUA_WANTLIB}
WANTLIB += boost_chrono-mt boost_date_time-mt boost_filesystem-mt
WANTLIB += boost_iostreams-mt boost_program_options-mt boost_regex-mt
WANTLIB += boost_system-mt boost_thread-mt bz2 c expat m tbb tbbmalloc z

MODULES =		devel/cmake \
			lang/lua
MODLUA_VERSION =	5.3
BUILD_DEPENDS =		devel/protozero \
			devel/utfcpp \
			geo/libosmium
LIB_DEPENDS =		archivers/bzip2 \
			devel/boost \
			devel/tbb

CONFIGURE_ARGS =	-DOSMIUM_INCLUDE_DIR=${LOCALBASE}/include/osmium \
			-DCMAKE_CXX_FLAGS="-I${LOCALBASE}/include/utfcpp \
				${CXXFLAGS}"

NO_TEST =		Yes

.include <bsd.port.mk>
