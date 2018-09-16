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
  - **ARP spoofing이란?**
    + 네트워크 안의 모든 기기는 인터넷으로 통하는 관문인 게이트웨이를 꼭 통해야 한다.  
    이를 이용해 공격자 스스로 게이트웨이라고 속이고 피해자는 이를 모르고 모든 데이터를 공격자에게 전송하게 된다.
    + 과정
      1. 공격자가 게이트웨이의 IP 주소와 자신의 MAC 주소가 담긴 패킷을 피해자에게 지속적으로 보낸다.
      2. 피해자는 그 패킷을 ARP table에 저장한다.
      3. 피해자는 공격자를 게이트웨이라고 인식하고 공격자에게 패킷을 전송하게 된다.
      4. 공격자는 그 패킷을 조작하여 공격한다.
   - **Defense**  
    1. ARP 테이블 확인  
    2. ARP spoofing 감지 (arp -a로 MAC 주소가 동일한 것을 발견)  
    3. 공격자 IP 주소 확인 후, 이 주소와 대응되는 MAC 주소 강제로 변경  
    4. 로컬 방식에서 사용되는 공격 방식이라 로컬 ARP cashe table을 static으로 변경  
     + 사전 방지책: OS 시작과 동시에 ARP cahse를 static으로 고정한다.  
