# $OpenBSD: Makefile,v 1.22 2018/01/22 21:50:23 kili Exp $

COMMENT =		Haskell implementation of the D-Bus protocol

DISTNAME =		dbus-0.10.13
REVISION =		1
CATEGORIES =		devel x11

HOMEPAGE =		https://github.com/rblaze/haskell-dbus#readme

MAINTAINER =		David Coppa <dcoppa@openbsd.org>

# GPLv3
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/ghc

MODGHC_BUILD =		cabal hackage haddock register

MODGHC_PACKAGE_KEY =	IUelLsOGWpyBGcXH63C8d4

RUN_DEPENDS =		devel/hs-cereal \
			devel/hs-network \
			devel/hs-parsec \
			devel/hs-random \
			devel/hs-text \
			devel/hs-vector \
			textproc/hs-libxml-sax \
			textproc/hs-xml-types
BUILD_DEPENDS =		${RUN_DEPENDS}

.include <bsd.port.mk>
