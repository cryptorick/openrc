include ../mk/net.mk

DIR=	${CONFDIR}
CONF=	bootmisc fsck hostname localmount netmount urandom tmpfiles \
	${CONF-${OS}}

ifeq (${MKNET},yes)
CONF+= modules network staticroute
TARGETS+=	modules network staticroute
CLEANFILES+=	modules network staticroute
endif

MK=	../mk
include ${MK}/os.mk

CONF-FreeBSD=	ipfw moused powerd rarpd savecore syscons

CONF-Linux=	consolefont devfs dmesg hwclock keymaps killprocs mtab \
		net-online

CONF-NetBSD=	moused rarpd savecore

include ${MK}/scripts.mk

modules: modules${SFX}
	cp $@${SFX} $@

network: network.in network${SFX}
	cat $^ > $@

staticroute: staticroute${SFX}
	cp $@${SFX} $@
