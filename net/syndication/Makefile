# $FreeBSD$

PORTNAME=	syndication
DISTVERSION=	${KDE_APPLICATIONS_VERSION}
CATEGORIES=	net kde kde-applications

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KDE RSS feed handling library

LICENSE=	LGPL21

USES=		cmake:outsource compiler:c++11-lib gettext kde:5 tar:xz
USE_KDE=	codecs config coreaddons ecm kio service
USE_QT5=	core gui xml \
		buildtools_build qmake_build
USE_LDCONFIG=	yes

DESCR=		${.CURDIR:H:H}/deskutils/kdepim/pkg-descr


.include <bsd.port.mk>
