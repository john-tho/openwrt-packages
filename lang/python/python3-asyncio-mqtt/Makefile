include $(TOPDIR)/rules.mk

PKG_NAME:=python3-asyncio-mqtt
PKG_VERSION:=0.12.1
PKG_RELEASE:=1

PYPI_NAME:=asyncio_mqtt
PKG_HASH:=6dbf85a45f94d26e7465411680ada3947b50546e98208d5d52e7a0a7ed7a7c38

PKG_MAINTAINER:=John Thomson <maint@johnthomson.fastmail.com.au>
PKG_LICENSE:=BSD 3-Clause "New" or "Revised" License
PKG_LICENSE_FILES:=LICENSE

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-asyncio-mqtt
  SECTION:=lang-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=asyncio-mqtt
  URL:=https://github.com/sbtinstruments/asyncio-mqtt
  DEPENDS:= \
    +python3-light \
    +python3-paho-mqtt
endef

define Package/python3-asyncio-mqtt/description
  MQTT client with idiomatic asyncio interface
endef

$(eval $(call Py3Package,python3-asyncio-mqtt))
$(eval $(call BuildPackage,python3-asyncio-mqtt))
$(eval $(call BuildPackage,python3-asyncio-mqtt-src))
