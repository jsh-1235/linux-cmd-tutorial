# DNS

- www.example.com. (sub-domain.second-level-domain.top-level-domain.root-domain)
- . (Root Domain)
- com (TLD : Tob Level Domain, gTLD, ccTLD : 국가 코드 최상위 도메인)
- DNS는 분산형 계층 데이터베이스 시스템으로 각 도메인은 특정 권위(Authoritative)를 지닌 서버가 관리한다.
- 각 네임 서버에는 캐시가 있지만 캐시에 데이터가 없을 경우 최상위 도메인을 관리하는 서버에 문위하면 권위를 지닌 서버까지 도달 할 수 있다.

## domain name structure

- www.naver.com
  - www : sub domain
  - naver.com : host name

## dns server

- cat /etc/resolv.conf (DNS Server)
- nameserver 172.26.16.1

## dig ( DNS lookup utility)

- dig bt-products.ga
- dig bt-products.ga ns
- dig @ns01.freenom.com. bt-products.ga ns
- dig 104.155.29.241
- dig 104.155.29.241 ns
- dig 15.164.80.55 ns

## nslookup (query Internet name servers interactively)

- 도메인명으로 IP 주소를 조회하거나 또는 IP 주소로 도메인명을 조회하는 명령어이다.
- nslookup bt-products.ga
- nslookup dns.google.
- nslookup 8.8.8.8


## host (DNS lookup utility)

- host bt-products.ga
- host -v bt-products.ga (dns 정보 표시)

## hosts file

- C:\Windows\System32\drivers\etc
- cat /etc/hosts
- cat /etc/resolv.conf
- host localhost

## whois (client for the whois directory service)

- whois bt-products.ga
- whois hanbit.co.kr
- whois naver.com
- whois -h whois.kisa.or.kr hanbit.co.kr
