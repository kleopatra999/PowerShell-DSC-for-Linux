TOP = .

include $(TOP)/config.mak

DIRECTORIES = omiutils
DIRECTORIES += codec/mof
DIRECTORIES += codec/mof/parser
DIRECTORIES += dsc/engine/EngineHelper
DIRECTORIES += dsc/engine/ca/CAInfrastructure
DIRECTORIES += dsc/engine/ca/CALogInfrastructure
DIRECTORIES += dsc/engine/ConfigurationManager
DIRECTORIES += dsc/engine/ModuleLoader/ModuleLibrary
DIRECTORIES += dsc/engine/lcm
DIRECTORIES += dsc/engine/ConsistencyInvoker
TESTDIRS += dsc/tests/Engine/TestProvider
TESTDIRS += dsc/tests/Engine/TestFileProvider
TESTDIRS += dsc/tests/Engine/CA
TESTDIRS += dsc/tests/Engine/ModuleLoader
TESTDIRS += dsc/tests/Engine/LCM
TESTDIRS += dsc/tests/Engine/E2E

include $(OMI)/mak/rules.mak

deploydsc:
	mkdir -p $(CONFIG_SYSCONFDIR)/dsc
	mkdir -p $(CONFIG_SYSCONFDIR)/dsc/configuration
	mkdir -p $(CONFIG_SYSCONFDIR)/dsc/configuration/schema
	mkdir -p $(CONFIG_SYSCONFDIR)/dsc/configuration/schema/MSFT_LogResource
	mkdir -p $(CONFIG_SYSCONFDIR)/dsc/configuration/baseregistration
	mkdir -p $(CONFIG_SYSCONFDIR)/dsc/configuration/registration
	mkdir -p $(CONFIG_SYSCONFDIR)/dsc/configuration/registration/MSFT_LogResource
	mkdir -p $(CONFIG_SYSCONFDIR)/dsc/configuration/BuiltinProvCache
	mkdir -p $(CONFIG_DATADIR)/dsc
	mkdir -p $(CONFIG_DATADIR)/dsc/configuration
	mkdir -p $(CONFIG_DATADIR)/dsc/configuration/schema
	mkdir -p $(CONFIG_DATADIR)/dsc/configuration/registration
	cp  -r $(TOP)/dsc/mof/OMI_BaseResourceUE.mof $(CONFIG_SYSCONFDIR)/dsc/configuration/baseregistration/baseresource.schema.mof
	cp  -r $(TOP)/dsc/mof/MSFT_DSCMetaConfiguration.mof $(CONFIG_SYSCONFDIR)/dsc/configuration/baseregistration/MSFT_DSCMetaConfiguration.mof
	cp  -r $(TOP)/dsc/mof/MSFT_LogResource.schema.mof $(CONFIG_SYSCONFDIR)/dsc/configuration/schema/MSFT_LogResource
	cp  -r $(TOP)/dsc/mof/MSFT_LogResource.registration.mof $(CONFIG_SYSCONFDIR)/dsc/configuration/registration/MSFT_LogResource
	$(BINDIR)/omireg -n "dsc" $(LIBDIR)/libdsccore.so