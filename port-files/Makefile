# Created by: Joe Maloney <jmaloney@ixsystems.com>
# $FreeBSD$

PORTNAME=	openrc
PORTVERSION=    %%CHGVERSION%%
CATEGORIES=	sysutils

MAINTAINER=	jmaloney@ixsystems.com
COMMENT=	Dependency-based init system

LICENSE=	BSD2CLAUSE

USE_LDCONFIG=	yes
USES=		gmake pkgconfig:both

USE_RC_SUBR+=	openrc
PKGMESSAGE=	${WRKDIR}/pkg-message
SUB_FILES+=	pkg-message

STRIP=		# stripping can break openrc scripts

.include <bsd.port.pre.mk>

post-configure:
	@${REINPLACE_CMD} -e 's|/sbin/openrc|/usr/local/sbin/openrc|g' ${WRKSRC}/etc/rc.in
	@${REINPLACE_CMD} -e 's|/sbin/openrc|/usr/local/sbin/openrc|g' ${WRKSRC}/etc/rc.shutdown.in
	@${REINPLACE_CMD} -e 's|/etc/init.d|/usr/local/etc/init.d|g' ${WRKSRC}/etc/rc.devd

USE_GITHUB=     yes
GH_ACCOUNT=     trueos
GH_PROJECT=     openrc
GH_TAGNAME=     %%GHTAG%%

.include <bsd.port.post.mk>
