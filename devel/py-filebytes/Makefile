# $OpenBSD: Makefile,v 1.2 2018/06/18 09:11:56 rpointel Exp $

COMMENT =	python module to read and write ELF, PE, MachO or OAT

MODPY_EGG_VERSION =	0.9.16
DISTNAME =	filebytes-${MODPY_EGG_VERSION}
PKGNAME =	py-${DISTNAME}

CATEGORIES =	devel security

HOMEPAGE =	https://scoding.de/filebytes-introduction

MAINTAINER =	Remi Pointel <rpointel@openbsd.org>

# GPLv2
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/python
MODPY_SETUPTOOLS =	Yes
MODPY_PI =		Yes

FLAVORS =	python3
FLAVOR ?=

.include <bsd.port.mk>
