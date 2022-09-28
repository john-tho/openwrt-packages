#
# Copyright (C) 2006-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=kismet
PKG_VERSION:=2022-08-R1
PKG_RELEASE:=$(AUTORELEASE)

PKG_LICENSE:=LGPLv2.1
PKG_CPE_ID:=cpe:/a:kismet:kismet

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://www.kismetwireless.net/code
PKG_HASH:=2149cceac5526508653f4d02dcf7a694e3da3dc000a2372a1ee4bf9988279781

include $(INCLUDE_DIR)/package.mk

define Package/kismet/Default
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Kismet
  MAINTAINER:=John Thomson <maint@johnthomson.fastmail.com.au>
  DEPENDS:= +libstdcpp +libpthread +libpcap +libcap \
	    +libwebsockets-full \
	    +protobuf-lite +libprotobuf-c \
	    +libnl +python3-websockets +python3-protobuf
  URL:=http://www.kismetwireless.net/
  SUBMENU:=Wireless
endef

define Package/kismet/Default/description
 An 802.11 layer2 wireless network detector, sniffer, and intrusion
 detection system.
endef

CONFIGURE_ARGS += \
	--sysconfdir=/etc/kismet \
	--bindir=/usr/bin \
	--disable-debuglibs \
	--enable-capture-tools-only
	#--disable-python-tools \
	#--enable-protobuflite \
	#--with-protoc=$(STAGING_DIR_HOSTPKG)/bin/protoc \
	#--disable-element-typesafety \

#CONFIGURE_VARS += \
#	CXXFLAGS="$$$$CXXFLAGS"
#-fno-rtti"  \
#	LIBS="-lm" \
#	CLIENTCLIBS="-lm"

#define Build/Compile
#	$(MAKE) -C $(PKG_BUILD_DIR) \
#		LD="$(TARGET_CXX)"
#		#datasources
#endef

define Package/kismet/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/capture_linux_wifi/kismet_cap_linux_wifi $(1)/usr/bin/
endef

define Package/kismet
$(call Package/kismet/Default)
  TITLE+= server
  DEPENDS+= +libsqlite3 +zlib +libsensors
endef

$(eval $(call BuildPackage,kismet))
