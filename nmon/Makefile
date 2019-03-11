
# Copyright (C) 2006-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# TODO: 20190311/lists ncurses6 as dependency instead of ncurses only

include $(TOPDIR)/rules.mk

PKG_NAME:=nmon
PKG_VERSION:=14g
PKG_RELEASE:=1

PKG_SOURCE:=lmon$(PKG_VERSION).c
PKG_SOURCE_URL:=@SF/nmon
PKG_HASH:=f3c062383b9447ed90eb631b8a13045a8dd70c2692f134cc23a81a618f1e5efc

#PKG_USE_MIPS16:=0
#PKG_USE_X64:=0

PKG_MAINTAINER:=Thomas Kupper <thomas.kupper@gmail.com>
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=LICENSE-GPL2

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
#PKG_INSTALL:=1
#UNPACK_CMD=$(CP) $(DL_DIR)/$(PKG_SOURCE) $(1)/

include $(INCLUDE_DIR)/package.mk

define Package/nmon
  SECTION:=nmon
  CATEGORY:=Administration
  URL:=http://nmon.sourceforge.net/pmwiki.php
  TITLE:=Nigel's performance Monitor for Linux
  DEPENDS:=+libncurses
endef

define Package/nmon/description
  Linux performance monitoring on-screen or to CSV file
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) $(DL_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)
endef

TARGET_LDFLAGS += -lncurses
TARGET_CPPFLAGS += -g -D JFS -D GETUSER -Wall -D LARGEMEM

define Build/Compile
	$(TARGET_CC) $(TARGET_CPPFLAGS) $(TARGET_CFLAGS) -o $(PKG_BUILD_DIR)/$(PKG_NAME) \
	$(PKG_BUILD_DIR)/$(MAKE_PATH)/$(PKG_SOURCE) $(TARGET_LDFLAGS)
endef

define Package/nmon/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(CP) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/opt/bin/
endef

$(eval $(call BuildPackage,nmon))
