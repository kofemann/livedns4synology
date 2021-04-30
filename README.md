# Use Gandi LiveDNS from Synology NAS box

This project aims to provide a dynamic DNS capability for Synology NAS users that
use [Gandi.net](https://www.gandi.net/en) domain name registrar. It based on [LiveDNS RESTful API][1].

## Installation

1. Add python3 package to the Synology box
1. Copy script to `/usr/local/bin/livedns.py` and make it executable
```
$ sudo curl -o /usr/local/bin/livedns.py https://raw.githubusercontent.com/kofemann/livedns4synology/master/livedns.py
$ sudo chmod +x /usr/local/bin/livedns.py
```
1. update /etc.defaults/ddns_provider.conf to add new provider:
```
[Gandi LiveDNS]
        modulepath=/usr/local/bin/livedns.py
        queryurl=Gandi
```

Now on the new provider should be available under `Control Panel -> External Access -> DDNS`

## Configuration

You need to provide the following configuration parameters:

1. FQDN of the host
1. Username, which is ignored
1. Gandy API key

## License

This work is published under [public domain](https://creativecommons.org/licenses/publicdomain/) license.

[1]: https://api.gandi.net/docs/livedns/