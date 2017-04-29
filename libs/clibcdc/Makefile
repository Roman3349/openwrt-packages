#
# Copyright (C) 2017 MICRORISC s.r.o.
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=clibcdc
PKG_VERSION:=0.1.2
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:https://github.com/iqrfsdk/clibcdc.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_MAINTAINER:=Roman Ondráček <ondracek.roman@centrum.cz>
PKG_LICENCE:=Apache-2.0
PKG_LICENSE_FILES:=LICENSE

CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/clibcdc
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=IQRF USB CDC Library
	URL:=https://github.com/iqrfsdk/clibcdc
	MAINTAINER:=Roman Ondráček <ondracek.roman@centrum.cz>
endef

define Package/clibcdc/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libcdcshared.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,clibcdc))
