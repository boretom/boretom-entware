
# Copyright (C) 2006-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=nmon
PKG_VERSION:=14g
PKG_RELEASE:=1

PKG_SOURCE:=lmon(PKG_VERSION).c
PKG_SOURCE_URL:=@SF/nmon
#PKG_MIRROR_HASH:=0601b4d7aa5ee096e99388a57cb0701673ab58fccd6ed2984a2abbd4f846e045

PKG_MAINTAINER:=Thomas Kupper <thomas.kupper@gmail.com>
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=LICENSE-GPL2

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/nmon
  SECTION:=nmon
  CATEGORY:=Administration
  URL:=http://nmon.sourceforge.net/pmwiki.php
  TITLE:=Nigel's performance Monitor for Linux
endef

define Package/nmon/description
  Linux performance monitoring on-screen or to CSV file
endef

define Package/nmon/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_DIR) $(1)/opt/share/man/man1
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/opt/bin/nmon $(1)/opt/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/opt/man/man1/nmon.1 $(1)/opt/share/man/man1/
endef

$(eval $(call BuildPackage,nmon))
