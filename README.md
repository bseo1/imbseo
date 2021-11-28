# Mentta-BrowserQuest

Mentta-BrowserQuest는 오픈소스 게임 엔진인 BrowserQuest를 기반으로 제작한 메타버스 게임 엔진입니다.

([BrowserQuest 깃허브 링크](https://github.com/browserquest/BrowserQuest))

네 가지 주요 부분이 있으며, 위의 세 부분은 기존 BrowserQuest와 유사하고, 클라우드 AI 서비스 적용을 위한 API 서버가 추가되었습니다.

- 서버 : Node.js
- 클라이언트 : 브라우저에서 JavaScript 사용
- 데이터베이스 : Redis
- **API 서버** : Node.js ([깃허브 링크](https://github.com/SangheonYi/mentta_express.git))

본 개발문서는 실행 방법과 수정된 부분에 대해 안내하며, 수정되지 않은 기존의 정보는 [BrowserQuest 깃허브](https://github.com/browserquest/BrowserQuest.git)에서 확인할 수 있습니다.

## 실행 방법

1. 다음 명령어를 통해 필요한 환경을 구축해 줍니다.

```bash
apt-get update -y
apt-get upgrade -y
apt-get install  curl git -y #debian에는 curl을 별도 설치해야 함
curl -fsSL https://deb.nodesource.com/setup_lts.x | bash -
apt-get install nodejs -y #nodejs 설치
apt-get install g++ make memcached libncurses5 redis-server -y 
git clone git://github.com/browserquest/BrowserQuest.git
cd BrowserQuest
npm install -d
```

1. redis 서버를 실행합니다.

```bash
redis-server
```

1. 새 터미널을 열어 아래 명령으로 서버 node를 실행합니다.

```bash
nodemon server.js
```

정상적으로 실행되면 아래와 같이 출력됩니다.

```bash
$ nodemon server.js
This server can be customized by creating a configuration file named: ./server/config_local.json
[Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO Starting BrowserQuest game server...
[Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world1 created (capacity: 200 players).
[Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world2 created (capacity: 200 players).
[Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world3 created (capacity: 200 players).
[Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world4 created (capacity: 200 players).
[Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO world5 created (capacity: 200 players).
[Thu Sep 13 2012 17:16:27 GMT-0400 (EDT)] INFO Server (everything) is listening on port 8000
```
