#
# Copyright (C) 2016 LEDE
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=sch-fq-codel-fast-oot
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/dtaht/fq_codel_fast/
PKG_SOURCE_DATE:=2019-08-20
PKG_SOURCE_VERSION:=51bd334bffe5fca5171fdc08c1e83eb7b5c1db1c
PKG_MIRROR_HASH:=bb226cf0d6a774c82af740adaf21e62075ca4716b9db7c4078edd66a5133ff07
PKG_MAINTAINER:=TBD

include $(INCLUDE_DIR)/package.mk

define KernelPackage/sch-fq-codel-fast-oot
  SUBMENU:=Network Support
  TITLE:=OOT experimental fast fq_codel shaper
  URL:=https://github.com/dtaht/fq_codel_fast/
  FILES:=$(PKG_BUILD_DIR)/sch_fq_codel_fast.ko
  AUTOLOAD:=$(call AutoLoad,75,sch_fq_codel_fast)
  DEPENDS:=
endef

include $(INCLUDE_DIR)/kernel-defaults.mk

define KernelPackage/sched-cake/description
  O(ut) O(f) T(ree) Common Applications Experimental fast fq_codel shaper
endef

define Build/Compile
	$(KERNEL_MAKE) M="$(PKG_BUILD_DIR)" modules
endef

$(eval $(call KernelPackage,sch-fq-codel-fast-oot))
