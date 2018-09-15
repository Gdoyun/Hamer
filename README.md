##  Frame
### ARP
 - ARP란?
   + ARP는 Address Resolution Protocol의 약자로 IP 주소를 물리적 네트워크 주소로 대응시키기 위해 사용되는 프로토콜
   + 물리적 네트워크 주소(MAC) : Ethernet or 48 bit 네트워크 카드 주소
   1. OSI 계층 3(network layer)에서 IP 주소 연결
   2. OSI 계층 2(data link layer)에서 MAC 주소 사용하여 실질적 데이터 이동
   + 1, 2인 IP 주소와 MAC 주소를 이어주는 역할이 ARP
 - Process 
   + 송신자 -> 수신자
     1. 데이터 보내기 전 ARP table 확인
     2. table에 수신자 정보가 없으면 ARP Request broadcast
     3. 네트워크 상 모든 호스트들은 ARP Request 패킷 수신
     4. 해당 ip를 가진 호스트만 mac주소 포함 ARP Reply 전송
     5. ARP Reply 패킷 받고 ARP table
 - ARP Packet Format
    + ![ARP Packet Format!](https://upload.wikimedia.org/wikipedia/commons/7/71/Arp-6-638.jpg "ARP Packet Format")
### ARP spoofing
  - ARP spoofing이란?
    + 네트워크 안의 모든 기기는 인터넷으로 통하는 관문인 게이트웨이를 꼭 통해야 한다.  
    이를 이용해 공격자 스스로 게이트웨이라고 속이고 피해자
    
