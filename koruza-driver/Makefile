include $(TOPDIR)/rules.mk

PKG_NAME:=koruza-driver
PKG_VERSION:=2016-08-31
PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/IRNAS/koruza-driver.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE_VERSION:=b1cc1af6e03b58e854a40cfdd8c5ddda1066228f
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_MAINTAINER:=Jernej Kos <jernej@kos.mx>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/koruza-driver
  SECTION:=utils
  CATEGORY:=Base system
  TITLE:=KORUZA driver
  DEPENDS:=+libubus +libubox +libuci
endef

define Package/koruza-driver/description
  KORUZA driver
endef

define Package/koruza-driver/conffiles
/etc/config/koruza
endef

define Package/koruza-driver/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/koruza-driver.init $(1)/etc/init.d/koruza-driver
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/koruza-driver $(1)/usr/bin/koruza-driver
	$(INSTALL_DIR) $(1)/usr/share/rpcd/acl.d
	$(INSTALL_CONF) ./files/rpcd-acl.json $(1)/usr/share/rpcd/acl.d/koruza-driver.json
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) ./files/koruza-driver.config $(1)/etc/config/koruza
endef

$(eval $(call BuildPackage,koruza-driver))

