# $FreeBSD$

PORTNAME=	plasma-pa
DISTVERSION=	${KDE_PLASMA_VERSION}
CATEGORIES=	audio kde kde-plasma

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Plasma5 Plasma pulse audio mixer

LIB_DEPENDS=	libcanberra.so:audio/libcanberra \
		libpulse.so:audio/pulseaudio

USES=		cmake:outsource compiler:c++11-lib cpe gettext kde:5 \
		pkgconfig qt:5 shebangfix tar:xz
USE_GNOME=	gconf2
USE_KDE=	config configwidgets coreaddons ecm globalaccel i18n \
		kdeclarative package plasma-framework
USE_QT=		core dbus gui network qml quick widgets \
		buildtools_build qmake_build

SHEBANG_FILES=	data/plasmaVolumeDisableKMixAutostart.pl

.include <bsd.port.mk>
