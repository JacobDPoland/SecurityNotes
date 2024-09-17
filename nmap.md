flags:
- `-sn` disable port scanning
- `-Pn` disable host discovery
- `-n` no dns resolution
- `-v` increase verbosity
- `--traceroute` track each hop the packet takes
- `-iL <inputfilename>` scan the address from the provided file
- `-iR` scan a random sampling of hosts
- `-d` debug

**nmap creates packets in certain ways that are trackable**
**scapy might make it easier to hide your digital footprint**


Layer 4:
- `nmap -PS<port list> target` TCP SYN Ping
	- This sends a SYN packet (the first step in the TCP handshake) to the target. 
	- If the target responds with a SYN/ACK, it indicates that the host is active. 
	- If the target responds with a RST (reset), the port is closed, but the host is still considered responsive. 
	- If no response is received, the host is considered down or blocked by a firewall.
- `nmap -PA<port list> target` TCP ACK Ping
- `nmap -PU<port list> target` UDP Ping
