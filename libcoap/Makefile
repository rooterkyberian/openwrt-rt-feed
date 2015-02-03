include $(TOPDIR)/rules.mk

PKG_NAME:=libcoap
PKG_VERSION:=4.1.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@SF/libcoap
PKG_MD5SUM:=2ab6daf1f187f02d25b77c39c2ecc56b

#PKG_BUILD_PARALLEL:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/libcoap
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=CoAP implementation compatible with RFC 7252
  URL:=http://libcoap.sourceforge.net/
  DEPENDS:=
  MAINTAINER:=Maciej Urbanski <rooter@kyberian.net>
endef

define Package/libcoap/description
	Lightweight application-protocol for devices that are constrained their
	resources such as computing power, RF range, memory, bandwith, or network
	packet sizes. This protocol, CoAP, is developed in the IETF working group
	"CoRE", <http://6lowapp.net>.
endef

CONFIGURE_ARGS+= \
	--with-shared \


define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/coap
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/*.h $(1)/usr/include/coap/

	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/libcoap.{a,so*} $(1)/usr/lib/
endef

define Package/libcoap/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/libcoap.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libcoap))
