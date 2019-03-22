##
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=tiv
PKG_REV:=287fde33419f24017e4db2fec2825f95977d7c5a
PKG_VERSION:=1.0.0-git-$(shell echo "$(PKG_REV)" | cut -c1-7)
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/stefanhaustein/TerminalImageViewer.git
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
#PKG_MIRROR_HASH:=25c2729b8a683b1d982e5d939ca6743d448d43edbeba66f4d25ef534e9a2c907
PKG_MAINTAINER:=Thomas Kupper <thomas.kupper@gmail.com>
PKG_LICENSE:=GPLv2

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/tiv
  SECTION:=devel
  CATEGORY:=Utilities
  TITLE:=Program to display images in a terminal
  URL:=http://directory.fsf.org/project/tiv/
  DEPENDS:=libstdcpp
endef

define Package/tiv/description
  Small C++ program to display images in a (modern) terminal using RGB ANSI codes
  and unicode block graphics characters
endef

define Build/Configure
	# make some of the 001 patch file executable
	chmod +x $(PKG_BUILD_DIR)/{configure,depcomp,install-sh,missing}
	$(call Build/Configure/Default)
endef

define Package/tiv/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(CP) $(PKG_BUILD_DIR)/src/main/cpp/tiv $(1)/opt/bin/
endef

$(eval $(call BuildPackage,tiv))
