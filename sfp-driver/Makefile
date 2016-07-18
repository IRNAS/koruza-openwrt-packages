include $(TOPDIR)/rules.mk

PKG_NAME:=sfp-driver
PKG_VERSION:=2016-07-18
PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/IRNAS/sfp-driver.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE_VERSION:=bca2a5686a2342dc105c04d4fa6f7c8f63d1c41b
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_MAINTAINER:=Jernej Kos <jernej@kos.mx>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/sfp-driver
  SECTION:=utils
  CATEGORY:=Base system
  TITLE:=SFP driver
  DEPENDS:=+libubus +libubox +libuci
endef

define Package/sfp-driver/description
  KORUZA driver
endef

define Package/sfp-driver/conffiles
/etc/config/sfp
endef

define Package/sfp-driver/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/sfp-driver.init $(1)/etc/init.d/sfp-driver
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/sfp-driver $(1)/usr/bin/sfp-driver
	$(INSTALL_DIR) $(1)/usr/share/rpcd/acl.d
	$(INSTALL_CONF) ./files/rpcd-acl.json $(1)/usr/share/rpcd/acl.d/sfp-driver.json
endef

$(eval $(call BuildPackage,sfp-driver))

