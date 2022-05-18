# docker

## ubuntu

- sudo apt-get remove docker docker-engine docker.io containerd runc
- sudo apt-get update
- sudo apt-get install ca-certificates curl gnupg lsb-release

- curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
- echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

- sudo apt-get update
- sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

- docker -v
- docker version
- docker images
- docker search nginx:latest

## docker compose (install)

- sudo curl -L "https://github.com/docker/compose/releases/download/1.26.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
- sudo chmod +x /usr/local/bin/docker-compose
- docker-compose version

- docker-compose up -d
- docker-compose -f docker-compose-local.yml up
- docker-compose down

- docker-compose start web
- docker-compose stop web

- docker-compose exec db psql postgres postgres
- docker-compose run web env

- docker-compose ps
- docker-compose logs -f web

## docker compose (Orchestration)

- 도커 명령어를 파일로 관리해서 복잡한 도커 컨테이너 및 도커 네트워크를 구성하기에 용이하다는 것이다!

- docker run -it -p 8080:80 --rm -v $(pwd):/usr/share/nginx/html/ nginx
- docker-compose.yml

