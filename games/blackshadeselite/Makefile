# Created by: Dmitry Marakasov <amdmi3@amdmi3.ru>
# $FreeBSD$

PORTNAME=	blackshadeselite
PORTVERSION=	0.0.1
PORTREVISION=	10
CATEGORIES=	games
MASTER_SITES=	http://download.gna.org/blackshadeselite/ \
		http://mirror.amdmi3.ru/distfiles/

MAINTAINER=	amdmi3@FreeBSD.org
COMMENT=	Psychic Bodyguard FPS - protect the VIP

LICENSE=	GPLv2+
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libvorbis.so:audio/libvorbis

USES=		tar:bzip2 gmake openal:al,alut
USE_SDL=	sdl
USE_GL=		gl glu

MAKE_ARGS=	CC="${CC}" CXX="${CXX}"

CXXFLAGS+=	-Wno-c++11-narrowing

WRKSRC=		${WRKDIR}/${PORTNAME}

PLIST_FILES=	bin/blackshades
PORTDOCS=	Readme Readme.elite
PORTDATA=	*

OPTIONS_DEFINE=	DOCS

MAKE_JOBS_UNSAFE=	yes

post-extract:
	@${FIND} ${WRKSRC}/Data -name '._*' -delete

post-patch:
	@${REINPLACE_CMD} -e '/InitGL/ s|.*|chdir("${DATADIR}"); &|' ${WRKSRC}/Source/Main.cpp

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/objs/blackshades ${STAGEDIR}${PREFIX}/bin/
	@cd ${WRKSRC} && ${COPYTREE_SHARE} Data ${STAGEDIR}${DATADIR}/

do-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
.for f in ${PORTDOCS}
	${INSTALL_DATA} ${WRKSRC}/${f} ${STAGEDIR}${DOCSDIR}
.endfor

.include <bsd.port.mk>
