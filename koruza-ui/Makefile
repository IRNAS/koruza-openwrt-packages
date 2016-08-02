include $(TOPDIR)/rules.mk

PKG_NAME:=koruza-ui
PKG_VERSION:=2016-08-02
PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/IRNAS/koruza-ui.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE_VERSION:=42e06aab5726566aa5c1e1e4fe677c65992b730a
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_MAINTAINER:=Jernej Kos <jernej@kos.mx>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/koruza-ui
  SECTION:=utils
  CATEGORY:=Base system
  TITLE:=KORUZA UI
  DEPENDS:=+koruza-driver +sfp-driver +rpcd +rpcd-mod-iwinfo +uhttpd +uhttpd-mod-ubus
endef

define Package/koruza-ui/description
  KORUZA UI
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/koruza-ui/install
	$(INSTALL_DIR) $(1)/www/koruza
	cp -a $(PKG_BUILD_DIR)/openwrt/* $(1)/www/koruza/
endef

$(eval $(call BuildPackage,koruza-ui))
