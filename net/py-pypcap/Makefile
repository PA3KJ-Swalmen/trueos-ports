# Created by: George V. Neville-Neil
# $FreeBSD$

PORTNAME=	pypcap
DISTVERSION=	1.2.1
CATEGORIES=	net python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Simplified object-oriented Python wrapper for libpcap

LICENSE=	BSD3CLAUSE

USES=		python
USE_PYTHON=	autoplist distutils

post-install:
	${STRIP_CMD} ${STAGEDIR}${PYTHON_SITELIBDIR}/pcap.so

.include <bsd.port.mk>
