DIR=	${INITDIR}
SRCS=	pcdm.in
BIN=    ${OBJS}

MK=	../mk

SED_EXTRA+= -e 's:@VARBASE@:/var:g'

include ${MK}/os.mk
include ${MK}/scripts.mk

_installafter_: realinstall

