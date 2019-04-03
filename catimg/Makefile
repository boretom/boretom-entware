##
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=catimg
PKG_SOURCE_DATE:=2019-03-10
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/posva/catimg.git
PKG_SOURCE_VERSION:=091f02157532a32672a00327a1004230036f1f3f
PKG_MIRROR_HASH:=1b4adc76f319c554364847e0f0920d81c13e66dcb6302de5094bc137e6aa02a2

PKG_MAINTAINER:=Thomas Kupper <thomas.kupper@gmail.com>
PKG_LICENSE:=MIT

PKG_INSTALL=0

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/catimg
  SECTION:=multimedia
  CATEGORY:=Utilities
  TITLE:=Insanely fast image printing in your terminal
  URL:=https://posva.net/shell/retro/bash/2013/05/27/catimg
  DEPENDS:=
endef

define Package/catimg/description
  catimg is a little program written in C with no dependencies that prints images
  in terminal. It supports JPEG, PNG and GIF formats. This program was originally
  a script that did the same by using ImageMagick convert.
endef

define Package/catimg/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(CP) $(PKG_BUILD_DIR)/bin/catimg $(1)/opt/bin/
endef

$(eval $(call BuildPackage,catimg))
