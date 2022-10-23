https://syuda.tistory.com/m/80

안녕하세요. 슈다 입니다.

윈도우10 ICMP 설정 방법을 알아보도록 하겠습니다.

 

같은 네트워크에 있는 단말PC 간 ping 명령어를 통해 네트워크 온라인 여부 등을 확인할 수 있습니다.

윈도우10에서는 기본적인 보안이 강화되어 별도로 방화벽 설정을 해야 ping check가 가능한데요,

ICMP가 허용되지 않았다면, 같은 네트워크 대역의 다른 단말기에서 ping을 보내도 [요청 시간이 만료되었습니다.]

화면만 보게 됩니다.

 

**윈도우10 방화벽 ICMP 허용 방법**

윈도우+R 키를 눌러 [실행] 창을 연 후 control 을 입력하여 [제어판] 을 실행합니다.

범주가 [큰 아이콘] 으로 되어 있다면 [작은 아이콘] 으로 변경합니다.

Windows Defender 방화벽 을 실행한 후 **고급설정**을 선택합니다.

 



![img](https://k.kakaocdn.net/dn/PQ4aM/btqAM3BR7pU/82TL2ot82kQXwrPMPffvv0/img.png)



 

 



![img](https://k.kakaocdn.net/dn/RCEUH/btqAN23zEp0/tpFFNC8MVQ8T6yRNzUtsG1/img.png)



 

좌측 상단의 [인바운드 규칙] 선택 후, 나열되는 항목 중 **[파일 및 프린터 공유 (에코 요청 - ICMPv4-In) / 공용]** 을 선택한뒤

[우클릭 > 규칙 사용] 을 선택합니다. 사용되는 규칙은 녹색 체크 표시가 되어 있습니다.

 



![img](https://k.kakaocdn.net/dn/bVPuCm/btqALQ4lm6K/pPRoCtgHekkPfgHKFEj6ZK/img.png)



 

타 단말PC에서 방화벽 설정을 완료한 윈도우10 PC의 IP로 ping 명령어를 사용해 봅니다.

정상적으로 ping이 가는 것이 확인 된다면 성공적으로 ICMP를 허용한 것 입니다.

 



**ICMP 매뉴얼 설정 방법**

만약 방화벽의 [인바운드 규칙] 에서 **[파일 및 프린터 공유 (에코 요청 - ICMPv4-In) / 공용]** 항목을 찾을 수 없다면

수동으로 ICMP 정책을 생성하여 허용해 주어야 합니다.

아래와 같이 **[새 규칙]** 을 통해 새로운 정책을 생성합니다. 

 



![img](https://k.kakaocdn.net/dn/cFZOBG/btqANEu7loM/gPgNDu8HZ7Qw6KNtH0vrGk/img.png)



 

스크린샷 내용을 따라가 규칙 설정을 완료합니다.

크게 어려운 부분이 없으므로 쉽게 따라할 수 있습니다.

 



![img](https://k.kakaocdn.net/dn/lg1Ca/btqAQmz1P0m/f9zOc6zuvUQKymz9HJCNa0/img.png)규칙 종류 - 사용자 지정



 



![img](https://k.kakaocdn.net/dn/CY2VB/btqAMOkGQ61/rUc58OqiMmO1SswxPaf5ok/img.png)모든 프로그램 선택



 



![img](https://k.kakaocdn.net/dn/mzGvf/btqAQlA8tVU/HbUf7S89ZVC2rk7bhM4kQ0/img.png)프로토콜 종류 - ICMPv4 선택



 



![img](https://k.kakaocdn.net/dn/bWEvkM/btqANDbWj2q/Z8bZFnhFNHqHHed6LhbIK0/img.png)모든 IP 주소 선택



 



![img](https://k.kakaocdn.net/dn/bm1fQf/btqAMPjz8wj/qAYeEySrjKJQWPXukzvRCk/img.png)연결 허용 선택



 



![img](https://k.kakaocdn.net/dn/y1ypF/btqAPdJ8O7l/cRp6HD29kadoyKra6QVPfk/img.png)모든 체크박스 선택



 



![img](https://k.kakaocdn.net/dn/LSXR7/btqAOcLJ7ic/DOZisxAjKUYhF5pYpwuS6K/img.png)규칙 이름 생성 - 원하는 이름으로 생성합니다.



 

 

새로운 규칙을 생성한 뒤 생성한 이름을 목록에서 확인합니다. 녹색 체크 표시로 현재 활성화 되어 있는 것을 확인할 수 있습니다.



![img](https://k.kakaocdn.net/dn/TEW78/btqALPRUT1w/tkoDXnY815IUcSf5HklBkk/img.png)



 

 

동일 네트워크 간에 윈도우10에서 다른 PC로 ping이 허용되는데 자신의 윈도우10으로는 ping이 오지 않을 경우

이제 당황하지 않고 **ICMP를 허용하여 ping을 활성화** 할 수 있습니다.