# Created by: Alexander Pyhalov <alp@sfedu.ru>
# $FreeBSD$

PORTNAME=	pg_reorg
PORTVERSION=	1.1.11
CATEGORIES=	databases
MASTER_SITES=	http://pgfoundry.org/frs/download.php/3821/ \
		http://BSDforge.com/projects/source/databases/pg_reorg/

MAINTAINER=	portmaster@BSDforge.com
COMMENT=	PostgreSQL utility to reorganize tables

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/COPYRIGHT

MAKE_ENV=	USE_PGXS=0
USES=		gmake pgsql uidfix
LLD_UNSAFE=	yes
WANT_PGSQL_VER=	91+
WANT_PGSQL=	server
INSTALL_TARGET=	install-strip
PORTDOCS=	*

OPTIONS_DEFINE=	DOCS

post-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	(cd ${WRKSRC}/doc && ${COPYTREE_SHARE} . ${STAGEDIR}${DOCSDIR})

.include <bsd.port.mk>
