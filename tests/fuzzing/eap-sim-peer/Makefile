ALL=eap-sim-peer
include ../rules.include

CFLAGS += -DIEEE8021X_EAPOL
CFLAGS += -DCONFIG_SIM_SIMULATOR

OBJS += $(SRC)/eap_peer/eap_sim.o
OBJS += $(SRC)/eap_common/eap_sim_common.o
OBJS += $(SRC)/eap_common/eap_common.o
LIBS += $(SRC)/crypto/libcrypto.a
LIBS += $(SRC)/utils/libutils.a

OBJS += eap-sim-peer.o

_OBJS_VAR := OBJS
include ../../../src/objs.mk

_OBJS_VAR := LIBS
include ../../../src/objs.mk

eap-sim-peer: $(OBJS) $(LIBS)
	$(Q)$(LDO) $(LDFLAGS) -o $@ $^ $(LIBS) $(ELIBS)
	@$(E) "  LD " $@

clean: common-clean
	rm -f eap-sim-peer *~ *.o *.d ../*~ ../*.o ../*.d
