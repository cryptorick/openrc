# Created by: Joe Maloney <jmaloney@ixsystems.com>
# $FreeBSD$

PORTNAME=	openrc
PORTVERSION=    %%CHGVERSION%%
CATEGORIES=	sysutils
MASTER_SITES=
DISTFILES=

MAINTAINER=	jmaloney@ixsystems.com
COMMENT=	Dependency-based init system

LICENSE=	BSD2CLAUSE

USE_LDCONFIG=	yes
USES=		gmake pkgconfig:both

USE_RC_SUBR+=	openrc
PKGMESSAGE=	${WRKDIR}/pkg-message
SUB_FILES+=	pkg-message

STRIP=		# stripping can break openrc scripts

USE_GITHUB=     yes
GH_TUPLE=       trueos:openrc:%%GHTAG%% \
                trueos:freebsd:31eb7bb:freebsd

.include <bsd.port.mk>
