#
# Copyright (C) 2007-2019 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=glib2
PKG_VERSION:=2.74.0
PKG_RELEASE:=3

PKG_SOURCE:=glib-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=@GNOME/glib/$(word 1,$(subst ., ,$(PKG_VERSION))).$(word 2,$(subst ., ,$(PKG_VERSION)))
PKG_HASH:=3652c7f072d7b031a6b5edd623f77ebc5dcd2ae698598abcc89ff39ca75add30

PKG_MAINTAINER:=Peter Wagner <tripolar@gmx.at>
PKG_LICENSE:=LGPL-2.1-or-later
PKG_LICENSE_FILES:=COPYING
PKG_CPE_ID:=cpe:/a:gnome:glib

PKG_BUILD_DIR:=$(BUILD_DIR)/glib-$(PKG_VERSION)
HOST_BUILD_DIR:=$(BUILD_DIR_HOST)/glib-$(PKG_VERSION)
PKG_CONFIG_DEPENDS:=CONFIG_BUILD_NLS
PKG_FORTIFY_SOURCE:=0
PKG_BUILD_FLAGS:=gc-sections

include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk
include $(INCLUDE_DIR)/meson.mk

define Package/glib2
  SECTION:=libs
  CATEGORY:=Libraries
  DEPENDS:=$(ICONV_DEPENDS) $(INTL_DEPENDS) +zlib +libpthread +libffi +libattr +libpcre2
  TITLE:=glib 2.0
  URL:=http://www.gtk.org/
endef

define Package/glib2/description
  The GLib library of C routines
endef

COMP_ARGS= \
	-Dselinux=disabled \
	-Dlibmount=disabled \
	-Dman=false \
	-Ddtrace=false \
	-Dsystemtap=false \
	-Dsysprof=disabled \
	-Dgtk_doc=false \
	-Dbsymbolic_functions=true \
	-Dforce_posix_threads=true \
	-Dtests=false \
	-Dinstalled_tests=false \
	-Doss_fuzz=disabled \
	-Dglib_debug=disabled \
	-Dglib_assert=false \
	-Dglib_checks=true \
	-Dlibelf=disabled

MESON_HOST_ARGS += $(COMP_ARGS) -Dxattr=false -Ddefault_library=static -Dnls=disabled -Dwrap_mode=forcefallback
MESON_ARGS += $(COMP_ARGS) -Dxattr=true -Db_lto=true -Ddefault_library=both -Dnls=$(if $(CONFIG_BUILD_NLS),en,dis)abled

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/bin/* \
		$(1)/usr/bin/

	$(INSTALL_DIR) $(1)/usr/include
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/include/glib-2.0 \
		$(1)/usr/include/
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/glib-2.0/include/*.h \
		$(1)/usr/include/glib-2.0/
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/include/gio-unix-2.0 \
		$(1)/usr/include/

	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/glib-2.0 \
		$(1)/usr/lib/

	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/*.{so*,a} \
		$(1)/usr/lib/

	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/lib/pkgconfig/*.pc \
		$(1)/usr/lib/pkgconfig

	$(INSTALL_DIR) $(2)/share/aclocal/
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/share/aclocal/*.m4  \
		$(2)/share/aclocal/

	$(INSTALL_DIR) $(1)/usr/share/glib-2.0
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/share/glib-2.0/codegen \
		$(1)/usr/share/glib-2.0/
endef

define Package/glib2/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/*.so* \
		$(1)/usr/lib/
endef

$(eval $(call HostBuild))
$(eval $(call BuildPackage,glib2))
