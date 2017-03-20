# watchnet
Monitors a network interface connection, notifies changes to the user and reconnects the interface when possible.

It's a simple and lightweight utility to keep the network interfaces allways connected.
Teams with the classic /etc/network/interfaces configuration and the packages ifupdown, ifplugd, guessnet, wpa-supplicant. Required packages are also bash, iproute2 and systemd.

Monitors cable and wireless interfaces, verifying connection reliability.
The user will be notified when an interface is connected or disconnected.
Even works in a configuration with only one wireless access point or one Ethernet port but also in complex configurations with multiple network interfaces and access points; most part of the magic is done by the other packages: ifplugd, guessnet, wpa-supplicant.

This package fills the actually existing gap to monitor a network interface and reconnect it, it doesn't have a graphical interface, all configuration is done via text files. It's lightweigth and avoids installing most heavy, processor and disk consumming network manager utilities.

Examples:

The superuser can request the daemon to connect and/or watch an already connected interface:

/usr/sbin/watchnetd ifname

The file /etc/network/interfaces can request the daemon to monitor an interface:

iface eth1 inet dhcp

    post-up /usr/sbin/watchnetd eth1

Or a mapping in the file /etc/network/interfaces can select a guessnet configuration:

mapping wlan0

    script /usr/sbin/watchnet-ifupdown


iface wlan0-casa inet dhcp

    wpa-ssid "jordipujol"

    ...

See most detailed configurations in the samples directory, .

The daemon program will allways fork, to debug it we must set the DEBUG variable in /etc/watchnet.conf and look for xtrace files in /tmp.
