# $OpenBSD: Makefile,v 1.3 2018/04/07 12:50:58 pvk Exp $

COMMENT =		versioning library for Python projects

MODPY_EGG_VERSION =	17.5.0

DISTNAME =		incremental-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}

CATEGORIES =		devel

# MIT
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/python
MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes

TEST_DEPENDS =		devel/py-click${MODPY_FLAVOR} \
			devel/py-test${MODPY_FLAVOR} \
			devel/py-twisted${MODPY_FLAVOR}

FLAVORS =		python3
FLAVOR ?=

TEST_ENV =		LC_CTYPE=en_US.UTF-8

do-test:
	cd ${WRKSRC}/src/incremental && ${SETENV} ${TEST_ENV} ${MODPY_BIN} -m pytest

.include <bsd.port.mk>
