# $OpenBSD: Makefile,v 1.6 2018/01/11 19:27:09 rpe Exp $

COMMENT =	lightweight shipper for hw.sensors data

BEAT =		hwsensorsbeat
VERSION =	0.1.2
REVISION =	4

GH_ACCOUNT =	jasperla
GH_PROJECT =	${BEAT}
GH_TAGNAME =	${VERSION}

ELASTIC_BEAT =	No

WANTLIB =	c pthread

CONFIGS =	hwsensorsbeat.yml hwsensorsbeat.template.json

.include <bsd.port.mk>
