# needs: libssl-dev
#        libiw-dev
#        libnl-dev libnl1
#        curl libcurl3 libcurl3-dev
#
# Hostapd calls this make to run this Makefile without parameters
# So make alone should compile only the the libraries to hostapd
#
# Call:
# * make
# to compile libraries to hostapd and generate the server (to install in the AP) and the client
#
# * make station
# to compile libraries and generate application for the station
#
# * make client
# to compile libraries and generate client test application (send comands to the station and AP)
#
# * make server
# to compile libraries and generate server application (installed in the AP)
#
#
SHELL := /bin/bash

ifndef CC
CC=gcc
endif

CFLAGS = -Wall
INCLUDES = -I. -I/usr/include
LIBS   = -L/usr/lib -lssl -lcrypto -lm -lnl -liw -lpthread

OBJS_FUNCOES =  ../ethanol_functions/utils.o
OBJS_FUNCOES += ../ethanol_functions/80211e.o
OBJS_FUNCOES += ../ethanol_functions/ap_txpower.o
OBJS_FUNCOES += ../ethanol_functions/change_ap.o
OBJS_FUNCOES += ../ethanol_functions/config_hostapd.o
OBJS_FUNCOES += ../ethanol_functions/connect.o
OBJS_FUNCOES += ../ethanol_functions/convert_freq.o
OBJS_FUNCOES += ../ethanol_functions/get_acs.o
OBJS_FUNCOES += ../ethanol_functions/get_cpuinfo.o
OBJS_FUNCOES += ../ethanol_functions/get_dns.o
OBJS_FUNCOES += ../ethanol_functions/get_interfaces.o
OBJS_FUNCOES += ../ethanol_functions/get_meminfo.o
OBJS_FUNCOES += ../ethanol_functions/get_route.o
OBJS_FUNCOES += ../ethanol_functions/get_snr.o
OBJS_FUNCOES += ../ethanol_functions/get_snr_ap.o
OBJS_FUNCOES += ../ethanol_functions/getmac.o
OBJS_FUNCOES += ../ethanol_functions/getnetlink.o
OBJS_FUNCOES += ../ethanol_functions/global_typedef.o
OBJS_FUNCOES += ../ethanol_functions/hostapd_hooks.o
OBJS_FUNCOES += ../ethanol_functions/is_wireless.o
OBJS_FUNCOES += ../ethanol_functions/iw_bitrates.o
OBJS_FUNCOES += ../ethanol_functions/iw_link.o
OBJS_FUNCOES += ../ethanol_functions/iw_powersave.o
OBJS_FUNCOES += ../ethanol_functions/net_statistics.o
OBJS_FUNCOES += ../ethanol_functions/nl80211_socket.o
OBJS_FUNCOES += ../ethanol_functions/noise_with_hostapd.o
OBJS_FUNCOES += ../ethanol_functions/return_ap_in_range.o
OBJS_FUNCOES += ../ethanol_functions/route.o
OBJS_FUNCOES += ../ethanol_functions/setip.o
OBJS_FUNCOES += ../ethanol_functions/signalstrength.o
OBJS_FUNCOES += ../ethanol_functions/sta_link_information.o
OBJS_FUNCOES += ../ethanol_functions/sta_statistics.o
OBJS_FUNCOES += ../ethanol_functions/strlib.o
OBJS_FUNCOES += ../ethanol_functions/time_stamp.o
OBJS_FUNCOES += ../ethanol_functions/utils_str.o
OBJS_FUNCOES += ../ethanol_functions/wapi_avail_freq.o
OBJS_FUNCOES += ../ethanol_functions/wapi_frequency.o
OBJS_FUNCOES += ../ethanol_functions/wapi_getfrequency.o
OBJS_FUNCOES += ../ethanol_functions/wapi_getssid.o
OBJS_FUNCOES += ../ethanol_functions/wapi_quality.o
OBJS_FUNCOES += ../ethanol_functions/wapi_scan2.o
OBJS_FUNCOES += ../ethanol_functions/wapi_ssid.o
OBJS_FUNCOES += ../ethanol_functions/wapi_txpower.o
OBJS_FUNCOES += ../ethanol_functions/wapi_util.o
OBJS_FUNCOES += ../ethanol_functions/wlan_info.o


