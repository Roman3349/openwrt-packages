#
# Copyright (C) 2017 MICRORISC s.r.o.
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=paho.mqtt.c
PKG_VERSION:=1.1.0
PKG_RELEASE:=1
PKG_LICENCE:=Apache-2.0
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Roman Ondráček <ondracek.roman@centrum.cz>

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/eclipse/paho.mqtt.c.git
PKG_SOURCE_VERSION:=$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-v$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

CMAKE_OPTIONS += -DPAHO_WITH_SSL=TRUE -DPAHO_BUILD_DOCUMENTATION=FALSE -DPAHO_BUILD_SAMPLES=TRUE

define Package/paho.mqtt.c
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=Eclipse Paho MQTT C client
	DEPENDS:=+libopenssl
	URL:=https://github.com/eclipse/paho.mqtt.c
	MAINTAINER:=Roman Ondráček <ondracek.roman@centrum.cz>
endef

define Package/paho.mqtt.c/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(BUILD_DIR)/src/MQTTVersion $(1)/usr/bin/

	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(BUILD_DIR)/src/libpaho-mqtt3{a,as,c,cs}.so.1.1.0 $(1)/usr/lib/
endef

$(eval $(call BuildPackage,paho.mqtt.c))
