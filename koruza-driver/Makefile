include $(TOPDIR)/rules.mk

PKG_NAME:=koruza-driver
PKG_VERSION:=2016-07-29
PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/IRNAS/koruza-driver.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE_VERSION:=46b2c8d6962a59103e12995b4a281d4a26725968
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
endef

$(eval $(call BuildPackage,koruza-driver))

