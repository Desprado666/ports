# $OpenBSD: Makefile,v 1.63 2018/05/09 09:39:05 sthen Exp $

COMMENT-main=		modular authoritative nameserver (with database support)
COMMENT-mysql=		MySQL database access module for PowerDNS
COMMENT-pgsql=		PostgreSQL database access module for PowerDNS

V=			4.1.2
DISTNAME=		pdns-${V}
EXTRACT_SUFX =		.tar.bz2
PKGNAME-main=		powerdns-${V}
PKGSPEC-main=		powerdns-=${V}
PKGNAME-mysql=		powerdns-mysql-${V}
PKGNAME-pgsql=		powerdns-pgsql-${V}

CATEGORIES=		net

HOMEPAGE=		http://www.powerdns.com/

MULTI_PACKAGES=		-main -mysql -pgsql

# GPLv2 only, OpenSSL exemption
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += m pthread ${COMPILER_LIBCXX}

WANTLIB-main += ${WANTLIB}
WANTLIB-main += boost_program_options-mt c crypto sodium sqlite3

MASTER_SITES=		https://downloads.powerdns.com/releases/

COMPILER =		base-clang ports-gcc

NO_TEST=		Yes

LIB_DEPENDS-main=	${LIB_DEPENDS} \
			databases/sqlite3 \
			devel/boost \
			security/libsodium

PSEUDO_FLAVORS+=	no_mysql no_pgsql
FLAVOR?=

BACKENDS=		gsqlite3

SYSCONFDIR=		${BASESYSCONFDIR}/pdns

CONFIGURE_STYLE=	gnu
CONFIGURE_ARGS+=	--disable-shared \
			--with-modules="bind" \
			--with-sqlite3 \
			--with-dynmodules="${BACKENDS}" \
			--without-lua \
			--disable-hardening \
			--without-protobuf \
			--enable-tools
CONFIGURE_ARGS+=	--without-ldap

CONFIGURE_ENV+=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"
LIBTOOL_FLAGS=		--tag=disable-static

.include <bsd.port.arch.mk>

# MySQL
.if ${BUILD_PACKAGES:M-mysql}
CONFIGURE_ARGS+=	--with-mysql=${LOCALBASE}
BACKENDS+=		gmysql
.else
CONFIGURE_ARGS+=	--without-mysql
.endif
LIB_DEPENDS-mysql=	${LIB_DEPENDS} \
			databases/mariadb
RUN_DEPENDS-mysql=	net/powerdns
WANTLIB-mysql+=		${WANTLIB} crypto lib/mysql/mysqlclient ssl z

# PostgreSQL
.if ${BUILD_PACKAGES:M-pgsql}
CONFIGURE_ARGS+=	--with-pgsql=${LOCALBASE} \
			--with-pgsql-includes=${LOCALBASE}/include/postgresql
BACKENDS+=		gpgsql
.else
CONFIGURE_ARGS+=	--without-pgsql
.endif
LIB_DEPENDS-pgsql=	${LIB_DEPENDS} \
			databases/postgresql,-main
RUN_DEPENDS-pgsql=	net/powerdns
WANTLIB-pgsql=		${WANTLIB} crypto pq>=2 ssl

EXAMPLE_DIR=		${PREFIX}/share/examples/pdns/

post-install:
	rm -f ${PREFIX}/lib/pdns/*.la
	${INSTALL_DATA_DIR} ${EXAMPLE_DIR}
	cat ${FILESDIR}/pdns.conf ${WRKSRC}/pdns/pdns.conf-dist > \
	    ${WRKSRC}/pdns.conf # concatenate local and upstream sample configs
	${INSTALL_DATA} ${WRKSRC}/pdns.conf ${EXAMPLE_DIR}

.include <bsd.port.mk>
