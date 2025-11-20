# ScoreMaster configuration

ScoreMaster can be run with or without Electronic Bonus Claiming (EBC). Without involves manual inspection of bonus claims usually at the end of a rally. With EBC, claims are submitted and collected electronically and assessed by judges throughout the rally.

The use of EBC means that internet access is necessary on the server machine.

## Basic hosting

The software consists of a small number of binary executables and can be made available to run on Windows, iOS or Linux. The program sources, written in [Go](https://go.dev/), are available from public repositories so are easily customised by anyone with the relevant technical skills.

A Windows laptop is possibly the simplest setup.

## Laptop + Hotel WiFi + live EBC

When configured with live EBC fetching the SM server machine needs access to the internet in order to retrieve emails. Local area networking is generally disabled using the hotel-provided WiFi. This is not a problem when a single machine is used to conduct all scoring activities but if multiple device access is needed a private wireless router needs to be configured to provide the LAN capability.

Any commercial router will do. It will need to be configured in advance to operate on a network segment different to the hotel's scheme.

The procedure is for the server to connect to the hotel WiFi (or a mobile phone hotspot) in the usual way then to be **cabled** to the private router. Make a note of the server's cabled IP address.

Have other devices connect to the private router's WiFi. They will not have internet access but they will be able to browse to the server using the noted IP address.

## Public web hosting + live EBC

The best solution is to use either a private server or a virtual private server, available from a wide range of ISPs. Linux is the preferred OS as it will be cheaper and more flexible than other OSes.