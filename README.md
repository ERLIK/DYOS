# DYOS
<h1>DYOS - Port Scanner</h1>
<p>
DYOS (Defend your own system) is a vulnerability detection and attack tool. According to the parameters given by
the user, it performs operations such as scanning type, attack, whether or not to extract data from the web.

* Can do port scanning.
* It collects the version information of the applications running on the ports it scans.
* Searches if the collected versions have a known vulnerability.
* It tells the user the reason for this vulnerability and how to fix it.
* According to the user's request, these vulnerabilities can be exploited.
</p>

<h2>Targeted scan types</h2>

        # TCP SYN SCAN
        # In this type of scan, in which the source machine starts by sending a TCP SYN flagged packet to the target machine, during the scan
        # most of the ports will probably be closed. When it is off, the target machine returns the RST + ACK flagged packet.
        # When it is on, the SYN + ACK flagged packet will be returned. The source machine breaks the connection by sending a RST flagged packet.
        # and thus the triple handshake is not completed

        # FIN SCAN
        # FIN Scan related frames are unusual because they are sent to the target machine without an initial TCP handshake.
        # If the FIN flagged packet sent by the source machine comes to a closed port of the target machine, the target machine is RST + ACK
        # returns the flagged packet. If the port is loose, no response will be returned from the target machine.

        # XMAX TreeScan
        # The packet that the source machine will set the URG, PSH, and FIN flags in TCP frane is sent to the target machine.
        # The answers that the target machine will return are the same as FIN Scan. URG, PSH and FIN to be sent by the welding machine
        If the # flagged packet arrives on a closed port of the target machine, the target machine will return the RST + ACK flagged packet.
        # If the port is open, there will be no response.

        # In this scan type, where the source machine will send a single ICMP Echo request packet to the target machine, the IP address can be accessed.
        # and unless ICMP filtering is present, the target machine will return an ICMP Echo response.
        # If the target machine is not reachable or the filterer is filtering ICMP packets, the target machine does not respond.
        # will not return.

        # Version Detection Scan
        # Version Detection works with any type of scan that can find information on all ports.
        # TCP SYN for authorized users (root, admin), unauthorized users if no scan type is specified
        Run TCP Connect Scan for #. If an open port is found, Version Detection Scan will run the search process on the target machine.
        # starts it. It can get as much information as it can by communicating directly with the applications of the target machine.
        # works.
