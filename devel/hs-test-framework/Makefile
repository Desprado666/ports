# $OpenBSD: Makefile,v 1.13 2018/01/22 21:43:45 kili Exp $

COMMENT =		framework for running and organising tests

DISTNAME =		test-framework-0.8.1.1
REVISION =		3
CATEGORIES =		devel

HOMEPAGE =		http://batterseapower.github.com/test-framework/

MAINTAINER =		Matthias Kilian <kili@openbsd.org>

# BSD3
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/ghc

MODGHC_BUILD =		cabal hackage haddock register

MODGHC_PACKAGE_KEY =	KakqBuIUYoUBZBqwCIlO84

BUILD_DEPENDS =		${RUN_DEPENDS}
RUN_DEPENDS =		net/hs-hostname>=1.0 \
			textproc/hs-xml>=1.3.5 \
			devel/hs-ansi-terminal>=0.4.0 \
			devel/hs-ansi-wl-pprint>=0.5.1 \
			devel/hs-extensible-exceptions>=0.1.1 \
			devel/hs-old-locale>=1.0 \
			devel/hs-random>=1.0,<2 \
			devel/hs-regex-posix>=0.72

.include <bsd.port.mk>
