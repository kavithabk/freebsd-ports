# Created by: adamw
# $FreeBSD$

PORTNAME=	x265
PORTVERSION=	2.6
CATEGORIES=	multimedia
MASTER_SITES=	http://ftp.videolan.org/pub/videolan/${PORTNAME}/
DISTNAME=	${PORTNAME}_${PORTVERSION}

MAINTAINER=	mi@aldan.algebra.com
COMMENT=	H.265/High Efficiency Video Coding (HEVC) format

LICENSE=	GPLv2+
LICENSE_FILE=	${WRKSRC}/../COPYING

BUILD_DEPENDS=	yasm:devel/yasm

USES=		cmake compiler:c++14-lang pathfix

OPTIONS_DEFINE=		DEBUG OPTIMIZED_FLAGS
OPTIONS_DEFINE_amd64=	HI10P HI12P

DEBUG_PREVENTS=		OPTIMIZED_FLAGS
DEBUG_PREVENTS_MSG=	Optimizations are incompatible with debugging code
DEBUG_VARS_OFF=		CFLAGS+=-DNDEBUG CPPFLAGS+=-DNDEBUG 
HI10P_CMAKE_BOOL=	HIGH_BIT_DEPTH
HI12P_CMAKE_BOOL=	MAIN12
HI12P_IMPLIES=		HI10P
OPTIMIZED_FLAGS_VARS=	CFLAGS+=-O3 CPPFLAGS+=-O3

DEBUG_DESC=	Enable debugging
HI10P_DESC=	Enable HI10P Support (64-bit only)
HI12P_DESC=	Enable HI12P Support (64-bit only)
OPTIMIZED_FLAGS_DESC=	Enable O3 optimization

USE_LDCONFIG=	yes
CMAKE_ARGS=	-DPLATFORM_LIBS=md -DENABLE_TESTS=on
CFLAGS_mips=	-DNO_ATOMICS # cannot use lang/gcc
CFLAGS_mips64=	-DNO_ATOMICS # cannot use lang/gcc
EXTRACT_AFTER_ARGS+=	--exclude "md5*"
WRKSRC=		${WRKDIR}/${PORTNAME}_v${PORTVERSION}/source

do-test:
	${WRKSRC}/test/TestBench

.include <bsd.port.mk>
