# $FreeBSD$

PORTNAME=	warp
PORTVERSION=	3.2.13
PORTREVISION=	1
CATEGORIES=	www haskell

MAINTAINER=	haskell@FreeBSD.org
COMMENT=	Fast, light-weight web server for WAI applications

LICENSE=	MIT

USE_CABAL=	auto-update>=0.1.1 blaze-builder>=0.4 case-insensitive>=0.2 \
		hashable http-date http-types>=0.8.5 http2>=1.0.2 \
		iproute>=1.3.1 network>=2.3 old-locale simple-sendfile>=0.2.7 \
		stm>=2.3 streaming-commons>=0.1.10 text unix-compat>=0.2 \
		vault>=0.3 wai>=3.0 word8

FLAGS_ENABLE=	allow-sendfilefd
FLAGS_DISABLE=	network-bytestring warp-debug use-bytestring-builder

.include "${.CURDIR}/../../lang/ghc/bsd.cabal.mk"
.include <bsd.port.mk>
