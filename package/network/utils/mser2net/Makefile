#
# Copyright (C) 2011-2012 Daniel Golle <dgolle@allnet.de>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mser2net
PKG_VERSION:=2.5
PKG_RELEASE:=3

PKG_LICENSE:=GPL-2.0+
PKG_LICENSE_FILES:=COPYING
PKG_MAINTAINER:=Michael Heimpold <mhei@heimpold.de>

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/mser2net
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Serial to Network Proxy enhanced for multi-connections support!
  DEPENDS:=+USE_UCLIBC:libpthread +USE_UCLIBC:librt
endef

define Package/mser2net/description
  This project provides a proxy that allows multi-connections telnet/tcp connections to be made to
  serial ports on a machine.
endef

define Package/mser2net/conffiles
/etc/mser2net.conf
endef

define Package/mser2net/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/ser2net $(1)/usr/sbin/mser2net

	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_CONF) ./files/mser2net.conf $(1)/etc/

	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_CONF) ./files/mser2net2.conf $(1)/etc/

	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) ./files/mser2net.config $(1)/etc/config/mser2net

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/mser2net.init $(1)/etc/init.d/mser2net
endef

$(eval $(call BuildPackage,mser2net))
