
# Copyright (C) 2006-2019 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=tshark
PKG_VERSION:=2.6.7
PKG_RELEASE:=1

PKG_SOURCE:=wireshark-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://www.wireshark.org/download/src/all-versions
PKG_HASH:=747b3e7a37414942959f76f198be49dcbcca936bda538c4408942ce71bfd2b71
PKG_INSTALL:=1

PKG_MAINTAINER:=Thomas Kupper <thomas.kupper@gmail.com>
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=LICENSE-GPL2

PKG_BUILD_DIR:=$(BUILD_DIR)/wireshark-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/tshark
  SECTION:=tshark
  CATEGORY:=Network
  URL:=https://www.wireshark.org
  TITLE:=Terminal based wireshark to dump and analyze network traffic
  #DEPENDS:=+geoip
  DEPENDS:=+libcares +glib2 +libcap +libpcap +libpcre +libgcrypt +libgnutls +zlib +libxml2 +libssh2 +libnghttp2 $(ICONV_DEPENDS)
endef

define Package/tshark/description
  TShark is a network protocol analyzer. It lets you capture packet data from a live network,
  or read packets from a previously saved capture file, either printing a decoded form of
  those packets to the standard output or writing the packets to a file. TShark's native capture
  file format is libpcap format, which is also the format used by tcpdump and various other tools.
endef


TARGET_CFLAGS += -D_GNU_SOURCE

CONFIGURE_ARGS += \
	--disable-wireshark \
	--with-libgcrypt-prefix=$(STAGING_PREFIX) \
	--with-qt=no --with-gtk=no \
	--with-pcap=$(STAGING_DIR)/opt \
	--enable-setuid-install \
	--enable-sshdump=yes \
	--without-lua \
	--without-libssh \
	--with-nghttp2 \
	--disable-wireshark

define Build/Compile
	$(MAKE) CC_FOR_BUILD=$(HOSTCC) CC=$(HOSTCC) -C $(PKG_BUILD_DIR)/tools/lemon lemon
	$(call Build/Compile/Default)
endef

define Package/tshark/install
	$(INSTALL_DIR) $(1)/opt/bin $(1)/opt/lib
	$(CP) $(PKG_INSTALL_DIR)/opt/bin/* $(1)/opt/bin/
	$(CP) $(PKG_INSTALL_DIR)/opt/lib/lib*.so.* $(1)/opt/lib/
	$(CP) $(PKG_INSTALL_DIR)/opt/lib/wireshark $(1)/opt/lib/
endef

$(eval $(call BuildPackage,tshark))
