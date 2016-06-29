DIR=	${INITDIR}
SRCS=	cron.in jail.in zfs.in zvol.in
BIN=    ${OBJS}

MK=	../mk

SED_EXTRA+= -e 's:@VARBASE@:/var:g'

include ${MK}/os.mk
include ${MK}/scripts.mk

_installafter_: realinstall

