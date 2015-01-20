include $(TOPDIR)/rules.mk

PKG_NAME:=smcp
PKG_VERSION:=0.6.5

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/darconeous/smcp.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=08e822e86a39e74ce07e0f675980723c70c508cf
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_FIXUP:=autoreconf
#PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/smcp
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=lightweight CoAP implementation
  URL:=https://github.com/darconeous/smcp/
  DEPENDS:=+libpthread +libcurl
endef

define Package/smcp/description
  SMCP is a C-based CoAP stack which is suitable for embedded environments
endef

CONFIGURE_ARGS += \
				 --disable-readline

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/{lib,include}
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/lib* $(1)/usr/lib/
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
endef

define Package/smcp/install
    $(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libsmcp.so.* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/smcpctl $(1)/usr/bin/
endef

$(eval $(call BuildPackage,smcp))
