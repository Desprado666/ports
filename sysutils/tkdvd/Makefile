# $OpenBSD: Makefile,v 1.14 2018/06/29 22:16:21 espie Exp $

COMMENT=		GUI to dvd+rw-tools and cdrecord

DISTNAME=		tkdvd-4.0.9
REVISION =		3
CATEGORIES=		sysutils

HOMEPAGE=		http://regis.damongeot.free.fr/tkdvd/

MAINTAINER=		Vlad Glagolev <stealth@sourcemage.org>

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=		${HOMEPAGE:=dl/}

WRKDIST=		${WRKDIR}/tkdvd

MODULES=		x11/tk

BUILD_DEPENDS=		${MODTCL_RUN_DEPENDS}
RUN_DEPENDS=		sysutils/cdrtools \
			sysutils/dvd+rw-tools \
			x11/gtk+3,-guic \
			${MODTK_RUN_DEPENDS}

NO_TEST=		Yes

pre-build:
			${SUBST_CMD} ${WRKSRC}/{install.tcl,TkDVD.sh}

do-build:
	cd ${WRKDIST} && ./install.tcl

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/tkdvd-install.sh ${PREFIX}/bin/tkdvd
	${INSTALL_DATA_DIR} ${PREFIX}/share/icons/hicolor/32x32/apps
	${INSTALL_DATA_DIR} ${PREFIX}/share/icons/hicolor/48x48/apps
	${INSTALL_DATA} ${WRKSRC}/icons/*-32.png ${PREFIX}/share/icons/hicolor/32x32/apps
	${INSTALL_DATA} ${WRKSRC}/icons/*-48.png ${PREFIX}/share/icons/hicolor/48x48/apps
	${INSTALL_DATA_DIR} ${PREFIX}/share/tkdvd
	${INSTALL_DATA} ${WRKSRC}/FAQ ${PREFIX}/share/tkdvd

.include <bsd.port.mk>
