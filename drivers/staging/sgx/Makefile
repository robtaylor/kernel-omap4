
#obj-$(CONFIG_PVR_SGX) += bridged/
#obj-$(CONFIG_PVR_SGX) += common/
#obj-$(CONFIG_PVR_SGX) += devices/
#obj-$(CONFIG_PVR_SGX) += env/

sgx-bridged-objs := bridged_pvr_bridge.o bridged_sgx_bridge.o bridged_support.o
sgx-common-objs := buffer_manager.o hash.o mem_debug.o perproc.o ra.o \
                   deviceclass.o lists.o metrics.o power.o refcount.o \
                   devicemem.o osfunc_common.o pvrsrv.o resman.o handle.o \
                   mem.o pdump_common.o queue.o
sgx-devices-objs := mmu.o pb.o sgxinit.o sgxkick.o sgxpower.o sgxreset.o \
                    sgxtransfer.o sgxutils.o
sgx-env-objs := event.o mmap.o module.o mutils.o osperproc.o proc.o \
                pvr_debug.o mm.o mutex.o osfunc.o pdump.o pvr_bridge_k.o \
                pvr_drm.o sysconfig.o sysutils_linux.o

#pvr-sgx-y := $(addprefix bridged/, $(sgx-bridged-objs))
#pvr-sgx-y := $(addprefix common/, $(sgx-common-objs))
#pvr-sgx-y := $(addprefix devices/, $(sgx-devices-objs))
#pvr-sgx-y := $(addprefix env/, $(sgx-env-objs))
#pvr-sgx-y := sysconfig.o sysutils_linux.o

pvr-sgx-y := $(sgx-bridged-objs) $(sgx-common-objs) $(sgx-devices-objs) $(sgx-env-objs)

subdir-ccflags-y=-D__linux__ -I$(src)/include/ -include $(srctree)/$(src)/include/config_kernel.h
ccflags-y=-D__linux__ -I$(src)/include/ -include $(srctree)/$(src)/include/config_kernel.h

#pvr-sgx-objs := sysconfig.o sysutils_linux.o
#sgx_bridged.o sgx_common.o sgx_devices.o sgx_env.o

obj-$(CONFIG_PVR_SGX) += pvr-sgx.o

