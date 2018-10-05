
# Copyright (C) 2006-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=simpleproxy
PKG_VERSION:=3.5
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
#PKG_SOURCE_URL=$(PROJECT_GIT)/project/jsonpath.git
PKG_SOURCE_URL=https://github.com/vzaliva/simpleproxy.git
PKG_SOURCE_DATE:=2016-08-08
PKG_SOURCE_VERSION:=2328a3c2265eb3363bcc45a02f1d1455023a468f
#PKG_MIRROR_HASH:=0601b4d7aa5ee096e99388a57cb0701673ab58fccd6ed2984a2abbd4f846e045

PKG_MAINTAINER:=Jane Doe <jane@doe.com>
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=LICENSE-GPL2

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/simpleproxy/Default
	SECTION:=simpleproxy
	CATEGORY:=Network
	URL:=https://github.com/vzaliva/simpleproxy
	TITLE:=Simple TCP proxy
endef

define Package/simpleproxy/description
  Simple TCP proxy
endef

define Package/simpleproxy/install
	$(INSTALL_DIR) $(1)/opt/sbin
endef

#CONFIGURE_ARGS += \

$(eval $(call BuildPackage,simpleproxy))
