# $FreeBSD$

PORTNAME=	libmysofa
PORTVERSION=	0.6
DISTVERSIONPREFIX=	v
CATEGORIES=	audio

MAINTAINER=	jhale@FreeBSD.org
COMMENT=	SOFA (Spatially Oriented Format for Acoustics) file reader

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

TEST_DEPENDS=	node:www/node

USES=		cmake shebangfix
USE_LDCONFIG=	yes

SHEBANG_FILES=	tests/compare.sh
bash_CMD=	/bin/sh

USE_GITHUB=	yes
GH_ACCOUNT=	hoene

OPTIONS_DEFINE=		TEST
OPTIONS_SUB=		yes

TEST_BUILD_DEPENDS=	cunit>0:devel/cunit
TEST_CMAKE_BOOL=	BUILD_TESTS
TEST_TEST_TARGET=	test

.include <bsd.port.mk>
