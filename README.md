# 📌 산돌이 Repository Template  

## 📂 개요

산돌이 프로젝트에 사용되는 `AMQP` (`RabbitMQ`) 관련 설정 레포지토리 입니다.

`RabbitMQ에서` 사용되는 `Exchange`, `Queue들의` 이름이 충돌 되지 않게 중앙 관리하는 레포지토리입니다

---

## 📌 프로젝트 구조  

- Docker compose 파일
- Exchange, Queue이름을 명시할 .env.amqp 파일

---

## 📌 문서  

- [직접 정리한 RabbitMQ 사용 설명서](https://www.notion.so/1a28dd105783807da114e6f4b01baf50?pvs=4)

---

## 📌 사용 방법 및 실행 방법

- 해당 레포지토리를 이용해 같은 AMQP 환경에서 이벤트를 구독, 발행 할수 있도록 합니다.
- 해당 레포지토리를 서브 레포로 설정후 사용할 exchange, queue 이름을 .env.amqp 에 추가합니다.

```bash
# 본인 레포지토리에 서브레포 설정하기
git submodule add -f -b main https://github.com/teamSANDOL/sandol_amqp.git

# submodule이 업데이트 되었을때 (main 브랜치의 최신 커밋이 바뀌었을 때)
git submodule update --remote --recursive

# 본인 레포지토리에 서브레포를 설정했다는 가정하에
docker compose -f docker-compose.yml -f {서브레포이름}/docker-compose.yml up -d --build
# 또는 (프로젝트안 모든 docker-compose.yml 파일들을 compose up)
docker compose $(for f in docker-compose.yml **/docker-compose.yml; do echo "-f $f " ;done) up -d --build
```

## 📌 문의  

- **(디스코드 채널 링크를 삽입하세요)**

---
🚀 **산돌이 프로젝트와 함께 효율적인 개발 환경을 만들어갑시다!**  
