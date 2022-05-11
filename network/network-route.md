# Route

- Best Effort
- TTL (Time to Live) : 패킷이 폐기될 때까지의 홉(hop)의 개수
- TTL이 0이 되면 해당 패킷은 폐기되고 ICMP Time Exceeded 에러를 송신한 호스트로 보낸다.

## ping

- ping www.example.com
- ctrl + c
- ping -c 3 www.example.com
- ping 명령은 ICMP(Internet Control Message Protocol)를 사용한다.

## tracepath (traces path to a network host discovering MTU along this path)

- tracepath [-nl]
- tracepath www.example.com


## traceroute (print the route packets trace to network host)

- traceroute [-nmpI]
- traceroute www.example.com

## route (show / manipulate the IP routing table)

- route (Kernel IP routing table)
- route add default gw 172.26.16.1
- route add -net 172.26.31.58/20 netmask 255.255.240.0 dev eth0

## ip

- ip route
- default via 172.26.16.1 dev eth0
- ip route add default via 172.26.16.1 dev eth0
