include $(TOPDIR)/rules.mk

PKG_NAME:=koruza-nodewatcher-agent
PKG_VERSION:=2016-08-29
PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/IRNAS/koruza-nodewatcher-agent.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE_VERSION:=119247b1e901fdc09f12c1eca500c29b27a3ea8a
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_MAINTAINER:=Jernej Kos <jernej@kos.mx>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/koruza-nodewatcher-agent
  SECTION:=utils
  CATEGORY:=Base system
  TITLE:=KORUZA nodewatcher agent module
  DEPENDS:=+koruza-driver +nodewatcher-agent
endef

define Package/koruza-nodewatcher-agent/description
  KORUZA reporting module for nodewatcher agent
endef

define Package/koruza-nodewatcher-agent/install
	$(INSTALL_DIR) $(1)/usr/lib/nodewatcher-agent
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/koruza.so $(1)/usr/lib/nodewatcher-agent/
endef

$(eval $(call BuildPackage,koruza-nodewatcher-agent))
