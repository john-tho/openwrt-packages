include $(TOPDIR)/rules.mk

PKG_NAME:=python3-confp
PKG_VERSION:=0.4.1
PKG_RELEASE:=1

PYPI_NAME:=confp
PKG_HASH:=5cf8f865318635a89f019e91176fb3a2a019401ba7b1b0805d71e283e7756251

PKG_MAINTAINER:=John Thomson <maint@johnthomson.fastmail.com.au>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-confp
  SECTION:=lang-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=confp
  URL:=https://github.com/flyte/confp
  DEPENDS:= \
    +python3-light \
    +python3-jinja2 \
    +python3-yaml \
    +python3-cerberus
endef

define Package/python3-confp/description
  A configuration management tool, similar to confd using Python and
  the Jinja2 templating language.
endef

$(eval $(call Py3Package,python3-confp))
$(eval $(call BuildPackage,python3-confp))
$(eval $(call BuildPackage,python3-confp-src))
