
# Port

- cat /etc/services | grep ssh
- cat /etc/services | more

## ss (another utility to investigate sockets)

- ss [-salntux]
- ss -a
- ss -s (각 프로토콜의 통계 정보 표시)
- ss -t (tcp)
- ss -u (utp)
- ss -x (UNIX 도메인 소켓 정보 표시)
- ss | grep tcp

## netstat (Print network connections, routing tables, interface statistics, masquerade connections, and multicast memberships)

- netstat
- netstat -tnlp
- netstat -lntup
- netstat -nap | grep LISTENING

## lsof (list open files)

- lsof
- lsof -i
- lsof -i -nP
- lsof -i -nP | grep LISTEN

## nmap (Network exploration tool and security / port scanner)

- nmap localhost
- nmap -PN localhost -p80 | grep ^80
- nmap -PN localhost -p22 | grep ^22
- nmap -PN daum.net -p80 | grep ^80
- nmap -PN daum.net -p22 | grep ^22

## nc (arbitrary TCP and UDP connections and listens)

- nc -zv localhost 80
- nc -zv localhost 22
- nc -zv ec2-15-164-95-222.ap-northeast-2.compute.amazonaws.com 80
- nc -zv ec2-15-164-95-222.ap-northeast-2.compute.amazonaws.com 22

## tcpdump (dump traffic on a network)

- 네트워크 인터페이스에서 트랙픽 데이터 취득하기
- tcpdump
- sudo tcpdump port http
- sudo tcpdump -v port http
- sudo tcpdump -w tcpdump.log port http
- sudo tcpdump port http and src host www.example.com
- sudo tcpdump -w tcpdump.log (Write)
- sudo tcpdump -r tcpdump.log (Read)
- ctrl + c
