---
title: 네트워크 (1) 인터넷과 프로토콜
date: 2020-11-16 20:10:11
category: Network
thumbnail: { thumbnailSrc }
draft: false
---


## What's the Internet : "nuts and bolts" view
### 구성요소로 본 인터넷
### end systems(종단 시스템) = hosts(호스트)
-> running network apps 장치 (네트워크 어플리케이션을 수행하는 장치)


end system(종단 시스템)은 **communication link(통신 링크)**와 **packet switch(패킷 스위치)**의 네트워크로 연결된다.  
-> 이 때 각각의 링크들은 다양한 transmission rate(전송률)을 이용하여 데이터 전송 


 

한 end system이 다른 end system으로 보낼 데이터를 가지고 있을 때, 송신 end system은 그 데이터를 **segment(세그먼트)**로 나누고 각 segment에 **header(헤더)**를 붙인다. 이렇게 만들어진 정보 패키지를 **packet(패킷)**이라 부른다.  packet은 목적지 end system으로 네트워크를 통해 보내지고, 목적지에서 원래의 데이터로 다시 조립된다. 

 
<br/>
 

 ### 패킷 스위치 (packet switch)

**packet switch(패킷 스위치)**는 입력 통신 링크의 하나로 도착하는 packet을 받아서 출력 통신 링크의 하나로 그 **패킷을 전달**한다. 가장 널리 사용되는 두 가지 종류로는 **router(라우터)**와 **link-layer switch(링크 계층 스위치)**가 있다. 

- link-layer switch는 보통 **access network(액세스 네트워크)**에서 사용

- router는 **network core(네트워크 코어)**에서 사용 

 
<br/>

### ISP(Internet Service Provider)
end system은 **ISP(Internet Service Provider)**를 통해 인터넷에 접속한다.  

- 가정 ISP, 법인 ISP, 대학 ISP, 셀룰러 데이터 ISP 등 다양하게 존재 
- 각 ISP는 **패킷 스위치와 통신 링크로 이루어진 네트워크**이다. 
- 인터넷은 end system을 서로 연결하는 것이므로 end system에 접속을 제공하는 ISP들로 서로 연결되어야만 한다. 하위 계층 ISP는 국가, 국제 상위 ISP를 통해 연결된다. 상위든 하위든 각 ISP 네트워크는 따로 관리되고, IP 프로토콜을 수행하며 네이밍과 주소배정 방식을 따른다. 

 

<br/>
 


end system, packet switch, 인터넷의 다른 구성 요소들은 인터넷에서 송수신을 제어하는 여러 **protocol(프로토콜)**을 수행한다. 특히 **TCP(Transmission Control Protocol)**와 **IP(Internet Protocol)**는 인터넷에서 가장 중요한 프로토콜이다. 


<br/>

**IP 프로토콜**은 라우터와 end system 사이에서 송수신되는 packet 포맷을 기술한다. 이러한 인터넷의 주요 프로토콜을 통칭하여 **TCP/IP**라고 한다. 

 
<br/>

인터넷에서 프로토콜이 아주 중요하다면 각각의 프로토콜이 무엇을 수행하는지에 대해 합의하는 것도 매우 중요하며, 그렇게 함으로써 사람들은 상호호환되는 시스템과 제품을 만들 수 있다. 

인터넷 표준은 **IETF(Internet Engineering Task Force)**에서 개발하며 **IETF 표준 문서**를 **R**FCs(Requests For Comments)**라고 한다. 

 

 

 

## What's the Internet: a service view
### 서비스 측면에서 본 인터넷 


<br/>

### 인터넷 = 애플리케이션에 서비스를 제공하는 인프라 구조 
### Infrastructure thar provides services to applications 

 

많은 애플리케이션들은 서로 데이터를 교환하는 많은 end system들을 포함하고 있기 때문에 **분산 애플리케이션(distributed application)**이라고 부른다. 중요한 것은 인터넷 애플리케이션은 end system 에서 수행된다는 것이다. - 이들은 네트워크 코어에 있는 패킷 교환기에서 수행되지 않는다.

 

인터넷에 접속된 end system들은 **한 end system에서 수행되는 프로그램이 어떻게 인터넷 인프라 구조에게 다른 end system에서 수행되는 특정 목적지 프로그램에게 데이터를 전달하도록 요구하는지를 명시**하는 socket interface(소켓 인터페이스)를 제공한다. 인터넷 소켓 인터페이스는 **송신 프로그램이 따라야 하는 규칙의 집합**이며, 인터넷은 이 규칙을 따라 데이터를 목적지 프로그램으로 전달하게 된다. 

 

 

 

## What's a Protocol?
### 프로토콜이란 무엇인가?
### 사람 프로토콜 - 사람의 의사소통을 보면

우리가 보내는 특정한 메세지가 있고, 수신된 응답 메세지 혹은 다른 상황에 대응해서 취하는 특정 행동이 있다.

 
<br/>

네트워크 프로토콜은 사람 간의 프로토콜과 매우 비슷하다. 통신하는 둘 이상의 원격 개체가 포함된 인터넷에서의 모든 활동은 프로토콜이 제어한다. 

 
<br/>

"프로토콜은 둘 이상의 통신 개체 간에 교환되는 **메시지 포맷과 순서** 뿐 아니라, 메시지의 송수신과 다른 **이벤트**에 따른 행동들을 정의한다."

"Protocols define **format**, **order** of messages sent and received among network entities, and **actions** taken on message transmission, receipt."