RFC - Request for Comments
* Defines how protocols should talk to each other
* Hackers don't have to follow the RFC's
* Creating packets not compliant with the RFC's can make the system do thing it is not supposed to in order to expose vulnerabilities
* hPing3 abuses bad packets to perform DDOS attacks

OSI Model
- Layer 1 - physical wires
- Layer 2 - Data Link
	- Switches
	- MAC addresses
- Layer 3 - Network
	- IP
- Layer 4 **Transport**: TCP, UDP
- Layer 5 **Session**: Manages sessions or connections between applications (e.g., session establishment, maintenance).
- Layer 6 **Presentation**: Formats and encrypts data for the application layer (e.g., data translation, encryption).
- Layer 7 **Application Layer**: Interfaces with the end-user applications (e.g., HTTP, FTP, email protocols).