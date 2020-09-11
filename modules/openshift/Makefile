OPENSHIFT_DIR := $(BUILD_HARNESS_EXTENSIONS_PATH)/vendor/openshift
OPENSHIFT := $(OPENSHIFT_DIR)/oc
OPENSHIFT_ARCHIVE := openshift-origin-client-tools-v1.5.1-7b451fc-linux-64bit.tar.gz
OPENSHIFT_URL := https://github.com/openshift/origin/releases/download/v1.5.1/$(OPENSHIFT_ARCHIVE)
OPENSHIFT_SERVER := openshift-server
OPENSHIFT_USER := user
OPENSHIFT_PW := pw
.PHONY: openshift/install
## Installs the Openshift CLI
openshift/install:
	[ -x $(OPENSHIFT) ] || ( \
	echo "Installing Openshift CLI" && \
	mkdir -p $(OPENSHIFT_DIR) && \
	cd $(OPENSHIFT_DIR) &&\
	wget -q $(OPENSHIFT_URL) && \
	tar -xvf ./$(OPENSHIFT_ARCHIVE) &&\
	mv ./*/oc $(OPENSHIFT) &&\
	chmod a+x $(OPENSHIFT) \
		)
	$(OPENSHIFT) version

.PHONY: openshift/login
#log in to OCP cluster
openshift/login:
	$(OPENSHIFT) login --server=$(OPENSHIFT_SERVER) -u $(OPENSHIFT_USER) -p $(OPENSHIFT_PW)
