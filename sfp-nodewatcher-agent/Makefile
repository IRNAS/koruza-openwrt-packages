include $(TOPDIR)/rules.mk

PKG_NAME:=sfp-nodewatcher-agent
PKG_VERSION:=2016-08-29
PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/IRNAS/sfp-nodewatcher-agent.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE_VERSION:=334caa34962cf62f2f6079f6ee59a9655524f82c
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_MAINTAINER:=Jernej Kos <jernej@kos.mx>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/sfp-nodewatcher-agent
  SECTION:=utils
  CATEGORY:=Base system
  TITLE:=SFP nodewatcher agent module
  DEPENDS:=+sfp-driver +nodewatcher-agent
endef

define Package/sfp-nodewatcher-agent/description
  SFP reporting module for nodewatcher agent
endef

define Package/sfp-nodewatcher-agent/install
	$(INSTALL_DIR) $(1)/usr/lib/nodewatcher-agent
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/sfp.so $(1)/usr/lib/nodewatcher-agent/
endef

$(eval $(call BuildPackage,sfp-nodewatcher-agent))
