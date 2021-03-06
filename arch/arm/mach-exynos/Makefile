# arch/arm/mach-exynos/Makefile
#
# Copyright (c) 2010-2011 Samsung Electronics Co., Ltd.
#		http://www.samsung.com/
#
# Licensed under GPLv2

obj-y				:=
obj-m				:=
obj-n				:=
obj-				:=

# Core

obj-$(CONFIG_ARCH_EXYNOS)	+= common.o
obj-$(CONFIG_SOC_EXYNOS5430)	+= asv-exynos.o asv-exynos5430.o pm_domains-exynos5430.o
obj-$(CONFIG_SOC_EXYNOS5433)	+= asv-exynos.o asv-exynos5433.o pm_domains-exynos5433.o asv-exynos5433_cal.o otp.o
obj-$(CONFIG_SOC_EXYNOS5422)	+= asv-exynos.o asv-exynos5422.o pm_domains-exynos5422.o

obj-$(CONFIG_EXYNOS5430_BTS)	+= bts-exynos5430.o
obj-$(CONFIG_EXYNOS5433_BTS)	+= bts-exynos5433.o
obj-$(CONFIG_EXYNOS5422_BTS)	+= bts-exynos5422.o
ifeq ($(CONFIG_SOC_EXYNOS5430),y)
obj-$(CONFIG_SUSPEND)		+= pm-exynos5430.o
obj-$(CONFIG_CPU_IDLE)		+= cpuidle.o
endif
ifeq ($(CONFIG_SOC_EXYNOS5433),y)
obj-$(CONFIG_SUSPEND)		+= pm-exynos5433.o
obj-$(CONFIG_CPU_IDLE)		+= cpuidle-exynos5433.o
obj-$(CONFIG_CPU_IDLE)		+= cpuidle_profiler.o
endif
obj-$(CONFIG_CPUIDLE_TEST_SYSFS)	+= cpuidle_sysfs.o

ifeq ($(CONFIG_SOC_EXYNOS5422),y)
obj-$(CONFIG_SUSPEND)		+= pm-exynos5422.o
obj-$(CONFIG_CPU_IDLE)		+= cpuidle-exynos5422.o
endif
obj-$(CONFIG_CPU_IDLE)		+= exynos-pm.o
obj-$(CONFIG_PM_RUNTIME)	+= pm_domains.o
obj-$(CONFIG_PM_RUNTIME_TEST_SYSFS)	+= pm_domains_sysfs.o

obj-$(CONFIG_SMP)		+= platsmp.o headsmp.o

obj-$(CONFIG_HOTPLUG_CPU)	+= hotplug.o

obj-$(CONFIG_ARCH_EXYNOS)	+= exynos-smc.o
obj-$(CONFIG_ARCH_EXYNOS)	+= firmware.o
obj-$(CONFIG_SOC_EXYNOS5430)	+= pmu-exynos5430.o
obj-$(CONFIG_SOC_EXYNOS5433)	+= pmu-exynos5433.o
obj-$(CONFIG_SOC_EXYNOS5422)	+= pmu-exynos5422.o

obj-$(CONFIG_CAL_SYS_PWRDOWN)	+= pmu_cal_sys.o
ifeq ($(CONFIG_SOC_EXYNOS5433),y)
obj-$(CONFIG_CAL_SYS_PWRDOWN)	+= pmu_cal_sys_exynos5433.o
endif

obj-$(CONFIG_EXYNOS_SNAPSHOT)	+= exynos-ss.o
obj-$(CONFIG_EXYNOS_CORESIGHT)	+= exynos-coresight.o

plus_sec := $(call as-instr,.arch_extension sec,+sec)
AFLAGS_exynos-smc.o		:=-Wa,-march=armv7-a$(plus_sec)

# machine support

obj-$(CONFIG_MACH_SMDKC210)		+= mach-smdkv310.o
obj-$(CONFIG_MACH_SMDKV310)		+= mach-smdkv310.o
obj-$(CONFIG_MACH_ARMLEX4210)		+= mach-armlex4210.o
obj-$(CONFIG_MACH_UNIVERSAL_C210)	+= mach-universal_c210.o
obj-$(CONFIG_MACH_NURI)			+= mach-nuri.o
obj-$(CONFIG_MACH_ORIGEN)		+= mach-origen.o

