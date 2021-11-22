# 인내타이머
- 개인적인 프로젝트

## 주요기능

- 금연 ,금주 등 날짜 카운트 기능
- MQTT 서버와 통신하여 실시간 채팅하는 기능

## 수행역할
- 총제작 및 배포
- MQTT + CentOS 서버 설치 및 제작

## 사용한 기술
- `Swift 5`, `Xcode 13`
- `CocoaMQTT`
- CentOS7 + MosquittoMQTT + Mysql
 
## 주요 구현 장면

### 1. 카운트다운 설정기능 
![image](https://user-images.githubusercontent.com/42457589/142844969-5c6cbacf-eb65-4f9f-a2c8-d6605418ad02.png)
![image](https://user-images.githubusercontent.com/42457589/142845270-6dc90bf7-fcf1-4307-ab1d-9cbea8ea8999.png)

시작날을 카운트다운 한다.

### 2. 실시간 채팅기능
![image](https://user-images.githubusercontent.com/42457589/142845099-91e7f510-56fd-4c87-b0af-23737fd518ee.png)  
MQTT 서버를 통해 실시간 채팅을 한다. 채팅 데이터는 MQTT 서버 DB에 저장된다.


