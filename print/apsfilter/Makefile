# $OpenBSD: Makefile,v 1.19 2017/05/11 20:50:55 espie Exp $

COMMENT=		filter to print a wide range of file formats

DISTNAME=		apsfilter-7.2.8
REVISION=		5
CATEGORIES=		print

HOMEPAGE=		http://www.apsfilter.org/

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=		http://www.apsfilter.org/download/

CONFIGURE_STYLE=	simple
CONFIGURE_ARGS+=	--prefix='${PREFIX}' \
			--sysconfdir='${SYSCONFDIR}' \
			--with-shell=/bin/sh \
			--with-awk=/usr/bin/awk

RUN_DEPENDS=		print/a2ps

WRKDIST=		${WRKDIR}/apsfilter

NO_TEST=		Yes

.include <bsd.port.mk>
