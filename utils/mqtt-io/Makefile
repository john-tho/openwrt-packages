
include $(TOPDIR)/rules.mk

PKG_NAME:=mqtt-io
PKG_VERSION:=2.2.7
PKG_RELEASE:=1

PYPI_NAME:=mqtt-io
PKG_HASH:=f9e862db6fd93bbb6d6bd84c745d29ce22358500598077233385addb63e88bf3

PKG_MAINTAINER:=John Thomson <maint@johnthomson.fastmail.com.au>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENCE

include ../../lang/python/pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../../lang/python/python3-package.mk

define Package/mqtt-io
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=GPIO control from MQTT
  URL:=https://github.com/flyte/mqtt-io
  DEPENDS:= \
    +python3-paho-mqtt \
	+python3-yaml \
	+python3-cerberus \
	+python3-typing-extensions \
	+python3-asyncio-mqtt \
	+python3-backoff \
	+python3-confp

endef

define Package/mqtt-io/description
	Exposes general purpose inputs and outputs (GPIO), hardware sensors
	and serial devices to an MQTT server. Ideal for single-board
	computers such as the Raspberry Pi.
endef

define Py3Package/mqtt-io/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/mqtt-io.init $(1)/etc/init.d/mqtt-io
	$(INSTALL_DIR) $(1)/etc/mqtt-io
endef

$(eval $(call Py3Package,mqtt-io))
$(eval $(call BuildPackage,mqtt-io))
