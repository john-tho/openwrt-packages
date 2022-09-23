#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-protobuf
PKG_VERSION:=4.21.6
PKG_RELEASE:=$(AUTORELEASE)

PYPI_NAME:=protobuf
PKG_HASH:=6b1040a5661cd5f6e610cbca9cfaa2a17d60e2bb545309bc1b278bb05be44bdd

PKG_MAINTAINER:=Michal Vasilek <michal.vasilek@nic.cz>
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-protobuf
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Library for developing with protobuf
  URL:=https://developers.google.com/protocol-buffers/
  DEPENDS:=+python3-light
endef

define Package/python3-protobuf/description
  Protocol buffers are Google's language-neutral, platform-neutral,
  extensible mechanism for serializing structured data – think XML, but
  smaller, faster, and simpler. You define how you want your data to be
  structured once, then you can use special generated source code to
  easily write and read your structured data to and from a variety of
  data streams and using a variety of languages. 
endef

$(eval $(call Py3Package,python3-protobuf))
$(eval $(call BuildPackage,python3-protobuf))
$(eval $(call BuildPackage,python3-protobuf-src))
