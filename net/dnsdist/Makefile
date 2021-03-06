# $OpenBSD: Makefile,v 1.12 2018/05/09 21:22:42 sthen Exp $

COMMENT=		highly DNS-, DoS- and abuse-aware loadbalancer

DISTNAME=		dnsdist-1.3.0
REVISION=		0
EXTRACT_SUFX=		.tar.bz2

CATEGORIES=		net

HOMEPAGE=		https://dnsdist.org/

MAINTAINER=		Peter van Dijk <peter.van.dijk@powerdns.com>

# GPLv2 only
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += 		${MODLUA_WANTLIB} c curses edit m protobuf pthread \
			z crypto ssl sodium ${COMPILER_LIBCXX}

MASTER_SITES=		https://downloads.powerdns.com/releases/

CONFIGURE_STYLE=	autoconf
AUTOCONF_VERSION=	2.69
USE_GMAKE=		Yes

CONFIGURE_ARGS+=	--disable-gnutls \
			--disable-hardening \
			--with-lua \
			--without-net-snmp \
			--enable-dns-over-tls \
			--enable-dnscrypt
CONFIGURE_ENV+=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib" \
			LIBEDIT_LIBS='-ledit -lcurses' \
			LIBEDIT_CFLAGS=' '
SYSCONFDIR=		${BASESYSCONFDIR}/dnsdist

COMPILER =		base-clang ports-gcc

MODULES+=		lang/lua
MODLUA_VERSION=		5.3

BUILD_DEPENDS=		devel/boost
LIB_DEPENDS+=		${MODLUA_LIB_DEPENDS} \
			security/libsodium \
			devel/protobuf

.if ${MACHINE_ARCH:Mi386}
# needs 64-bit atomics
CFLAGS+=		-march=i586
CXXFLAGS+=		-march=i586
.endif

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/{doc,examples}/dnsdist
	cd ${WRKSRC}; ${INSTALL_DATA} README.md ${PREFIX}/share/doc/dnsdist/; \
	    ${INSTALL_DATA} dnsdistconf.lua ${PREFIX}/share/examples/dnsdist/

.include <bsd.port.mk>
