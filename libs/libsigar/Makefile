include $(TOPDIR)/rules.mk

PKG_NAME:=libsigar
PKG_SOURCE_DATE:=2017-02-21
PKG_SOURCE_VERSION:=a6c61edf8c64e013411e8c9d753165cd03102c6e
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_SOURCE_DATE).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/boundary/sigar/tar.gz/$(PKG_SOURCE_VERSION)?
PKG_HASH:=5232f0fa994ab60ad4622364fad0297c0054e04f0cfec9c586b14e33bbc387da
PKG_BUILD_DIR:=$(BUILD_DIR)/sigar-$(PKG_SOURCE_VERSION)

PKG_LICENSE:=Apache-2.0
PKG_LICENSE_FILE:=LICENSE

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

PKG_BUILD_PARALLEL:=1
CMAKE_INSTALL:=1

define Package/libsigar
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=System Information Gatherer And Reporter
	URL:=https://github.com/boundary/sigar
	DEPENDS:=+libtirpc
	MAINTAINER:=Amol Bhave <ambhave@fb.com>
endef

define Package/libsigar/description
	System Information Gatherer And Reporter
endef

define Package/libsigar/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libsigar.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libsigar))
