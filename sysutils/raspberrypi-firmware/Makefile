#	$OpenBSD: Makefile,v 1.11 2018/08/11 12:52:33 jsg Exp $

COMMENT=	Raspberry Pi firmware
GH_ACCOUNT=	raspberrypi
GH_PROJECT=	firmware
V=		1.20180810
GH_COMMIT=	953a33962f0e3a33f7627248f47b8378cb40e6e4
#DISTNAME=	${GH_ACCOUNT}-${GH_PROJECT}-${GH_TAGNAME}
DISTNAME=	${GH_ACCOUNT}-${GH_PROJECT}-${V}

CATEGORIES=	sysutils

# Broadcom/Raspberry Pi license
# allows redistrubtion of binary files
# only allows them to be used in relation to Raspberry Pi
PERMIT_PACKAGE_CDROM=	No
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

PKG_ARCH=		*

NO_BUILD=		Yes
NO_TEST=		Yes

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/raspberrypi-firmware/
	cp -r ${WRKSRC}/boot/ ${PREFIX}/share/raspberrypi-firmware/boot/

.include <bsd.port.mk>
