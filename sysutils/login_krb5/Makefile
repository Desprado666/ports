# $OpenBSD: Makefile,v 1.17 2018/06/14 06:58:10 ajacoutot Exp $

COMMENT=		authentication provider for KerberosV

GIT_PROJECT=		login_krb5
GIT_COMMIT=		f31110a

DISTNAME=		${GIT_COMMIT}
PKGNAME=		${GIT_PROJECT}-6.3

DIST_SUBDIR=		${GIT_PROJECT}
WRKDIST=		${WRKDIR}/${GIT_PROJECT}-${GIT_COMMIT}

CATEGORIES=		sysutils security

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

HOMEPAGE=		http://repo.or.cz/login_krb5.git

# ISC
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += c

MASTER_SITES=		http://repo.or.cz/login_krb5.git/snapshot/

MODULES=		security/heimdal

NO_TEST=		Yes

FAKE_FLAGS=		BINDIR=${PREFIX}/libexec/auth \
			MANDIR=${PREFIX}/man/man

.include <bsd.port.mk>
