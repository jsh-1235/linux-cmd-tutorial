# yum (Yellowdog Updater Modified)

- RPM 명령의 패키지 의존성 문제를 해결
- 인터넷을 통하여 필요한 파일들을 저장소(Repository)에서 다운로드 해서 설치하는 방식
- 또한 의존성을 가지는 다른 RPM 패키지까지 알아서 다운로드하여 설치한다.
- Update된 패키지들을 검사하고, 다운로드하여 설치까지 자동으로 진행한다.

## command

- sudo yum update (모든 패키지 업데이트)
- yum check-update (설치된 패키지 중에 업데이트가 가능한 패키지 목록 출력)

- yum -y (설치 여부를 묻지 않고 바로 설치한다.)
- yum install tree
- yum update tree
- yum remove tree
- yum info tree
