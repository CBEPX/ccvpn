Title: Public API

## Gateway object:

  - **hostname**: *string*, the gateway's hostname.
  - **fqdn**: *string*, its fully qualified domain name.
  - **country**: *string*, ISO 3166-1 alpha-2 country codes. (fr, en, nl, ...)
  - **bandwidth**: *integer*, The bandwidth in bits/second.
  - **ipv4 and ipv6**: *string*, IP addresses of the gateway. Either can be null.
  - **enabled**: *boolean*, true if the gateway is enabled.

Example:

    {"hostname": "fr-poney0",
     "fqdn": "fr-poney0.204vpn.net",
     "country": "fr",
     "bandwidth": 1000000000,
     "ipv4": "195.154.79.147",
     "ipv6": "2001:bc8:3505:1000::1",
     "enabled": true}

## Get a list of Gateway objects:

Parameters:

  - **show_disabled**: *boolean*, should it include disabled gateways?
                       (default: false)
  - **country**: *string*, filter by country code.
  - **hostname**: *string*, filter by hostname.

Python example:

    #!/usr/bin/python
    
    """
    This example prints the name of every enabled gateway
    """

    import json
    import requests

    # GET /api/public/gateways
    r = requests.get('http://vpn.ccrypto.org/api/public/gateways')
    gateways = r.json()
    for gateway in gateways:
        print(gateway['hostname'])
    


