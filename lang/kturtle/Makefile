# $FreeBSD$

PORTNAME=	kturtle
DISTVERSION=	${KDE_APPLICATIONS_VERSION}
CATEGORIES=	lang kde kde-applications

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Educational programming environment for KDE

USES=		cmake:outsource gettext kde:5 tar:xz
USE_KDE=	attica auth codecs config configwidgets coreaddons crash ecm \
		emoticons i18n init itemmodels kdelibs4support kio newstuff \
		service sonnet textwidgets widgetsaddons xmlgui
USE_QT5=	core dbus gui network printsupport svg widgets xml \
		buildtools_build qmake_build

.include <bsd.port.mk>
