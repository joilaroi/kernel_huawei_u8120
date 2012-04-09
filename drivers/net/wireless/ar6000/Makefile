REV ?= 2

PWD := $(shell pwd)

EXTRA_CFLAGS += -I$(src)/include

EXTRA_CFLAGS += -DLINUX -D__KERNEL__ \
                -DTCMD -DSEND_EVENT_TO_APP -DUSER_KEYS \
                -DNO_SYNC_FLUSH -DWAPI_ENABLE #\
                -DMULTIPLE_FRAMES_PER_INTERRUPT -DAR6000REV$(REV) \
                -DBLOCK_TX_PATH_FLAG \

EXTRA_CFLAGS += -DHTC_RAW_INTERFACE
EXTRA_CFLAGS += -DEEPROM_FILE_USED
EXTRA_CFLAGS += -DANDROID_ENV
EXTRA_CFLAGS += -DKERNEL_2_6
CFLAGS_REMOVE_ioctl.o = -Wframe-larger-than=1024

obj-$(CONFIG_AR6000_WLAN) += ar6000.o

ar6000-objs += htc/ar6k.o      		   \
	       htc/ar6k_events.o 	   \
               htc/htc_send.o       	   \
               htc/htc_recv.o       	   \
               htc/htc_services.o          \
               htc/htc.o     		   \
               hif/hif.o     		   \
               bmi/bmi.o                   \
               wmi/wmi.o                   \
               ar6000/ar6000_drv.o         \
               ar6000/ar6000_raw_if.o	   \
               ar6000/netbuf.o		   \
               ar6000/wireless_ext.o	   \
               ar6000/ioctl.o		   \
               ar6000/engine.o		   \
               ar6000/eeprom.o		   \
               miscdrv/common_drv.o	   \
               miscdrv/credit_dist.o	   \
               wmi/wmi.o                   \
               wlan/wlan_node.o            \
               wlan/wlan_recv_beacon.o     \
               wlan/wlan_utils.o

EXTRA_LDFLAGS += --strip-debug


