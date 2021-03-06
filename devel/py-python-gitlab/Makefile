# $FreeBSD$

PORTNAME=	python-gitlab
PORTVERSION=	1.3.0
CATEGORIES=	devel python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	dereks@lifeofadishwasher.com
COMMENT=	Interact with GitLab API

LICENSE=	LGPL3
LICENSE_FILE=	${WRKSRC}/COPYING

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}requests>=2.4.2:www/py-requests@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}six>0:devel/py-six@${FLAVOR}
TEST_DEPENDS=	${PYTHON_PKGNAMEPREFIX}httmock>0:www/py-httmock@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}mock>0:devel/py-mock@${FLAVOR}

OPTIONS_DEFINE=	DOCS

DOCS_BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}sphinx>0:textproc/py-sphinx@${FLAVOR}
DOCS_PORTDOCS=	*
DOCS_VARS=	PYDISTUTILS_BUILD_TARGET=build_sphinx \
		PYDISTUTILS_BUILDARGS="-n --all-files --fresh-env"

NO_ARCH=	yes
USES=		python
USE_PYTHON=	distutils autoplist concurrent

SUB_FILES=	pkg-message

do-test:

post-patch:
	@${REINPLACE_CMD} -e 's|/etc|${LOCALBASE}/etc|g' ${WRKSRC}/gitlab/config.py

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	(cd ${WRKSRC}/build/sphinx/html && \
	${COPYTREE_SHARE} . ${STAGEDIR}${DOCSDIR} "! -name .buildinfo -and ! -name objects.inv")

do-test:
	cd ${WRKSRC} && ${PYTHON_CMD} ${PYDISTUTILS_SETUP} test

.include <bsd.port.mk>
