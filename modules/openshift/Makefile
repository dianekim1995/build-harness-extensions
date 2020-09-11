OPENSHIFT_DIR := $(BUILD_HARNESS_EXTENSIONS_PATH)/vendor/openshift
OPENSHIFT := $(OPENSHIFT_DIR)/oc

OPENSHIFT_URL := https://github.com/openshift/origin/releases/download/v1.5.1/openshift-origin-client-tools-v1.5.1-7b451fc-linux-64bit.tar.gz


.PHONY: openshift/install
## Installs the Openshift CLI
openshift/install:
	[ -x $(OPENSHIFT) ] || ( \
		echo "Installing Openshift CLI" && \
		mkdir -p $(OPENSHIFT_DIR) && \
		cd $(OPENSHIFT_DIR)
		wget $(OPENSHIFT_URL) && \
		chmod a+x $(OPENSHIFT) \
		)
	$(OPENSHIFT) version
