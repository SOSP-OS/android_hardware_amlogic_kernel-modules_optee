LOCAL_INCLUDES += -I$(M)/../include  \
               -I$(M)/../include/linux \
               -I$(M)/include \
               -I$(M)/include/linux \
               -I$(KERNEL_SRC)/$(M)/../include \
               -I$(KERNEL_SRC)/$(M)/../include/linux \
               -I$(KERNEL_SRC)/$(M)/include \
               -I$(KERNEL_SRC)/$(M)/include/linux

ccflags-y+=-Werror
ccflags-y+=$(LOCAL_INCLUDES)

obj-m += optee_armtz.o

optee_armtz-objs += core.o
optee_armtz-objs += call.o
optee_armtz-objs += rpc.o
optee_armtz-objs += supp.o
ifeq ($(KERNEL_A32_SUPPORT), true)
optee_armtz-objs += smccc-call-a32.o
else
optee_armtz-objs += smccc-call.o
endif
optee_armtz-objs += log.o
optee_armtz-objs += watermark.o
