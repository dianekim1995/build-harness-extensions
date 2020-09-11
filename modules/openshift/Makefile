OPENSHIFT_DIR := $(BUILD_HARNESS_EXTENSIONS_PATH)/vendor/openshift
OPENSHIFT := $(OPERATORSDK_DIR)/oc

OPERATORSDK_URL := https://github.com/openshift/origin/releases/download/v1.5.1/openshift-origin-client-tools-v1.5.1-7b451fc-linux-64bit.tar.gz


.PHONY: openshift/install
## Installs the Operator SDK
openshift/install:
	[ -x $(OPENSHIFT) ] || ( \
		echo "Installing Openshift CLI" && \
		mkdir -p $(OPENSHIFT_DIR) && \
		curl '-#' -fL -o $(OPENSHIFT) $(OPENSHIFT_URL) && \
		chmod a+x $(OPENSHIFT) \
		)
	$(OPENSHIFT) version
