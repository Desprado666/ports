# $OpenBSD: Makefile,v 1.13 2018/04/25 13:28:16 jasper Exp $

# XXX: Check _cffi__ hashes of dependent ports if updating.
# e.g. devel/libgit2/py-git2

COMMENT=		Foreign Function Interface for Python calling C code

MODPY_EGG_VERSION=	1.11.5
DISTNAME=		cffi-${MODPY_EGG_VERSION}
PKGNAME=		py-${DISTNAME}
CATEGORIES=		devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODPY_PI =		Yes

WANTLIB=		ffi pthread ${MODPY_WANTLIB}

MODULES=		lang/python
FLAVORS=		python3
FLAVOR?=

MODPY_SETUPTOOLS=	Yes

LIB_DEPENDS=		devel/libffi
RUN_DEPENDS=		devel/py-cparser${MODPY_FLAVOR}
TEST_DEPENDS=		${RUN_DEPENDS} \
			devel/py-py${MODPY_FLAVOR} \
			devel/py-test${MODPY_FLAVOR}

.include <bsd.port.mk>
