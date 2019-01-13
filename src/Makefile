obj-m := tcp_airium.o

all:
	make -C /lib/modules/`uname -r`/build M=`pwd` modules CC=/usr/bin/gcc

clean:
	make -C /lib/modules/`uname -r`/build M=`pwd` clean

install:
	install tcp_airium.ko /lib/modules/`uname -r`/kernel/net/ipv4
	insmod /lib/modules/`uname -r`/kernel/net/ipv4/tcp_airium.ko
	depmod -a

uninstall:
	rm /lib/modules/`uname -r`/kernel/net/ipv4/tcp_airium.ko
	modprobe -rf tcp_airium
