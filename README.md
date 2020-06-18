# netcut

To modify packet flow in target to our machine while in MITM attacks

Usage:

First Terminal:

pip install netfilterqueue

python netcut.py

Second Terminal:
Outside the Machine:

iptables -I FORWARD -j NFQUEUE --queue-num 0

Inside the machine:

iptables -I OUTPUT -j NFQUEUE --queue-num 0

iptables -I INPUT -j NFQUEUE --queue-num 0

python arp_spoofer.py

Third Terminal:

echo 1 > /proc/sys/net/ipv4/ip_forward

All Finished:

iptables --flush


