tcpdump -D // List interfaces available 
tcpdump -i "Interface"  // Captures traffic using the specified interface
tcpdump src "ip"
tcpdump dst "ip"
tcpdump src port "port"
tcpdump dst port "port"
tcpdump "protocol"  // e.g. tcpdump ftp

// Logical operators like and & or can be used // e.g. "tcpdump src port 80 and dst 1.1.1.1"

tcpdump -c 10 // Captures 10 packets then stops
tcpdump -n // Turns off name resolution
tcpdump -w file.pcap // Saves capture to a file
tcpdump -r file.pcap // Opens file with default configs
tcpdump -(v)(vv)(vvv) // Each one increasing in verbosity

S = SYN
P = PSH
F = FIN
R = RST
U = URG 
A = ACK

tcpdump[tcpflag] == x // shows only results with that tcp flag

// Multable tcp flags can be specified by converting all flags to decimal

========================
C  |  E  |  U  |  A  |  P  |  R  |  S  |  F
W |  C  |  R  |  C  |  S  |  S  |  Y  | I
R  |  E  |  G  |  K  |  H  |  T  |  N  | N



e.g
 0     0    0     1       1     0      0     0
========================
C  |  E  |  U  |  A  |  P  |  R  |  S  |  F
W |  C  |  R  |  C  |  S  |  S  |  Y  | I           = 00011000 or 24
R  |  E  |  G  |  K  |  H  |  T  |  N  | N   

tcpdump[tcpflag] == 24

tcpdump -r file.pcap | cut -d ":" -f 1,2,3  // This will filter out everything other then lines 1, 2, 3





