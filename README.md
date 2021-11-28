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
- `RxSwift`
- `RxCocoa`
- `RxRelay`
- CentOS7 + MosquittoMQTT + Mysql

 ## 적용한 주요 Layout
- `PageViewController`
- `NavigationController`

 ## 한계점
- Cocoa MQTT를 Background 상태에도 실행해보려 AppDelegate에 mqtt 객체를 생성하였지만 Background 알람기능을 개발하는데 실패하였다.  

## MVVM 구조
채팅기능에 MVVM 구조를 적용

### 1. mqtt 서버에서 전송하는 원시데이터 수신
``` swift
class MQTTRepo{
 var chatString = PublishSubject<[String]>()
 .
 . 
 func mqtt(_ mqtt: CocoaMQTT, didReceiveMessage message: CocoaMQTTMessage, id: UInt16) {
        chatString.onNext([message.topic,message.string]) // 원시데이터 방출
     }
 }
```
### 2. 원시데이터를 chatData 구조체로 가공 (Model)
``` swift
class ChatModel{
 var chatData = PublishSubject<ChatData>()
 var mqttRepo = MQTTRepo()
.
.
mqttRepo.chatString // 원시데이터를 구독
            .observe(on: ConcurrentDispatchQueueScheduler(qos: .default)) // 컨커런트 작업
            .subscribe(onNext:{
            self.chatData.onNext(self.makeChatData($0[0], $0[1])) // 원시데이터를 chatData 구조체로 가공하여 방출
        }).disposed(by: disposeBag)
}
```

## 주요 구현 장면

### 1. 카운트다운 설정기능 
![ezgif-1-533fb719b1f2](https://user-images.githubusercontent.com/42457589/142845629-868fbcc7-0c99-4b85-a2aa-97c0d08707c5.gif)
![ezgif-1-fbd363b5e6c9](https://user-images.githubusercontent.com/42457589/142845693-7ff0b292-fed9-4f5a-968e-36f1cd566f84.gif)


시작날을 카운트다운 한다.


### 2. 실시간 채팅기능
![endure4](https://user-images.githubusercontent.com/42457589/143208926-4fad4b46-d6fc-4053-89f3-ee5a2c3f14b4.gif)

MQTT 서버를 통해 실시간 채팅을 한다. 채팅 데이터는 MQTT 서버 DB에 저장된다.


