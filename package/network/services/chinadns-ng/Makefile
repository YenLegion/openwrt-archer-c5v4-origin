include $(TOPDIR)/rules.mk

PKG_NAME:=chinadns-ng
PKG_VERSION:=1.0-beta.26
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/zfl9/chinadns-ng.git
PKG_SOURCE_VERSION:=e7c4ebd64af2690a153fb0e16a5f543d185545d6
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.xz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)/$(PKG_SOURCE_SUBDIR)

PKG_BUILD_PARALLEL:=1
PKG_USE_MIPS16:=0

PKG_LICENSE:=GPL-3.0
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=pexcn <i@pexcn.me>

include $(INCLUDE_DIR)/package.mk

define Package/chinadns-ng
	SECTION:=net
	CATEGORY:=Network
	TITLE:=ChinaDNS Next Generation, refactoring with epoll and ipset
	URL:=https://github.com/zfl9/chinadns-ng
	DEPENDS:=+ipset
endef

define Package/chinadns-ng/description
ChinaDNS Next Generation, refactoring with epoll and ipset.
endef

define Package/chinadns-ng/conffiles
/etc/config/chinadns-ng
endef

define Package/chinadns-ng/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/chinadns-ng $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) files/chinadns-ng.init $(1)/etc/init.d/chinadns-ng
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) files/chinadns-ng.config $(1)/etc/config/chinadns-ng
endef

$(eval $(call BuildPackage,chinadns-ng))
