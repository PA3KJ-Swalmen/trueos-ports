# $FreeBSD$

PORTNAME=	trueos-utils-qt5
PORTVERSION=	201803051002
CATEGORIES=	sysutils

MAINTAINER=	jt@ixsystems.com
COMMENT=	TrueOS QT5 Utilities

LICENSE=	BSD2CLAUSE

RUN_DEPENDS=	setxkbmap:x11/setxkbmap \
		xdpyinfo:x11/xdpyinfo \
		xwd:x11/xwd \
		xcursor-themes>=0:x11-themes/xcursor-themes
LIB_DEPENDS=	libtrueos-ui.so:sysutils/trueos-libqt5

WRKSRC_SUBDIR=  src-qt5
MAKE_ARGS=      PREFIX=${STAGEDIR}${PREFIX}

CONFLICTS=      pcbsd-utils-[0-9]*

MAKE_JOBS_UNSAFE=yes
ONLY_FOR_ARCHS= amd64
USE_LDCONFIG=   yes
USE_QT5=        core gui network svg linguist_build \
		buildtools_build x11extras widgets multimedia
USES=           qmake shebangfix tar:xz
USE_GL+=	gl

WRKSRC_SUBDIR=  src-qt5

QMAKE_ARGS=     CONFIG+="configure"

USE_GITHUB=	yes
GH_ACCOUNT=	trueos
GH_PROJECT=	trueos-utils-qt5
GH_TAGNAME=	269b05a54038145b77df910ca1a7de108d168d30

.include <bsd.port.mk>
