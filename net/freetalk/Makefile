# $OpenBSD: Makefile,v 1.19 2017/11/21 00:13:02 naddy Exp $

COMMENT=	console based Jabber client

DISTNAME=	freetalk-3.2
REVISION=	4

CATEGORIES=	net

HOMEPAGE=	https://www.gnu.org/software/freetalk/

# GPLv3
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=	c glib-2.0 gmp iconv idn intl ltdl m ncurses pthread \
		readline ${COMPILER_LIBCXX} guile loudmouth-1>=3

MASTER_SITES=	${MASTER_SITE_SAVANNAH:=freetalk/}

LIB_DEPENDS=	lang/guile \
		net/loudmouth

AUTOCONF_VERSION=	2.61
CONFIGURE_STYLE= autoconf no-autoheader
CONFIGURE_ENV=	LDFLAGS="-L${LOCALBASE}/lib" \
		CPPFLAGS="-I${LOCALBASE}/include"

FAKE_FLAGS=	Examplesdir=${PREFIX}/share/examples/freetalk/

.include <bsd.port.mk>
