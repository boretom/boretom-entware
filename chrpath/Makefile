##
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=chrpath
PKG_VERSION:=0.16
PKG_RELEASE:=1

PKG_SOURCE_URL:=http://http.debian.net/debian/pool/main/c/chrpath
PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION).orig.tar.gz
PKG_HASH:=bb0d4c54bac2990e1bdf8132f2c9477ae752859d523e141e72b3b11a12c26e7b
PKG_MAINTAINER:=Thomas Kupper <thomas.kupper@gmail.com>
PKG_LICENSE:=GPLv2

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/chrpath
  SECTION:=devel
  CATEGORY:=Development
  TITLE:=Change or delete the rpath or runpath in ELF files
  URL:=http://directory.fsf.org/project/chrpath/
  DEPENDS:=
endef

define Package/chrpath/description
  Change or delete the rpath or runpath in ELF files
endef

TARGET_LDFLAGS+=

define Package/chrpath/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/opt/bin/chrpath $(1)/opt/bin/
endef

$(eval $(call BuildPackage,chrpath))
