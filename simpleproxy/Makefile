
# Copyright (C) 2006-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=simpleproxy
PKG_SOURCE_DATE:=2016-08-08
#PKG_VERSION:=3.5
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=https://github.com/vzaliva/simpleproxy.git
PKG_SOURCE_VERSION:=2328a3c2265eb3363bcc45a02f1d1455023a468f
PKG_MIRROR_HASH:=18a42b6be0f18a930bd65029f6f5d1569f8eb349be513fac0413cbaca0839038

PKG_MAINTAINER:=Thomas Kupper <thomas.kupper@gmail.com>
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=LICENSE-GPL2

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/simpleproxy
  SECTION:=simpleproxy
  CATEGORY:=Network
  URL:=https://github.com/vzaliva/simpleproxy
  TITLE:=Simple TCP proxy
endef

define Package/simpleproxy/description
  Simpleproxy is a simple TCP proxy. It accepts connections on a local
  TCP port and forward them to anoter port on a remote host via TCP.
endef

define Package/simpleproxy/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_DIR) $(1)/opt/share/man/man1
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/opt/bin/simpleproxy $(1)/opt/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/opt/man/man1/simpleproxy.1 $(1)/opt/share/man/man1/
endef

$(eval $(call BuildPackage,simpleproxy))
