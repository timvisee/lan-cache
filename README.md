# Steam cache for LAN-parties
This repository includes a steamcache configuration and steps on how to
configure it for use at LAN-parties.

This is based on steamcache.net

## Usage
* Disable DNS stuff on host:

  ```bash
  sudo systemctl stop systemd-resolved
  sudo systemctl stop bind9
  ```

* Add local IP as DNS server to resolved configuration:

  ```bash
  # File: /etc/resolv.conf
  nameserver 127.0.0.1
  ```

* Configure static IP address on host: `192.168.1.10`
* Clone the repository and start the cache stack:

  ```bash
  # Clone repository
  git clone https://github.com/timvisee/lan-cache.git
  cd lan-cache

  # Start the stack
  ./start

  # Stop the stack after use
  ./stop
  ```
* Make sure to configure the host IP as DNS server in the network DHCP server.