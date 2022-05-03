
# Port

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

## nc (Remote port check)

- nc -zv localhost 80
- nc -zv daum.net 80
