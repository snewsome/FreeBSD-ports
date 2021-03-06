# Created by: Gea-Suan Lin <gslin@gslin.org>
# $FreeBSD$

PORTNAME=	s3fs
DISTVERSIONPREFIX=	v
DISTVERSION=	1.83
CATEGORIES=	sysutils
PKGNAMEPREFIX=	fusefs-

PATCH_SITES=	https://github.com/${GH_ACCOUNT}/${GH_PROJECT}/commit/ # https://github.com/s3fs-fuse/s3fs-fuse/pull/729
PATCHFILES=	c9f431258886bdcb9941a16c27c6e231414687c1.patch:-p1

MAINTAINER=	dg@syrec.org
COMMENT=	FUSE-based file system backed by Amazon S3

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libcurl.so:ftp/curl

USES=		autoreconf fuse pkgconfig ssl
GNU_CONFIGURE=	yes
USE_GITHUB=	yes
GH_ACCOUNT=	s3fs-fuse
GH_PROJECT=	s3fs-fuse
USE_GNOME=	libxml2

PLIST_FILES=	bin/s3fs man/man1/s3fs.1.gz

post-patch:
	@${REINPLACE_CMD} -e 's/libcrypto >= 0.9//' ${WRKSRC}/configure.ac
	@${REINPLACE_CMD} -e '/DEPS_LIBS/s/$$/ -lcrypto/' \
		${WRKSRC}/src/Makefile.am

.include <bsd.port.mk>
