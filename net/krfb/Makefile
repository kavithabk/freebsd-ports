# $FreeBSD$

PORTNAME=	krfb
PORTVERSION=	${KDE4_VERSION}
PORTREVISION=	2
CATEGORIES=	net kde kde-kde4

MAINTAINER=	kde@FreeBSD.org
COMMENT=	VNC server for KDE

LIB_DEPENDS=	libtelepathy-qt4.so:net-im/telepathy-qt4

USES=		alias cmake:outsource jpeg kde:4 tar:xz
USE_KDE=	kdelibs automoc4
USE_QT4=	corelib gui network \
		moc_build qmake_build rcc_build uic_build

.include <bsd.port.mk>
