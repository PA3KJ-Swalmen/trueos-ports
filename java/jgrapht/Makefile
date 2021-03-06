# Created by: ijliao
# $FreeBSD$

PORTNAME=	jgrapht
PORTVERSION=	0.7.3
PORTREVISION=	1
CATEGORIES=	java math
MASTER_SITES=	SF/${PORTNAME}/JGraphT/Version%20${PORTVERSION}

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Java package for mathematical graph-theory objects and algorithms

BROKEN=		fails to build

USES=		dos2unix zip
DOS2UNIX_GLOB=	*.xml *.java
USE_JAVA=	yes
JAVA_VERSION=	1.6 1.7

OPTIONS_DEFINE=	DOCS

.include <bsd.port.options.mk>

.if !defined(WITHOUT_COMPILE)
USE_ANT=	yes
ALL_TARGET=	jar
.if ${PORT_OPTIONS:MDOCS}
ALL_TARGET+=	javadoc
.endif
.else
NO_BUILD=	yes
.endif

PORTDOCS=	*

PLIST_FILES=	${JAVAJARDIR}/${PORTNAME}.jar

.include <bsd.port.pre.mk>

JAVA_PORT_API=	${LOCALBASE}/share/doc/jdk${JAVA_PORT_VERSION:C/([0-9]\.[0-9])\.[0-9]/\1/}/api
.if exists(${JAVA_PORT_API})
MAKE_ARGS+=	-Djdk.api="${JAVA_PORT_API}"
.endif

pre-fetch:
	@${ECHO_MSG} ""
	@${ECHO_MSG} "You may use the following build options:"
	@${ECHO_MSG} ""
	@${ECHO_MSG} "    WITHOUT_COMPILE=yes    Install the pre-compiled .jar file"
	@${ECHO_MSG} ""

do-install:
	@${ECHO_MSG} -n  ">> Installing JAR as ${JAVAJARDIR}/${PORTNAME}.jar..."
	@${INSTALL_DATA} ${WRKSRC}/${PORTNAME}-jdk1.5.jar ${STAGEDIR}${JAVAJARDIR}/${PORTNAME}.jar
	@${ECHO_MSG} " [DONE]"
.if ${PORT_OPTIONS:MDOCS}
	@${ECHO_MSG} -n ">> Installing documentation in ${DOCSDIR}..."
	@cd ${WRKSRC}/javadoc && ${FIND} . -type d -exec ${MKDIR} ${STAGEDIR}${DOCSDIR}/{} \;
	@cd ${WRKSRC}/javadoc && ${FIND} . -type f -exec ${INSTALL_DATA} {} ${STAGEDIR}${DOCSDIR}/{} \;
	@${ECHO_MSG} " [DONE]"
.endif

.include <bsd.port.post.mk>
