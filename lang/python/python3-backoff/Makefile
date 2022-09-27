include $(TOPDIR)/rules.mk

PKG_NAME:=python3-backoff
PKG_VERSION:=2.1.2
PKG_RELEASE:=1

PYPI_NAME:=backoff
PKG_HASH:=407f1bc0f22723648a8880821b935ce5df8475cf04f7b6b5017ae264d30f6069

PKG_MAINTAINER:=John Thomson <maint@johnthomson.fastmail.com.au>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-backoff
  SECTION:=lang-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=backoff
  URL:=https://github.com/litl/backoff
  DEPENDS:= \
    +python3-light
endef

define Package/python3-backoff/description
  Function decoration for backoff and retry
endef

$(eval $(call Py3Package,python3-backoff))
$(eval $(call BuildPackage,python3-backoff))
$(eval $(call BuildPackage,python3-backoff-src))
