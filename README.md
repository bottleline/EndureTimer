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
![endure1](https://user-images.githubusercontent.com/42457589/142130083-e700496d-308c-429c-a82f-7c4b5629eaa1.gif)  
시작날을 카운트다운 한다.

### 2. 실시간 채팅기능
![endure2](https://user-images.githubusercontent.com/42457589/142130103-084805f2-65d0-4ab7-ae2b-ef5de8bee636.gif)  
MQTT 서버를 통해 실시간 채팅을 한다. 채팅 데이터는 MQTT 서버 DB에 저장된다.