OBJS = buffer_handler_fun.o ssl_common.o
OBJS+= msg_error.o
OBJS+= msg_common.o
OBJS+= msg_hello.o
OBJS+= msg_bye.o
OBJS+= msg_ping.o
OBJS+= msg_802_11e_enabled.o
OBJS+= msg_ap_ctsprotection_enabled.o
OBJS+= msg_ap_broadcastssid.o
OBJS+= msg_ap_frameburstenabled.o
OBJS+= msg_ap_guardinterval.o
OBJS+= msg_ap_dtiminterval.o
OBJS+= msg_ap_rtsthreshold.o
OBJS+= msg_beacon_interval.o
OBJS+= msg_bytesreceived.o
OBJS+= msg_bytessent.o
OBJS+= msg_packetsreceived.o
OBJS+= msg_packetssent.o
OBJS+= msg_packetslost.o
OBJS+= msg_deauthenticate_user.o
OBJS+= msg_disconnect_user.o
OBJS+= msg_powersavemode.o
OBJS+= msg_delay.o
OBJS+= msg_failed.o
OBJS+= msg_jitter.o
OBJS+= msg_fastbsstransition_compatible.o
OBJS+= msg_association_process.o
OBJS+= msg_snr.o
OBJS+= msg_frequency.o
OBJS+= msg_currentchannel.o
OBJS+= msg_mac.o
OBJS+= msg_radio_wlans.o
OBJS+= msg_channels.o
OBJS+= msg_intf.o
OBJS+= msg_beaconinfo.o
OBJS+= msg_radio_linkstatistics.o
OBJS+= msg_wlan_info.o
OBJS+= msg_channelbandwitdh.o
OBJS+= msg_ipv4_address.o
OBJS+= msg_txpower.o
OBJS+= msg_ap_in_range.o
OBJS+= msg_retries.o
OBJS+= msg_uptime.o
OBJS+= msg_routes.o
OBJS+= msg_ssid.o
OBJS+= msg_memory.o
OBJS+= msg_cpu.o
OBJS+= msg_scan.o
OBJS+= msg_channelinfo.o
OBJS+= msg_inform_beacon.o
OBJS+= msg_interferencemap.o
OBJS+= msg_request_begin_association.o
OBJS+= msg_fragmentationthreshold.o
OBJS+= msg_tx_bitrates.o
OBJS+= msg_tx_bitrate.o
OBJS+= msg_noiseinfo.o
OBJS+= msg_sta_link_information.o
OBJS+= msg_supportedinterface.o
OBJS+= msg_location.o
OBJS+= msg_conf_ssid_radio.o
OBJS+= msg_statistics.o
OBJS+= msg_sta_statistics.o
OBJS+= msg_vap_create.o
OBJS+= msg_set_snr_threshold.o
OBJS+= msg_set_snr_interval.o
OBJS+= msg_acs.o
OBJS+= list_devices.o list_aps.o list_stations.o
OBJS+= msg_snr_threshold_reached.o
OBJS+= msg_changed_ap.o
OBJS+= msg_mean_sta_stats.o
OBJS+= msg_station_trigger_transition.o
OBJS+= msg_tos.o
OBJS+= msg_mtu.o
OBJS+= msg_txqueuelen.o

PROG = ethanol_station ethanol_client ethanol_server

all: hostapd

%.o: %.c
	@echo ' CC : ' $@
#	@echo $(CC) $(CFLAGS) -c -o $@ $< $(LIBS) $(INCLUDES)
	@$(CC) $(CFLAGS) -c $< -o $@ $(LIBS) $(INCLUDES)

