# 인내타이머

## 주요기능

- 금연 ,금주 등 날짜 카운트 기능
- MQTT 서버와 통신하여 실시간 채팅하는 기능

## 수행역할
- 총제작

## 사용한 기술
- `Swift 5`, `Xcode 13`
- `CocoaMQTT`
- CentOS7 + MosquittoMQTT + Mysql
 
## 주요 구현 장면

### 1. 카운트다운 설정기능 
![bt_rs](https://user-images.githubusercontent.com/42457589/132491009-ab3fbeb9-16f6-42fe-97bd-aa3f0f201e50.gif)  
시작날을 카운트다운 한다.

### 2. 실시간 채팅기능
![crop](https://user-images.githubusercontent.com/42457589/132491006-89d419a6-0604-41d8-beb2-e88d7cc8fe6c.gif)  
MQTT 서버를 통해 실시간 채팅을 한다. 채팅 데이터는 MQTT 서버 DB에 저장된다.


