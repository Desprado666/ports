# $OpenBSD: Makefile,v 1.20 2017/06/16 14:03:46 sthen Exp $

COMMENT=	SMTP support for PHP

DISTNAME=	Net_SMTP-1.8.0
CATEGORIES=	net

MODULES=	www/pear

MAINTAINER=	Stuart Henderson <sthen@openbsd.org>

# PHP License
PERMIT_PACKAGE_CDROM=	Yes

RUN_DEPENDS=	net/pear-Net-Socket>=1.0.7 \
		security/pear-Auth-SASL

MODULES+=	 lang/php # MODPHP_BIN, for tests
MODPHP_BUILDDEP= No
MODPHP_RUNDEP=	 No
TEST_DEPENDS=	 ${BASE_PKGPATH}
do-test:
	cd ${WRKSRC}/tests; pear -d php_bin=${MODPHP_BIN} run-tests

.include <bsd.port.mk>
