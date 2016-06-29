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

PKGMESSAGE=	${WRKDIR}/pkg-message
SUB_FILES+=	pkg-message

STRIP=		# stripping can break openrc scripts

USE_GITHUB=     yes
GH_TUPLE=       trueos:openrc:%%GHTAG%% \
		trueos:freebsd:31eb7bb:freebsd

.include <bsd.port.pre.mk>

post-extract:
	@${MKDIR} ${WRKSRC}/src/github.com/freebsd
	@${MV} ${WRKSRC_freebsd} ${WRKSRC}/src/github.com/freebsd/freebsd

post-configure:
	@${REINPLACE_CMD} -e 's|/sbin/openrc|/usr/local/sbin/openrc|g' ${WRKSRC}/etc/rc.in
	@${REINPLACE_CMD} -e 's|/sbin/openrc|/usr/local/sbin/openrc|g' ${WRKSRC}/etc/rc.shutdown.in
	@${REINPLACE_CMD} -e 's|/etc/init.d|/usr/local/etc/init.d|g' ${WRKSRC}/etc/rc.devd
	@${REINPLACE_CMD} -e 's|/etc/rc|/usr/local/etc/rc|g' ${WRKSRC}/src/github.com/freebsd/freebsd/sbin/init/init.c
	@${REINPLACE_CMD} -e 's|/etc/rc|/usr/local/etc/rc|g' ${WRKSRC}/src/github.com/freebsd/freebsd/sbin/init/pathnames.h
	@cd ${WRKSRC}/src/github.com/freebsd/freebsd/sbin/init; make
	@${MKDIR} ${STAGEDIR}${PREFIX}/sbin/
	${INSTALL_PROGRAM} ${WRKSRC}/src/github.com/freebsd/freebsd/sbin/init/init ${STAGEDIR}${PREFIX}/sbin/

.include <bsd.port.post.mk>
