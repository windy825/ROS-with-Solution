## 왜 ROS 인가 ?

**1. 노드 프로세스의 분산 프레임 워크**

- 실행 프로그램들을 독립적으로 설계
- 프로세스 간 결합도를 낮춤

**2. 다양한 라이브러리와 C++ 과 Python 언어 지원**

**3. 시각화 툴 good**

<br>

<br>

## 통신 컨셉

**1. 메시지 , 토픽**

- 노드 간 데이터 주고받을때 사용

- 마스터를 통해 각 노드의 publisher 와 subscriber의 정보 공유를 통해 통신

  ![image](https://user-images.githubusercontent.com/89068148/198058684-145b0f24-6667-45eb-ad5b-2c6b70603b8e.png)

  채널 : 토픽 (통로는 점유하면 다른 공급자가 못 쓴다.)

  한 채널에 대해 발행은 하나의 노드지만, 수신은 여러 노드에서 이를 받아 볼 수 있음

<br>

**2. ROS Custom**

[ROS위키가 잘되있음](http://wiki.ros.org/ROS/Tutorials/CreatingMsgAndSrv)

**1. 가능한 종류**

- [msg](http://wiki.ros.org/msg) : msg 파일은 ROS 메시지의 필드를 설명하는 간단한 텍스트 파일입니다. 

  ​           다른 언어로 된 메시지의 소스 코드를 생성하는 데 사용됩니다.

작성 가능한 타입

```
int8, int16, int32, int64 (plus uint*)
float32, float64
string
time, duration
other msg files
variable-length array[] // 가변
fixed-length array[C] // 고정
```



- [srv](http://wiki.ros.org/srv) : srv 파일은 서비스를 설명합니다. 

  ​        요청과 응답의 두 부분으로 구성됩니다.

<br>

<br>

**3. rosbridge** (ROS package)

json 형식의 데이터 -> ROS 메시지

ROS 메시지 -> json 형식의 데이터

- Local ip 로 내부에서만 통신하는 것이 아닌, 

  외부 프로그램과도 통신할 수 있도록 한다.