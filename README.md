# FastAPI-sample-app

## yaml 파일 작성법

### version 
* docker-compose의 버전을 명시한다.
```
version: "3.9"
```
### service
* 각 생성할 컨테이너를 서비스에 선언
* 컨테이너의 depth는 ```space``` 2칸
* 컨테이너의 속성값은 컨테이너 depth에서 ```space``` 2칸
```
services: 
  db:
    image: postgres:13
    ports:
      - "5432:5432"
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
      POSTGRES_DB: postgres
    restart: always
    volumes:
      - pgdata:/var/lib/postgresql/data
```
* db: 컨테이너 명 (container-name: )으로 지정
* ports: 포트포워딩 "5050:80" -> 호스트의 5050 포트와 컨테이너의 80 포트포워딩
  * 포트 선언 시 ""는 습관적으로 해준다. 10:10 을 시간으로 인식하는 경우가 있음
* environment: 컨테이너의 환경 변수 설정
* restart: 오류 발생하거나 컨테이너가 종료 시 항상 재시작 한다.
* volumes: host의 볼륨 설정
* depends_on: depends on에 선언된 컨테이너가 실행한 후에 해당 컨테이너를 실행한다.
  * 다만 컨테이너 구동이 완료된 시점은 다를 수 있음
      
 
