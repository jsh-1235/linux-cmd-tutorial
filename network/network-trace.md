# Route

- Best Effort
- TTL (Time to Live) : 패킷이 폐기될 때까지의 홉(hop)의 개수
- TTL이 0이 되면 해당 패킷은 폐기되고 ICMP Time Exceeded 에러를 송신한 호스트로 보낸다.
- 원격 호스트를 향한 네트워크 경로 표시 (tracepath & traceroute)

## ping (send ICMP ECHO_REQUEST to network hosts)

- 외부 호스트에서 신호를 보내면 신호를 받은 호스트는 응답을 주면서 서로 네트워크가 연결되어 있음을 확인시켜주는 명령어이다.
- ping www.example.com
- ctrl + c
- ping -c 3 www.example.com
- ping 명령은 ICMP(Internet Control Message Protocol)를 사용한다.

## tracepath (traces path to a network host discovering MTU along this path)

- tracepath [-nl]
- tracepath www.example.com


## traceroute (print the route packets trace to network host)

- 목적지 호스트까지의 경로를 표시하고 그 구간의 정보를 기록하는 명령어이다.
- traceroute [-nmpI]
- traceroute www.example.com
- traceroute -m 2 www.example.com

## route (show / manipulate the IP routing table)

- route (Kernel IP routing table)
- route add default gw 172.26.16.1
- route add -net 172.26.31.58/20 netmask 255.255.240.0 dev eth0
