# watchnet
Monitors the network interface connection, notifies changes to the user and reconnects the interface when possible.

Is a simple and lightweight utility to keep the network interfaces allways connected.
It teams with the classic /etc/network/interfaces configuration, and the packages ifupdown, ifplugd, guessnet, wpa-supplicant. It works with cable and wireless networks.
The user will be notified when an interface is connected or disconnected.
Even works in a configuration with one wireless access point or only one Ethernet port but also in complex configurations with multiple network interfaces and access points; most part of the magic is done by the other packages: ifplugd, guessnet, wpa-supplicant.

This package fills the actually existing gap to monitor a network interface and reconnect it, it doesn't have a graphical interface, all configuration is done via text files. It's lightweigth and avoids installing most heavy and disk consumming network manager packages.