obj-$(CONFIG_MACH_SMDK4212)		+= mach-smdk4x12.o
obj-$(CONFIG_MACH_SMDK4412)		+= mach-smdk4x12.o

obj-$(CONFIG_MACH_EXYNOS4_DT)		+= mach-exynos4-dt.o
obj-$(CONFIG_MACH_EXYNOS5_DT)		+= mach-exynos5-dt.o

obj-$(CONFIG_MACH_SMDK5422)		+= mach-smdk5422.o
obj-$(CONFIG_MACH_XYREF5422)		+= mach-xyref5422.o
obj-$(CONFIG_MACH_UNIVERSAL5422)	+= mach-universal5422.o

obj-$(CONFIG_MACH_XYREF5430)		+= mach-xyref5430.o
obj-$(CONFIG_MACH_UNIVERSAL5430)	+= mach-universal5430.o

obj-$(CONFIG_MACH_ESPRESSO5433)		+= mach-espresso5433.o
obj-$(CONFIG_MACH_UNIVERSAL5433)	+= mach-universal5433.o

# BRCM
obj-$(CONFIG_MACH_UNIVERSAL5433)	+= ../../../drivers/net/wireless/bcmdhd4358/dhd_custom_exynos.o

obj-$(CONFIG_VIDEO_EXYNOS_FIMC_IS)    += setup-fimc-is.o
obj-$(CONFIG_VIDEO_EXYNOS_FIMC_IS)    += setup-fimc-is-sensor.o
obj-$(CONFIG_VIDEO_EXYNOS_FIMC_IS)    += setup-fimc-is-companion.o

# device support

obj-y					+= dev-uart.o
obj-$(CONFIG_ARCH_EXYNOS4)		+= dev-audio.o
obj-$(CONFIG_EXYNOS4_DEV_AHCI)		+= dev-ahci.o
obj-$(CONFIG_EXYNOS_DEV_DMA)		+= dma.o
obj-$(CONFIG_EXYNOS4_DEV_USB_OHCI)	+= dev-ohci.o
obj-$(CONFIG_VIDEO_EXYNOS_FIMG2D)	+= dev-fimg2d.o

obj-$(CONFIG_ARCH_EXYNOS)		+= setup-i2c0.o
obj-$(CONFIG_EXYNOS4_SETUP_FIMC)	+= setup-fimc.o
obj-$(CONFIG_EXYNOS4_SETUP_FIMD0)	+= setup-fimd0.o
obj-$(CONFIG_EXYNOS4_SETUP_I2C1)	+= setup-i2c1.o
obj-$(CONFIG_EXYNOS4_SETUP_I2C2)	+= setup-i2c2.o
obj-$(CONFIG_EXYNOS4_SETUP_I2C3)	+= setup-i2c3.o
obj-$(CONFIG_EXYNOS4_SETUP_I2C4)	+= setup-i2c4.o
obj-$(CONFIG_EXYNOS4_SETUP_I2C5)	+= setup-i2c5.o
obj-$(CONFIG_EXYNOS4_SETUP_I2C6)	+= setup-i2c6.o
obj-$(CONFIG_EXYNOS4_SETUP_I2C7)	+= setup-i2c7.o
obj-$(CONFIG_EXYNOS4_SETUP_KEYPAD)	+= setup-keypad.o
obj-$(CONFIG_EXYNOS4_SETUP_SDHCI_GPIO)	+= setup-sdhci-gpio.o
obj-$(CONFIG_EXYNOS4_SETUP_USB_PHY)	+= setup-usb-phy.o
obj-$(CONFIG_EXYNOS_SETUP_SPI)		+= setup-spi.o
obj-$(CONFIG_EXYNOS5_SETUP_MIPIPHY)	+= setup-exynos5-mipiphy.o
obj-$(CONFIG_EXYNOS_CONTENT_PATH_PROTECTION) += secmem.o

# HMP
obj-$(CONFIG_SCHED_HMP)			+= core_sysfs.o

ifdef CONFIG_MSM_SUBSYSTEM_RESTART
	obj-y += subsystem_notif.o
	obj-y += subsystem_restart.o
endif
