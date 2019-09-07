# Local 개발환경에서 사용할 kafka 세팅하기
- kafka 와 zookeeper 두개를 사용해야하므로, docker-compose 를 사용해야한다.

> https://github.com/Yelp/docker-compose/blob/master/docs/install.md

- docker-compose.yml 파일
```yaml
version: '2'
services:
  zookeeper:
    container_name: local-zookeeper
    image: wurstmeister/zookeeper:3.4.6
    ports:
      - "2181:2181"
  kafka:
    container_name: local-kafka
    image: wurstmeister/kafka:2.12-2.3.0
    depends_on:
      - zookeeper
    ports:
      - "9092:9092"
    environment:
      KAFKA_ADVERTISED_HOST_NAME: 127.0.0.1
      KAFKA_ADVERTISED_PORT: 9092
      KAFKA_CREATE_TOPICS: "test:1:1" # Topic명:Partition개수:Replica개수
      KAFKA_ZOOKEEPER_CONNECT: zookeeper:2181
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
```

## 명령어
#### 실행 및 종료

###### 실행
> docker-compose -f docker-compose.yml up -d

###### 종료

> docker-compose down

#### 로그보기

###### zookeeper 로그보기

> docker container logs local-zookeeper

###### kafka 로그보기

> docker container logs local-kafka


---
## 참고링크 
- https://github.com/wurstmeister/kafka-docker
