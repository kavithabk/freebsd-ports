# Created by: Wen Heping <wenheping@gmail.com>
# $FreeBSD$

PORTNAME=	adminer
PORTVERSION=	4.6.1
CATEGORIES=	databases www
MASTER_SITES=	https://github.com/vrana/adminer/releases/download/v${PORTVERSION}/
EXTRACT_SUFX=	.php
EXTRACT_ONLY=

MAINTAINER=	uzsolt@uzsolt.hu
COMMENT=	Full-featured database management tool written in PHP

LICENSE=	APACHE20

USES=	php
USE_PHP=	session

NO_ARCH=	yes
NO_BUILD=	yes

PLIST_SUB=	WWWOWN="${WWWOWN}" WWWGRP="${WWWGRP}"
SUB_FILES=	pkg-message
SUB_LIST=	PHPVER="${PHP_VER}"

do-install:
	${MKDIR} ${STAGEDIR}${WWWDIR}/${PORTNAME}
	${CP} ${DISTDIR}/${DISTNAME}${EXTRACT_SUFX} ${STAGEDIR}${WWWDIR}/${PORTNAME}/index.php

.include <bsd.port.mk>
