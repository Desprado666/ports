# $OpenBSD: Makefile,v 1.13 2018/06/29 22:16:30 espie Exp $

COMMENT =	screen capture program for KDE
DISTNAME =	ksnapshot-${MODKDE4_VERSION}
REVISION =	4

WANTLIB =  c m pthread
WANTLIB += ${COMPILER_LIBCXX}
WANTLIB += ICE SM X11 Xext Xfixes
WANTLIB += lib/qt4/QtDBus lib/qt4/QtGui lib/qt4/QtNetwork
WANTLIB += lib/qt4/QtSvg lib/qt4/QtXml
WANTLIB += ${KDE4LIB}/kdeui ${KDE4LIB}/kio ${KDE4LIB}/kipi

RUN_DEPENDS =	devel/desktop-file-utils \
		x11/gtk+3,-guic

LIB_DEPENDS = 	${MODKDE4_DEP_DIR}/libkipi>=${MODKDE4_DEP_VERSION}

.include <bsd.port.mk>
