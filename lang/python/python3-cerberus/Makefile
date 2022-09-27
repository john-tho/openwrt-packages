include $(TOPDIR)/rules.mk

PKG_NAME:=python3-cerberus
PKG_VERSION:=1.3.4
PKG_RELEASE:=1

PYPI_NAME:=Cerberus
PKG_HASH:=d1b21b3954b2498d9a79edf16b3170a3ac1021df88d197dc2ce5928ba519237c

PKG_MAINTAINER:=John Thomson <maint@johnthomson.fastmail.com.au>
PKG_LICENSE:=ISC
PKG_LICENSE_FILES:=LICENSE

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-cerberus
  SECTION:=lang-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Cerberus
  URL:=https://github.com/pyeve/cerberus
  DEPENDS:= \
    +python3-light
endef

define Package/python3-cerberus/description
  Cerberus is a lightweight and extensible data validation library for Python.
endef

$(eval $(call Py3Package,python3-cerberus))
$(eval $(call BuildPackage,python3-cerberus))
$(eval $(call BuildPackage,python3-cerberus-src))
