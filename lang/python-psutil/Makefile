include $(TOPDIR)/rules.mk

PKG_NAME:=psutil
PKG_VERSION:=5.4.3
PKG_RELEASE:=1

PKG_SOURCE:=psutil-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/e2/e1/600326635f97fee89bf8426fef14c5c29f4849c79f68fd79f433d8c1bd96/
PKG_MD5SUM:=3b291833dbea631db9d271aa602a169a

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-psutil
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python-psutil
  URL:=https://github.com/giampaolo/psutil
  DEPENDS:=+python
endef

define Package/python-psutil/description
  psutil is a module providing an interface for retrieving information on all running processes and system utilization (CPU, memory, disks, network, users) in a portable way by using Python.
endef

define Build/Compile
	$(call Build/Compile/PyMod,., \
		install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" \
	)
endef

define Package/python-psutil/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-psutil))
