# ScoreMaster configuration

Electronic Bonus Claiming, EBC, introduces some additional constraints to the hosting options. Firstly, internet access is necessary on the server machine and secondly. multiuser access options need some thought.

## Hotel WiFi + live EBC

When configured with live EBC fetching the SM server machine needs access to the internet in order to retrieve emails. Local area networking is generally disabled using the hotel-provided WiFi. This is not a problem when a single machine is used to conduct all scoring activities but if multiple device access is needed a private wireless router needs to be configured to provide the LAN capability.

Any commercial router will do. It will need to be configured in advance to operate on a network segment different to the hotel's scheme.

The procedure is for the server to connect to the hotel WiFi (or a mobile phone hotspot) in the usual way then to be **cabled** to the private router. Make a note of the server's cabled IP address.

Have other devices connect to the private router's WiFi. They will not have internet access but they will be able to browse to the server using the noted IP address.

## Public webhosting + live EBC

Without EBC, any standard web hosting package will do. The requirements are PHP and a webserver, almost universally available.

With EBC it's necessary to run a binary executable service as well as the standard application. The best solution is either to publish using a Virtual Private Server, available from a wide variety of ISPs, or to make a private server accessible from the internet.