funcoes:
	$(MAKE) -C ../ethanol_functions

client: funcoes $(OBJS)
	rm -f ethanol_client
#	@echo $(CC) $(CFLAGS) -o $@ $@.c $(LIBS) $(INCLUDES)
	@$(CC) $(CFLAGS) $(OBJS) $(OBJS_FUNCOES) -o ethanol_$@ ssl-client.c $(LIBS) $(INCLUDES)

client_debug: CFLAGS += -DDEBUG
client_debug: client
	@echo ' CC client com DEBUG'

server: funcoes $(OBJS)
	rm -f ethanol_server
	@$(CC) $(CFLAGS) -lpthread -c -o ssl-server.o ssl-server.c $(LIBS) $(INCLUDES)
	@echo ' CC: ' $@
#	@echo ">>$(CC)" $(CFLAGS) -o $@ $@.c $(LIBS) $(INCLUDES)
	@$(CC) $(CFLAGS) $(OBJS) $(OBJS_FUNCOES) ssl-server.o -o ethanol_$@ run-server.c $(LIBS) $(INCLUDES) -lpthread -lm -liw

server_debug: CFLAGS += -DDEBUG
server_debug: server
	@echo ' CC server com DEBUG'

server_handover: CFLAGS += -DDEBUG -DHANDOVER
server_handover: server
	@echo ' CC server com DEBUG e HANDOVER'


# this clause compiles the libraries to hostapd
# generates two executables: a client and a server
hostapd: clean
	rm -f $(PROG)
	$(MAKE) client
	$(MAKE) server

clean:
	rm -f *o *.~* *~
	$(MAKE) -C ../ethanol_functions clean

clear: clean
	rm -f $(PROG)

station: CFLAGS += -DPROCESS_STATION
station: clean funcoes $(OBJS)
	$(CC) $(CFLAGS) -lpthread -c -o ssl-server.o ssl-server.c $(LIBS) $(INCLUDES)
	@echo ' CC: ' $@
#	@echo ">>$(CC)" $(CFLAGS) -o $@ $@.c $(LIBS) $(INCLUDES)
	$(CC) $(CFLAGS) $(OBJS) $(OBJS_FUNCOES) ssl-server.o -o ethanol_$@ run-station.c $(LIBS) $(INCLUDES) -lpthread -lm -liw

station_debug: CFLAGS += -DDEBUG
station_debug: station
	@echo ' CC station com DEBUG'

station_handover: CFLAGS += -DDEBUG -DHANDOVER
station_handover: station
	@echo ' CC station com DEBUG e HANDOVER'

teste: funcoes $(OBJS)
	@echo ' CC: ' $@
	@echo ">>$(CC)" $(CFLAGS) -o $@ $@.c $(LIBS) $(INCLUDES)
	$(CC) $(CFLAGS) $(OBJS) $(OBJS_FUNCOES) -o $@ $@.c $(LIBS) $(INCLUDES) -lpthread -lm -liw


debug: clear
	@echo "compilaçao com debug"
	@echo "vai gerar tres programas: ethanol_server (para ap), ethanol_client (para enviar comandos) e ethanol_station (para estação)"
	$(MAKE) clean
	@printf "\n\n\nCompilando client\n"
	$(MAKE) client_debug
	@printf "\n\n\nCompilando server\n"
	$(MAKE) server_debug
	$(MAKE) clean
	@printf "\n\n\nCompilando station\n"
	$(MAKE) station_debug


handover:
	@echo "CC handover"
	@echo "vai gerar dois programas: ethanol_server (controlador) e ethanol_station (para estação)"
	@echo "para AP usar a versão gerada do hostapd com 'make ethanol'"
	@printf "\n\n"
	@rm -f ethanol_server
	@rm -f ethanol_station
	$(MAKE) clean
	@printf "\n\n\CC server\n"
	$(MAKE) server_handover
	$(MAKE) clean
	@printf "\n\n\CC station\n"
	$(MAKE) station_handover
