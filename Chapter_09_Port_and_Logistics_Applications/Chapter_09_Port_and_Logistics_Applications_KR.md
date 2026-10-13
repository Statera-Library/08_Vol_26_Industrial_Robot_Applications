**Volume 26. Industrial Robot Applications**

# Chapter 09. Port and Logistics Applications

## 09.01. Port Automation Overview AGV AMR Crane SW

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

항만 자동화(Port Automation)는 최소한의 수동 개입으로 컨테이너와 화물을 이동하기 위해 자동화 차량(Automated Vehicle), 크레인(Crane), 센싱 시스템(Sensing System), 터미널 소프트웨어(Terminal Software), 통신 인프라(Communication Infrastructure)를 통합적으로 운용하는 기술이다. 일반적인 창고 자동화(Warehouse Automation)와 달리 항만은 중장비, 선박, 트럭, 작업자, 자율주행 장비가 지속적으로 상호작용하는 대규모 실외 환경이다. 따라서 소프트웨어 아키텍처(Software Architecture)는 물류 최적화(Logistics Optimization), 실시간 제어(Real-Time Control), 위치 추정(Localization), 안전(Safety), 운영 조정을 하나의 통합 환경에서 결합해야 한다.

현대적인 자동화 컨테이너 터미널(Automated Container Terminal)은 서로 연결된 운송 및 하역 프로세스의 연속으로 볼 수 있다. 선박으로 도착한 컨테이너는 안벽 크레인(Quay Crane)에 의해 하역되고, 자동화 운송 차량(Automated Transport Vehicle)로 이송된 후 컨테이너 야드(Container Yard)의 블록으로 전달되어 자동화 적재 크레인(Automated Stacking Crane)에 의해 배치된다. 수출 컨테이너는 이와 반대 과정으로 이동한다. 각각의 물리적 이동은 터미널 일정, 컨테이너 식별 정보, 장비 상태, 교통 상황, 선박 적재 계획과 동기화되어야 하는 소프트웨어 이벤트(Software Event)를 생성한다.

자동 유도 차량(Automated Guided Vehicle, AGV)은 전통적으로 안벽 크레인과 야드 보관 구역 사이에서 컨테이너의 수평 운송을 담당해 왔다. 기존 항만용 AGV는 일반적으로 트랜스폰더(Transponder), 자기 마커(Magnetic Marker), 가상 트랙(Virtual Track), 정밀 측량 지도 등을 통해 정의된 사전 설정 경로를 따라 이동한다. 제어 소프트웨어(Control Software)는 결정론적 경로 실행(Deterministic Route Execution), 교통 조정, 충돌 방지, 컨테이너 인계 동기화, 반복적인 고하중 운송 주기에서의 안정적인 운용을 중점적으로 처리한다.

자율 이동 로봇(Autonomous Mobile Robot, AMR)은 더 높은 수준의 환경 인식(Environmental Perception)과 주행 유연성을 도입하여 이러한 개념을 확장한다. 항만용 AMR은 GNSS/RTK, 라이다(LiDAR), 카메라(Camera), 레이더(Radar), 관성 센서(Inertial Sensor), 휠 오도메트리(Wheel Odometry), 지도 정보를 결합하여 자신의 위치를 추정하고 주변 교통 환경을 이해할 수 있다. 고정된 유도 경로에 완전히 의존하는 대신 내비게이션 소프트웨어(Navigation Software)가 실행 가능한 궤적을 계산하고, 일시적인 장애물에 대응하며, 경로를 조정하고, 운영 안전 구역을 준수하면서 변화하는 터미널 배치에 대응할 수 있다.

AGV와 AMR의 차이는 예측 가능성과 유연성이 동시에 요구되는 항만 응용에서 특히 중요하다. 구조화된 컨테이너 전용 차로에서는 결정론적인 AGV 운용이 적합한 반면, 혼합 교통 구역, 정비 구역, 동적으로 변화하는 물류 공간에서는 자율주행 기능이 유리하다. 따라서 대규모 터미널에서는 고정 경로 차량, 자율 운송 차량, 사람이 운전하는 트럭, 특수 로봇 플랫폼이 공통 교통 관리 인프라(Traffic Management Infrastructure)를 공유하는 하이브리드 차량군(Hybrid Fleet)을 구축할 수 있다.

안벽 크레인(Quay Crane)은 또 다른 핵심 자동화 영역이다. 안벽 크레인은 트롤리(Trolley), 호이스트(Hoist), 갠트리(Gantry), 스프레더(Spreader)의 동작을 조정하여 선박과 육상 운송 장비 사이에서 컨테이너를 이동시킨다. 크레인 소프트웨어(Crane Software)는 동작 명령, 위치 피드백(Position Feedback), 흔들림 방지 제어(Anti-Sway Control), 컨테이너 정렬, 인터록(Interlock), 장비 안전 기능을 관리한다. 자동화 운용을 위해서는 선박 계획 및 운송 차량과의 동기화도 필요하며, 이를 통해 크레인이 컨테이너 이송을 완료하는 시점에 AGV 또는 AMR이 정확한 위치에 배치될 수 있다.

스프레더(Spreader)는 크레인과 컨테이너 사이의 물리적 인터페이스(Physical Interface)를 구성한다. 스프레더 제어 시스템은 트위스트 록(Twist-Lock) 체결, 컨테이너 존재 감지, 정렬 확인, 안전한 해제 등의 기능을 관리한다. 센서는 인양을 시작하기 전에 컨테이너가 안전하게 체결되었는지 확인하기 위한 피드백을 제공한다. 이러한 기능은 크레인의 프로그래머블 로직 컨트롤러(Programmable Logic Controller, PLC), 모션 컨트롤러(Motion Controller), 안전 컨트롤러(Safety Controller), 상위 감독 소프트웨어(Supervisory Software)와 통합되어 위험한 동작 순서와 잘못된 컨테이너 취급을 방지한다.

수평 운송 이후에는 야드 자동화(Yard Automation)가 프로세스를 이어받는다. 자동화 적재 크레인(Automated Stacking Crane)은 컨테이너를 인계 지점, 보관 위치, 트럭 교환 구역 사이에서 이동시킨다. 관련 소프트웨어는 갠트리 이동, 트롤리 동작, 인양, 컨테이너 식별, 적재 공간 점유 상태, 충돌 방지를 조정해야 한다. 컨테이너 배치는 이후의 반출 작업 효율에 영향을 미치기 때문에 크레인의 실행 제어는 개별 컨테이너의 저장 위치를 결정하는 상위 수준의 야드 계획 알고리즘(Yard Planning Algorithm)과 밀접하게 연결된다.

감독 계층에서는 터미널 운영 시스템(Terminal Operating System, TOS)이 터미널 활동의 운영 상태를 디지털 형태로 관리한다. TOS는 컨테이너 정보, 선박 일정, 야드 재고, 작업 대기열, 장비 할당, 적재 및 하역 계획을 관리한다. 로봇과 크레인 시스템은 서로 고립된 자동화 시스템으로 동작해서는 안 된다. 대신 차량군 관리(Fleet Management) 및 장비 제어 계층(Equipment Control Layer)이 TOS의 작업 지시를 실행 가능한 임무로 변환하고, 실행 상태, 예외 상황, 작업 완료 이벤트를 다시 터미널 소프트웨어로 전달한다.

일반적인 소프트웨어 계층 구조(Software Hierarchy)는 비즈니스 수준의 물류 의사결정과 장비 수준의 실시간 제어를 분리한다. TOS는 어떤 화물을 이동해야 하는지를 결정하고, 차량군 관리 소프트웨어(Fleet Management Software)는 어떤 차량이 해당 운송 작업을 수행할지를 결정한다. 교통 관리 소프트웨어(Traffic Management Software)는 공유 도로와 교차로를 조정하며, 차량 자율주행 소프트웨어(Vehicle Autonomy Software)는 위치 추정, 경로 계획, 장애물 대응, 주행 실행을 수행한다. 최종적으로 임베디드 컨트롤러(Embedded Controller)는 동작 명령을 조향, 추진, 제동, 유압 또는 액추에이터(Actuator) 동작으로 변환한다.

자율 운송 차량의 수가 증가할수록 차량군 오케스트레이션(Fleet Orchestration)의 중요성도 증가한다. 디스패처(Dispatcher)는 차량 위치, 배터리 상태, 적재 능력, 혼잡도, 크레인 일정, 정비 상태, 작업 우선순위를 고려하여 임무를 할당해야 한다. 소규모 시스템에서는 가장 가까운 차량을 선택하는 단순한 방식이 동작할 수 있지만, 대규모 터미널에서는 미래의 교통 상황과 장비 활용률까지 고려하는 최적화 방법이 필요하다. 잘못된 배차 결정은 개별 로봇이 정상적으로 작동하더라도 크레인 주변에 대기열을 발생시킬 수 있다.

교통 관리(Traffic Management)는 독립적으로 수행되는 차량 임무 사이를 연결하는 조정 계층을 제공한다. 항만 도로에는 교차로, 합류 차선, 인계 지점, 제한 구역, 사람에 의해 운전되는 장비와 공유되는 영역이 존재한다. 교통 시스템은 경로 예약(Route Reservation), 교차로 통행 허가, 우선순위 규칙, 속도 제한, 교착 상태 해결(Deadlock Resolution) 메커니즘을 사용할 수 있다. 목표는 단순히 충돌을 방지하는 것이 아니라 크레인 및 선박 작업 생산성을 감소시키는 혼잡을 억제하면서 예측 가능한 물류 흐름을 유지하는 것이다.

위치 추정(Localization)은 환경 조건이 빠르게 변화할 수 있는 대규모 실외 터미널에서도 신뢰성을 유지해야 한다. GNSS/RTK는 정밀한 전역 위치 정보를 제공할 수 있으며, 라이다, 카메라, 레이더, 관성 측정 장치(Inertial Measurement Unit, IMU), 오도메트리(Odometry)는 상호 보완적인 지역 위치 정보를 제공한다. 센서 융합(Sensor Fusion)을 적용하면 크레인, 컨테이너 적재 구조물, 건물, 대형 금속 구조물 주변에서 위성 신호가 약화되는 경우에도 자율 차량이 계속 운용될 수 있다. 또한 위치 추정 서브시스템(Localization Subsystem)은 신뢰도 정보를 제공하여 위치 정확도가 저하되면 속도를 제한하거나 안전 정지를 수행할 수 있어야 한다.

인지 소프트웨어(Perception Software)는 차량, 작업자, 컨테이너, 장애물, 차선 경계, 기반 시설, 운영 구역을 식별한다. 항만 환경에서는 비, 안개, 먼지, 야간, 눈부심, 반사 표면, 반복적으로 적재된 컨테이너 구조 등 센싱을 어렵게 만드는 다양한 조건이 발생한다. 따라서 강건한 시스템(Robust System)은 단일 인지 방식에 의존하지 않고 상호 보완적인 센서를 사용한다. 감지 결과는 충돌 회피(Collision Avoidance)와 궤적 계획(Trajectory Planning)을 지원하는 지역 환경 표현(Local Environmental Representation)으로 변환된다.

안전 아키텍처(Safety Architecture)는 생산성 최적화 소프트웨어가 중요한 보호 기능을 무시하지 못하도록 일반적인 임무 최적화 기능과 분리된다. 비상 정지(Emergency Stop), 보호 영역(Protective Field), 장애물 감지, 속도 감시, 제동 모니터링, 지오펜스(Geofence) 기반 제한, 장비 인터록은 독립적인 안전 계층(Safety Layer)을 구성할 수 있다. 통신이 중단되거나 위치 추정 신뢰도가 허용 가능한 임계값 아래로 떨어지면 불확실한 정보를 기반으로 임무를 계속 수행하는 대신 사전에 정의된 성능 저하 상태(Degraded State) 또는 안전 상태(Safe State)로 전환해야 한다.

통신 인프라(Communication Infrastructure)는 차량, 크레인, 제어 서버(Control Server), TOS 플랫폼, 정비 시스템, 운영자 스테이션(Operator Station)을 연결한다. 터미널 요구사항에 따라 산업용 이더넷(Industrial Ethernet), 무선 LAN(Wireless LAN), 사설 셀룰러 네트워크(Private Cellular Network) 및 기타 이중화 통신 기술을 조합할 수 있다. 시스템 아키텍처는 지연 시간에 민감한 제어 및 안전 정보와 일반 텔레메트리(Telemetry), 로그(Log), 비디오 스트림(Video Stream), 이력 데이터를 구분하여 대역폭이 큰 서비스가 운영상 중요한 메시지 전달을 방해하지 않도록 해야 한다.

컨테이너 식별(Container Identification)은 실제 화물의 이동을 디지털 물류 시스템(Digital Logistics System)과 연결한다. 광학 문자 인식(Optical Character Recognition, OCR) 카메라, 장비 센서, 사용 가능한 경우 무선 주파수 식별(Radio Frequency Identification, RFID), 컨테이너 위치 기록 등을 이용하여 운송 과정에서 컨테이너의 신원을 확인할 수 있다. 소프트웨어는 관측된 각 컨테이너를 해당 임무, 출발 위치, 목적지, 차량, 크레인 작업, TOS 기록과 연결해야 한다. 잘못된 식별 정보는 전체 물류 체인으로 전파될 수 있기 때문에 추적성(Traceability)과 검증(Verification)은 자동화 터미널 운영의 핵심 요소이다.

운영 모니터링(Operational Monitoring)은 전체 자동화 시스템의 실시간 상태를 제공한다. 관제 센터(Control Center)는 차량 위치, 크레인 상태, 활성 임무, 차단된 경로, 경보, 배터리 상태, 통신 품질, 장비 가용성을 시각적으로 확인한다. 축적된 텔레메트리 데이터는 사이클 시간(Cycle Time), 장비 활용률(Utilization), 혼잡, 고장 빈도, 에너지 소비, 복구 성능을 분석하는 데 사용된다. 이러한 데이터는 운영자가 개별 장비의 고장과 스케줄링 또는 교통 정책에 의해 발생한 시스템 수준의 문제를 구분할 수 있도록 한다.

예외 처리(Exception Handling) 역시 매우 중요하다. 항만에서는 모든 운영 상황이 완벽하게 예측 가능하다고 가정할 수 없기 때문이다. 차량이 이동 불가능 상태에 빠지거나, 컨테이너 식별에 실패하거나, 크레인이 정비 모드(Maintenance Mode)에 진입하거나, 통신 링크가 사라지거나, 예정된 인계 작업이 수행되지 않을 수 있다. 자동화 소프트웨어는 이러한 상태를 감지하고 운영상의 영향을 분류하며, 허용되는 범위에서 안전한 복구를 시도하고, 해결되지 않은 문제는 임무 및 컨테이너 상태 정보를 유지한 상태에서 작업자에게 전달해야 한다.

디지털 트윈(Digital Twin)과 시뮬레이션 환경(Simulation Environment)은 실제 시스템을 배치하기 전에 항만 자동화를 설계하고 검증하는 데 활용될 수 있다. 차량 경로, 크레인 사이클, 야드 배치, 교통 규칙, 배차 알고리즘을 시뮬레이션된 작업 부하에서 평가할 수 있다. 소프트웨어 인 더 루프(Software-in-the-Loop, SIL)와 하드웨어 인 더 루프(Hardware-in-the-Loop, HIL) 시험을 통해 실제 운영에서 문제가 발생하기 전에 혼잡, 교착 상태, 위험한 상호작용, 성능 병목을 발견할 수 있다. 시뮬레이션은 소프트웨어 업데이트와 새로운 자율주행 기능을 검증하기 위한 반복 가능한 시험 시나리오도 제공한다.

따라서 전체 항만 자동화 아키텍처(Port Automation Architecture)는 독립적으로 자동화된 장비들의 단순한 집합이 아니다. 이는 AGV, AMR, 안벽 크레인, 적재 크레인, 센서, 차량군 서비스(Fleet Service), 교통 관리자(Traffic Manager), 터미널 애플리케이션(Terminal Application)이 지속적으로 상태와 의사결정 정보를 교환하는 분산 사이버 물리 물류 시스템(Distributed Cyber-Physical Logistics System)이다. 이러한 구조는 차량군 지능(Fleet Intelligence), 통신 API(Communication API), 엣지 컴퓨팅(Edge Computing), 내비게이션(Navigation), 인지(Perception), 사이버보안(Cybersecurity), 검증(Validation) 기술과도 자연스럽게 연결된다.

장기적인 발전 방향은 개별 장비 수준이 아니라 전체 시스템 수준에서 장비의 동작을 최적화할 수 있는 더욱 통합적이고 소프트웨어 정의된 터미널(Software-Defined Terminal)로 향하고 있다. 인공지능(Artificial Intelligence, AI)은 배차, 혼잡 예측, 장비 상태 추정, 컨테이너 인식, 운영 예측을 향상시킬 수 있으며, 자율주행 차량은 유연한 물리적 실행 능력을 제공한다. 핵심적인 엔지니어링 과제는 더욱 적응적이고 지능적인 자동화를 단계적으로 도입하면서도 결정론적 안전성(Deterministic Safety)과 신뢰할 수 있는 물류 성능을 지속적으로 유지하는 것이다.

## 09.02. Automated Container Transport AMR SW [w/Code]

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

자동화 컨테이너 운송 자율 이동 로봇(Automated Container Transport AMR)은 자동화 터미널에서 안벽 크레인(Quay Crane), 컨테이너 야드(Container Yard), 이송 스테이션(Transfer Station), 육상 물류 구역(Landside Logistics Area)을 연결하는 수평 운송 계층(Horizontal Transport Layer)을 제공한다. 경량 창고 AMR과 달리 이러한 차량은 수 톤에서 수십 톤에 이르는 컨테이너를 운반하면서 대규모 실외 공간에서 지속적으로 운용되어야 한다. 따라서 소프트웨어는 자율주행(Autonomous Navigation), 대형 차량 모션 제어(Motion Control), 임무 실행(Mission Execution), 기능 안전(Functional Safety), 차량군 조정(Fleet Coordination), 터미널 시스템 통합(Terminal System Integration)을 높은 신뢰성을 갖는 런타임 아키텍처(Runtime Architecture) 안에서 결합해야 한다.

AMR 소프트웨어 아키텍처(Software Architecture)는 일반적으로 인지(Perception), 위치 추정(Localization), 계획(Planning), 제어(Control), 임무 관리(Mission Management), 안전(Safety), 통신(Communication), 진단(Diagnostics), 하드웨어 추상화(Hardware Abstraction) 계층으로 구분된다. 이러한 분리는 상위 수준의 물류 의사결정이 차량 하드웨어와 강하게 결합되는 것을 방지한다. 임무 관리자(Mission Manager)가 안벽 크레인에서 야드 블록까지의 이동을 요청하면 내비게이션 및 제어 모듈은 차량이 목적지에 안전하고 정확하게 도달하는 방법을 독립적으로 결정할 수 있다.

임무 실행은 차량군 관리 시스템(Fleet Management System)이 컨테이너 운송 요청을 차량에 할당하면서 시작된다. 요청에는 일반적으로 출발지와 목적지 위치, 컨테이너 또는 작업 식별 정보, 우선순위, 필요한 장비 인터페이스, 시간 제약 조건이 포함된다. AMR은 이러한 외부 요청을 배차(Dispatch), 경로 획득(Route Acquisition), 이동(Travel), 픽업 정렬(Pickup Alignment), 컨테이너 확인(Container Verification), 적재 운송(Loaded Transport), 배송 위치 정렬(Delivery Alignment), 하역 확인(Unloading Confirmation), 임무 완료(Mission Completion)를 포함하는 내부 상태 머신(State Machine)으로 변환한다.

위치 추정(Localization)은 차량이 터미널 도로를 주행하고 크레인 또는 이송 장비 아래에 정확하게 정렬할 수 있을 정도로 자신의 위치를 알아야 하기 때문에 핵심적인 기능이다. GNSS/RTK는 개방된 공간에서 전역 위치 정보를 제공할 수 있으며, 관성 측정 장치(Inertial Measurement Unit, IMU), 휠 인코더(Wheel Encoder), 라이다(LiDAR), 카메라(Camera), 레이더(Radar)는 이를 보완하는 측정 정보를 제공한다. 위치 추정 프레임워크(Localization Framework)는 이러한 신호를 융합하여 단순한 하나의 좌표만 내비게이션 스택(Navigation Stack)에 제공하는 것이 아니라 위치, 방향, 속도, 불확실성, 센서 상태까지 추정한다.

항만에는 개별 위치 추정 기술의 성능을 일시적으로 저하시킬 수 있는 다양한 환경 조건이 존재한다. 컨테이너 적재 구조물과 대형 크레인은 위성 신호를 차단하거나 반사할 수 있으며, 비, 안개, 야간, 먼지, 반복적인 구조물은 카메라 또는 라이다 기반 인지 성능에 영향을 줄 수 있다. 따라서 소프트웨어는 위치 추정 신뢰도(Localization Confidence)를 지속적으로 감시하고 성능 저하 운용(Degraded Operation)을 지원해야 한다. 불확실성이 정의된 한계를 초과하면 차량 속도를 낮추거나 신뢰할 수 있는 위치 추정이 복구될 때까지 AMR을 제어된 정지(Controlled Stop) 상태로 전환할 수 있다.

인지 서브시스템(Perception Subsystem)은 AMR 주변 환경에 대한 표현을 구축한다. 차량, 작업자, 장애물, 컨테이너, 도로 경계, 장비, 정적 터미널 지도에 존재하지 않을 수 있는 임시 물체를 감지한다. 라이다는 기하학적 정보를 제공하고, 카메라는 시각 및 의미 정보(Semantic Information)를 제공하며, 레이더는 열악한 환경 조건에서 감지 성능을 보완할 수 있다. 센서 융합(Sensor Fusion)은 이러한 관측 정보를 추적 객체(Tracked Object)와 주행 가능 공간(Free Space) 정보로 결합하여 경로 계획 및 안전 기능에 제공한다.

전역 경로 계획(Global Route Planning)은 현재 위치와 임무 목적지를 연결하는 터미널 도로 및 운영 구역의 이동 순서를 결정한다. 경로 계획기는 일방통행 차선, 제한 구역, 차량 크기, 회전 제약, 컨테이너 이송 지점, 임시 폐쇄 구역, 차량군 교통 정책을 고려해야 한다. 여러 AMR이 동일한 인프라를 공유할 수 있기 때문에 경로 선택에서는 터미널 교통 관리 시스템(Traffic Management System)이 제공하는 혼잡도와 경로 예약(Route Reservation) 정보도 고려해야 한다.

지역 경로 계획(Local Planning)은 전역 경로를 차량이 실제로 주행할 수 있는 동적 궤적(Dynamically Feasible Trajectory)으로 변환한다. 경로 계획기는 주변 장애물, 차량 속도, 조향 한계, 제동 거리, 적재 상태, 도로 형상, 주변 교통 객체의 예상 움직임을 평가한다. 대형 컨테이너 운송 차량의 동역학은 소형 실내 로봇과 크게 다르기 때문에 급격한 움직임을 피해야 한다. 궤적 생성(Trajectory Generation)은 기반 시설과 주변 장비로부터 충분한 간격을 유지하면서 안정적이고 예측 가능한 움직임을 우선해야 한다.

모션 제어 계층(Motion-Control Layer)은 선택된 궤적을 조향, 추진, 제동 명령으로 변환한다. 종방향 제어(Longitudinal Control)는 가속도와 속도를 조절하고, 횡방향 제어(Lateral Control)는 목표 경로 또는 조향 궤적을 유지한다. 컨트롤러(Controller)는 차량 질량, 액추에이터 지연(Actuator Delay), 타이어 특성, 경사도, 노면 상태, 적재 및 비적재 운행에 따른 변화를 고려해야 한다. 명령 제한(Command Limit)을 적용하여 내비게이션 시스템이 플랫폼의 안전한 물리적 운용 범위 밖의 움직임을 요구하지 못하도록 해야 한다.

적재 상태(Payload State)는 AMR의 동작에 직접적인 영향을 준다. 컨테이너를 적재한 차량은 비적재 차량과 질량 분포, 정지 거리, 가속 성능, 안정성 특성이 다르다. 따라서 소프트웨어는 적재 운행과 비적재 운행에 서로 다른 모션 제약(Motion Constraint)을 유지할 수 있다. 컨테이너 존재 센서, 잠금 장치, 하중 측정 장치 또는 장비 간 핸드셰이크(Handshake)를 통해 운송을 시작하기 전에 소프트웨어에 표현된 적재 상태와 실제 물리적 상태가 일치하는지 확인해야 한다.

컨테이너 픽업(Container Pickup)을 위해서는 AMR과 크레인 또는 이송 장비 사이의 정밀한 조정이 필요하다. 차량은 먼저 지정된 인계 구역(Handover Zone)에 접근한 후 속도를 낮추고 정밀한 최종 위치 정렬(Final Positioning)을 수행한다. 이송 작업 전에 위치 허용 오차(Position Tolerance), 차량 준비 상태, 브레이크 상태, 적재 인터페이스 상태, 크레인 작업 허가를 확인한다. 핸드셰이크 프로토콜(Handshake Protocol)은 상대 장비가 요구된 상태에 도달하지 않은 상황에서 어느 한쪽 장비가 위험한 동작을 시작하는 것을 방지한다.

적재가 완료된 후 AMR은 인계 구역을 떠나기 전에 컨테이너가 정상적으로 이송되었는지 확인한다. 차량 설계에 따라 존재 감지 센서(Presence Sensor), 잠금 상태, 하중 감지(Load Detection), 장비 메시지 또는 이러한 신호들의 이중화 조합을 사용할 수 있다. 단순히 예상 이송 시간이 경과했다는 이유만으로 임무 상태를 다음 단계로 진행해서는 안 된다. 명시적인 확인(Explicit Confirmation)을 통해 소프트웨어는 정상적인 픽업과 불완전하거나 비정상적인 컨테이너 적재를 구분할 수 있다.

차량군 조정(Fleet Coordination)은 개별적으로 정상 동작하는 AMR들이 시스템 수준에서 비효율적이거나 위험한 동작을 만드는 것을 방지한다. 차량군 관리자(Fleet Manager)는 임무를 할당하고, 교통 관리 계층(Traffic Management Layer)은 공유 차선, 교차로, 대기 구역, 이송 지점을 조정한다. 경로 예약 또는 시간 기반 통행 권한(Time-Based Permission)을 통해 충돌 가능성이 있는 이동을 방지할 수 있다. 또한 크레인 대기 시간은 터미널 처리량(Terminal Throughput)을 직접 감소시킬 수 있기 때문에 중요한 안벽 크레인 작업을 지원하는 차량에 우선순위를 부여할 수 있다.

많은 대형 차량이 제한된 도로망에서 운용될 경우 교착 상태 방지(Deadlock Prevention)가 특히 중요하다. 충돌 회피 기능이 정상적으로 작동하더라도 두 대 이상의 AMR이 서로의 이동을 차단하는 상황이 발생할 수 있다. 교통 소프트웨어는 방향성 차선(Directional Lane), 예약 그래프(Reservation Graph), 교차로 잠금(Intersection Locking), 대기 구역, 자원 순서 정책(Resource-Ordering Policy)을 통해 이러한 위험을 줄일 수 있다. 예방에 실패한 경우 교착 상태 감지(Deadlock Detection)가 순환 의존 관계를 식별하고 하나 이상의 차량을 선택하여 경로 재계획(Rerouting) 또는 제어된 후퇴(Controlled Retreat)를 수행한다.

가능한 경우 안전 기능(Safety Function)은 일반적인 내비게이션 기능과 독립적으로 동작한다. 비상 정지 회로(Emergency-Stop Circuit), 보호 센싱(Protective Sensing), 속도 감시(Speed Monitoring), 제동 감독(Braking Supervision), 지오펜스 제한(Geofenced Restriction), 안전 컨트롤러 로직(Safety-Controller Logic)은 자율주행 스택(Autonomy Stack)에 장애가 발생하더라도 위험한 움직임으로부터 시스템을 보호한다. 내비게이션 시스템은 장애물을 부드럽게 회피할 수 있지만 최소 안전 거리 요구사항을 위반하면 안전 계층이 즉각적인 보호 동작을 명령할 수 있어야 한다.

통신 소프트웨어(Communication Software)는 AMR을 차량군 서비스(Fleet Service), 교통 관리 시스템, 터미널 애플리케이션, 크레인 시스템, 유지보수 서버, 운영자 인터페이스와 연결한다. 메시지에는 임무 명령, 경로 통행 허가, 차량 위치 및 자세(Pose), 배터리 상태, 적재 상태, 경보, 장비 핸드셰이크 정보가 포함될 수 있다. 통신 손실(Communication Loss)은 사전에 정의된 대응 동작을 갖는 하나의 운영 상태로 취급해야 한다. 차량의 핵심 안전 기능이 원격 서버와의 지속적인 연결에만 의존해서는 안 된다.

터미널 운영 시스템(Terminal Operating System, TOS)과의 통합은 자율주행을 실제 컨테이너 물류 프로세스와 연결한다. TOS는 필요한 화물 이동을 결정하고, 차량군 소프트웨어는 이러한 요구사항을 로봇 임무(Robot Mission)로 변환한다. AMR은 실행 진행 상태와 예외 상황을 보고하여 디지털 컨테이너 기록과 실제 물리적 이동이 동기화되도록 한다. 이러한 관계를 통해 AMR 운송, 항만 교통 관리, 컨테이너 인식, TOS 통합 기능은 서로 연결된 하나의 자동화 체계를 구성한다.

에너지 관리(Energy Management) 역시 물류 스케줄링(Logistics Scheduling)과 연계되어야 한다. AMR은 배터리 충전 상태(State of Charge), 온도, 전력 요구량, 충전 설비 가용성, 할당된 임무 수행에 필요한 예상 에너지를 감시한다. 배터리가 위험할 정도로 낮아질 때까지 기다리는 대신 차량군 소프트웨어는 작업량이 적은 시간에 기회 충전(Opportunity Charging)을 수행하거나 예상 작업 부하에 따라 차량을 충전소로 배차할 수 있다. 에너지 인지형 임무 할당(Energy-Aware Assignment)은 차량군 가용성을 유지하면서 예상하지 못한 임무 중단을 줄인다.

진단 및 관측 가능성(Diagnostics and Observability)은 지속적으로 운용되는 차량군을 유지하는 데 필요한 정보를 제공한다. 차량 소프트웨어는 위치 추정 품질, 센서 상태, 컨트롤러 오류, 네트워크 상태, 배터리 상태, 액추에이터 고장, 임무 상태 전환, 안전 이벤트, 비정상 정지를 기록한다. 중앙 모니터링 서비스(Central Monitoring Service)는 이러한 텔레메트리(Telemetry)를 통합하여 반복적인 고장과 성능 저하를 식별한다. AMR, 크레인, 차량군 서비스 간의 상호작용을 재구성하기 위해서는 정확한 타임스탬프(Timestamp)와 이벤트 상관 분석(Event Correlation)이 필수적이다.

고장 관리(Fault Management)는 위치 추정 손실, 센서 고장, 차단된 경로, 액추에이터 고장, 통신 중단, 컨테이너 이송 오류, 안전 시스템 작동에 대한 명확한 대응 절차를 정의해야 한다. 일부 고장에서는 저속 운행이나 자동 경로 재계획이 가능하지만 다른 고장에서는 즉각적인 정지와 작업자 개입이 필요하다. 복구 로직(Recovery Logic)은 차량 또는 대체 AMR이 실제 컨테이너와 디지털 운송 작업 사이의 관계를 잃지 않고 물류 작업을 재개할 수 있도록 임무 상태를 보존해야 한다.

시뮬레이션(Simulation)과 디지털 트윈 환경(Digital-Twin Environment)은 전체 AMR 소프트웨어 스택을 검증하는 데 유용하다. 개발자는 실제 차량에 소프트웨어를 배포하기 전에 터미널 도로, 컨테이너 블록, 크레인 인터페이스, 교통 패턴, 센서 조건, 대규모 차량군을 재현할 수 있다. 소프트웨어 인 더 루프(Software-in-the-Loop, SIL) 시험은 경로 계획 및 임무 로직을 검증하고, 하드웨어 인 더 루프(Hardware-in-the-Loop, HIL) 시험은 컨트롤러와 인터페이스를 평가한다. 스트레스 시험 시나리오(Stress Scenario)를 통해 의도적으로 혼잡, 경로 차단, 센서 성능 저하, 통신 장애를 발생시켜 시스템의 대응 능력을 검증할 수 있다.

실제 운영 환경의 컨테이너 AMR은 궁극적으로 독립적인 자율주행 차량이 아니라 분산형 터미널 자동화 시스템(Distributed Terminal Automation System)의 하나의 노드(Node)로 취급해야 한다. AMR의 효과적인 운용은 크레인, 차량군 배차(Fleet Dispatch), 교통 제어(Traffic Control), 컨테이너 식별, TOS 서비스, 안전 인프라, 유지보수 시스템과의 지속적인 조정에 의존한다. 이러한 구조에서 항만 로봇은 차량군 지능(Fleet Intelligence), 내비게이션, 인지, 통신, 엣지 컴퓨팅(Edge Computing), 시험 및 검증(Testing and Validation) 기술과 긴밀하게 연결된다.

유도식 컨테이너 운송 차량(Guided Container Carrier)에서 지능형 AMR(Intelligent AMR)로의 발전은 운영 유연성을 높이는 동시에 소프트웨어가 담당해야 하는 책임도 증가시킨다. 미래 시스템에는 예측형 교통 모델(Predictive Traffic Model), AI 지원 인지(AI-Assisted Perception), 동적 임무 최적화(Dynamic Mission Optimization), 장비 상태 예측(Equipment-Health Prediction), 협력형 차량군 계획(Cooperative Fleet Planning)이 적용될 수 있다. 그러나 이러한 기능은 결정론적 안전 메커니즘(Deterministic Safety Mechanism)과 검증 가능한 차량 동작(Verifiable Vehicle Behavior)의 범위 안에서 운용되어야 한다. 따라서 성공적인 항만 AMR 소프트웨어는 계획 계층의 적응형 자율성(Adaptive Autonomy)과 물리 계층의 예측 가능한 제어 및 고장 안전 실행(Fail-Safe Execution)을 결합해야 한다.

## 09.03. Quay Crane Automation and Spreader Control [w/Code]

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

안벽 크레인 자동화(Quay Crane Automation)는 선박과 육상 사이의 컨테이너 하역 작업을 수동으로 조정되는 기계 작업에서 통합된 모션(Motion), 센싱(Sensing), 물류 시스템(Logistics System)으로 전환한다. 크레인은 정밀한 위치 제어와 엄격한 안전 제약을 유지하면서 선박의 컨테이너 베이(Container Bay)와 육상 운송 장비 사이에서 컨테이너를 신속하게 이동시켜야 한다. 따라서 크레인 소프트웨어는 갠트리(Gantry), 트롤리(Trolley), 호이스트(Hoist), 스프레더(Spreader), 센서(Sensor), 프로그래머블 컨트롤러(Programmable Controller), 안전 기능(Safety Function), 터미널 수준의 명령을 하나의 동기화된 제어 시스템으로 조정한다.

선박-육상 간 안벽 크레인(Ship-to-Shore Quay Crane)은 동작이 서로 조정되어야 하는 여러 개의 독립적인 구동 메커니즘(Actuated Mechanism)으로 구성된다. 갠트리 주행(Gantry Travel)은 전체 크레인을 안벽을 따라 이동시키고, 트롤리 동작(Trolley Motion)은 인양 시스템을 선박과 육상 위치 사이에서 이동시키며, 호이스트는 수직 이동을 제어한다. 스프레더는 컨테이너와 직접 연결되는 최종 인터페이스를 구성한다. 자동화 소프트웨어는 기계적 한계, 운용 범위(Operating Envelope), 충돌 구역(Collision Zone), 장비 인터록(Equipment Interlock)을 준수하면서 이러한 축을 통합적으로 관리한다.

제어 아키텍처(Control Architecture)는 일반적으로 상위 감독 시퀀싱(Supervisory Sequencing)과 결정론적 장비 제어(Deterministic Equipment Control)를 분리한다. 상위 수준의 크레인 컨트롤러(Crane Controller)는 작업 지시를 해석하고 필요한 하역 순서를 결정하며, 프로그래머블 로직 컨트롤러(Programmable Logic Controller, PLC)와 모션 컨트롤러(Motion Controller)는 시간 결정성이 중요한 명령을 실행한다. 드라이브(Drive)는 트롤리, 호이스트, 갠트리의 모터를 제어하고, 안전 컨트롤러(Safety Controller)는 위험 상태를 독립적으로 감시한다. 이러한 계층 구조를 통해 실시간 모션 보호 기능을 약화시키지 않으면서 물류 명령을 변경할 수 있다.

컨테이너 하역(Container Handling)은 대상 컨테이너, 선박 위치, 출발 또는 목적 슬롯(Slot), 관련 운송 작업을 식별하는 작업 지시(Work Instruction)로 시작된다. 크레인 자동화 시스템은 이러한 정보를 접근(Approach), 위치 결정(Positioning), 하강(Lowering), 스프레더 정렬(Spreader Alignment), 잠금(Locking), 인양(Lifting), 수평 이송(Horizontal Transfer), 목적지 정렬(Destination Alignment), 하강, 잠금 해제(Unlocking), 복귀(Return) 등의 실행 가능한 상태로 변환한다. 예상하지 못한 장비 동작이 후속 단계로 전달되지 않도록 상태 전환(State Transition)에는 명시적인 확인이 필요하다.

컨테이너 이송은 좁은 기하학적 허용 오차(Geometric Tolerance) 안에서 이루어지기 때문에 정밀한 트롤리 및 호이스트 위치 제어가 필수적이다. 인코더(Encoder), 레이저 거리 측정 장치(Laser Ranging Device), 카메라(Camera), 위치 센서(Position Sensor) 등의 측정 시스템을 이용하여 트롤리, 스프레더, 컨테이너, 선박 구조물, 목표 이송 위치를 추정할 수 있다. 제어 시스템은 이러한 측정값을 크레인 기하 정보와 결합하여 모션 기준값(Motion Reference)을 계산하고 실제 장비의 움직임이 허용 가능한 위치 범위 내에 유지되는지를 지속적으로 확인한다.

주요 제어 문제 중 하나는 컨테이너가 와이어 로프(Wire Rope)에 매달린 상태에서 트롤리가 가속하거나 감속할 때 발생하는 하중 흔들림(Load Sway)이다. 과도한 흔들림은 사이클 시간(Cycle Time)을 증가시키고 위치 정확도를 떨어뜨리며 충돌 위험을 발생시킬 수 있다. 흔들림 방지 제어(Anti-Sway Control)는 추정된 진자 운동(Pendulum Motion)에 따라 트롤리 가속도 또는 궤적을 수정한다. 피드포워드 모델(Feedforward Model), 피드백 제어(Feedback Control), 궤적 형상화(Trajectory Shaping), 센서 기반 추정(Sensor-Based Estimation)을 결합하여 컨테이너 이송 속도를 불필요하게 낮추지 않으면서 진동을 감소시킬 수 있다.

궤적 생성(Trajectory Generation)은 처리량(Throughput)과 기계적·안전 제약 사이의 균형을 유지해야 한다. 모든 축을 최대 속도로 움직이는 것이 반드시 전체 크레인 사이클 시간을 최소화하는 것은 아니다. 과도한 가속은 하중 흔들림을 발생시키고 추가적인 안정화 시간을 요구할 수 있기 때문이다. 따라서 자동화 시스템은 트롤리 속도, 호이스트 높이, 가속, 감속, 장애물 여유 공간을 조정하는 모션 프로파일(Motion Profile)을 계산한다. 효율적인 제어는 매달린 하중을 예측 가능한 운동 범위 안에 유지하면서 전체 이송 시간을 최소화한다.

스프레더(Spreader)는 크레인 자동화 시스템과 컨테이너 사이에서 가장 중요한 물리적 인터페이스(Physical Interface)이다. 스프레더는 컨테이너 코너 캐스팅(Corner Casting)에 정렬되고, 트위스트 록(Twist Lock)을 체결하며, 안전한 결합 상태를 확인하고, 인양 중 결합을 유지한 후 허가된 목적지에서만 컨테이너를 해제해야 한다. 따라서 스프레더 제어(Spreader Control)는 컨테이너 체결을 단순한 개폐 명령으로 처리하지 않고 기계적 구동, 센서 검증, 인터록 로직(Interlock Logic)을 통합한다.

픽업(Pickup) 과정에서는 정렬 센서(Alignment Sensor) 또는 비전 시스템(Vision System)이 상대적인 위치와 방향을 추정하는 동안 스프레더가 컨테이너 방향으로 하강한다. 정밀 위치 제어(Fine Positioning)는 선박 움직임, 컨테이너 배치 오차, 구조적 허용 오차, 잔류 스프레더 흔들림으로 발생하는 위치 편차를 보정한다. 접촉 센서(Contact Sensor) 또는 착상 센서(Landing Sensor)는 스프레더가 컨테이너에 도달했음을 나타낸다. 요구되는 착상 조건이 충족된 이후에만 제어 시퀀스가 트위스트 록 체결을 허용할 수 있다.

트위스트 록 제어(Twist-Lock Control)는 안전 중요 상태 시퀀스(Safety-Critical State Sequence)로 구현된다. 잠금 액추에이터(Locking Actuator)가 컨테이너 코너 캐스팅 내부에서 트위스트 록을 회전시키고 위치 센서가 잠금 또는 잠금 해제 상태를 확인한다. 소프트웨어는 서로 모순되는 센서 신호, 불완전한 잠금, 비정상적인 상태 전환 시간을 오류로 처리해야 한다. 요구되는 잠금 조건이 확인될 때까지 호이스트 동작을 금지하여 스프레더에 안전하게 체결되지 않은 컨테이너가 인양되는 것을 방지한다.

하중 검증(Load Verification)은 잠금 이후 추가적인 확인 기능을 제공한다. 로드 셀(Load Cell), 로프 장력 측정(Rope Tension Measurement), 유압 또는 전기 신호, 컨테이너 존재 센서(Container-Presence Sensor)를 이용하여 컨테이너가 실제로 스프레더에 매달려 있는지를 확인할 수 있다. 측정된 하중은 과부하(Overload) 또는 심각한 하중 불균형(Load Imbalance)을 감지하는 데도 활용될 수 있다. 이러한 신호를 이용하면 고속 호이스트 또는 트롤리 동작을 허용하기 전에 컨트롤러가 예상된 작업 상태와 실제 물리적 상태를 비교할 수 있다.

스프레더는 서로 다른 컨테이너 규격을 지원해야 하므로 일반적인 컨테이너 길이에 맞춰 텔레스코픽 조절(Telescopic Adjustment) 기능을 제공할 수 있다. 자동화 소프트웨어는 스프레더의 확장 또는 수축 동작을 관리하면서 픽업 전에 장치가 필요한 구성에 도달했는지를 확인한다. 트윈 리프트(Twin-Lift) 또는 기타 특수 하역 모드를 지원하는 경우 하중 형상과 잠금 조건이 더욱 복잡해지기 때문에 추가적인 센서와 인터록이 필요하다.

충돌 회피(Collision Avoidance)는 매달린 컨테이너 자체에만 적용되는 것이 아니다. 크레인은 선박 구조물, 해치 커버(Hatch Cover), 주변 컨테이너, 안벽 장비, 운송 차량, 다른 크레인까지 고려해야 한다. 기하학적 보호 구역(Geometric Protection Zone)과 센서 기반 장애물 감지(Sensor-Based Obstacle Detection)를 결합하여 위험한 궤적을 제한할 수 있다. 자동화 시스템은 선박 프로파일(Ship Profile) 또는 베이 모델(Bay Model)을 사용하여 허용 가능한 모션 통로(Motion Corridor)를 정의하면서 예상하지 못한 장애물에 대해서는 독립적인 비상 보호 기능을 유지할 수 있다.

육상 이송 인터페이스(Landside Transfer Interface)에서는 컨테이너 운송 차량과의 조정이 필수적이다. AGV 또는 AMR은 지정된 인계 위치(Handover Position)에 접근하여 크레인 시스템에 준비 상태를 보고한다. 크레인은 컨테이너를 하강시키기 전에 차량 식별 정보, 위치, 정지 상태, 이송 허가를 확인한다. 중요한 이송 단계에서는 차량이 움직이지 않도록 고정되어야 하며, 두 시스템 모두 명시적인 완료 신호를 교환한 이후에만 인계 상태를 종료할 수 있다.

안벽 크레인은 터미널 운영 시스템(Terminal Operating System, TOS) 및 장비 제어 인프라(Equipment-Control Infrastructure)와도 연결된다. 작업 대기열(Work Queue)은 어떤 컨테이너를 적재하거나 하역해야 하는지를 정의하고, 크레인 제어 소프트웨어는 이러한 물류 요구사항을 실제 물리적 하역 사이클로 변환한다. 실행 이벤트(Execution Event)는 컨테이너 상태를 갱신하고 후속 차량 배차를 가능하게 한다. 이러한 관계를 통해 안벽 크레인 자동화는 자동화 컨테이너 운송, 항만 교통 관리(Port Traffic Management), 컨테이너 인식(Container Recognition), TOS 통합과 직접 연결된다.

안전 로직(Safety Logic)은 생산성 중심의 자동화 기능보다 항상 우선적인 권한을 가져야 한다. 비상 정지(Emergency Stop), 이동 한계 초과 방지(Overtravel Limit), 과부하 감지(Overload Detection), 과속 보호(Overspeed Protection), 브레이크 감시(Brake Monitoring), 접근 인터록(Access Interlock), 풍속 제한(Wind Restriction), 충돌 보호(Collision Protection), 안전 운용 구역(Safe Operating Zone)은 각각 독립적으로 모션을 금지할 수 있다. 상위 수준 최적화 알고리즘이 더 빠른 동작을 요구하더라도 인증된 컨트롤러(Certified Controller) 또는 하드와이어드 보호 회로(Hardwired Protective Circuit)에 구현된 결정론적 안전 조건을 우회해서는 안 된다.

크레인은 외부 해양 환경에 지속적으로 노출되기 때문에 환경 조건(Environmental Condition)은 안벽 크레인 운용에 큰 영향을 미친다. 바람은 매달린 하중의 움직임을 증가시키고, 비와 안개는 광학 센서의 성능을 저하시킬 수 있으며, 염분 오염(Salt Contamination)은 장비에 영향을 줄 수 있고, 선박의 움직임은 목표 위치의 기하학적 관계를 변화시킬 수 있다. 따라서 자동화 소프트웨어는 관련 환경 및 장비 상태를 감시하고 모든 조건에서 정상 제어 파라미터가 유효하다고 가정하는 대신 필요한 경우 운용 한계를 조정해야 한다.

고장 관리(Fault Management)는 센서, 액추에이터, 통신 링크 또는 기계 서브시스템이 비정상적으로 동작할 때 크레인이 어떻게 대응해야 하는지를 정의한다. 정렬 센서 하나가 고장 난 경우 제한적인 수동 운전(Manual Operation)을 허용할 수 있지만, 서로 모순되는 트위스트 록 신호나 브레이크 고장은 자동 하역 작업을 즉시 중단해야 할 수 있다. 진단 소프트웨어(Diagnostic Software)는 고장 코드(Fault Code), 컨트롤러 상태, 센서 값, 시퀀스 전환 정보를 기록하여 유지보수 담당자가 중단된 컨테이너 작업 당시의 상태를 재구성할 수 있도록 한다.

운영 텔레메트리(Operational Telemetry)는 성능 최적화에도 활용된다. 사이클 시간은 픽업, 인양, 트롤리 이동, 하강, 인계, 복귀 단계로 세분화하여 병목 구간을 식별할 수 있다. 반복적인 흔들림 보정, 정렬 재시도, 차량 대기, 지연된 스프레더 잠금은 생산성 손실의 구체적인 원인을 보여줄 수 있다. 따라서 이력 데이터(Historical Data)는 저수준 크레인 동작을 시간당 컨테이너 처리량(Moves per Hour), 장비 활용률(Equipment Utilization), 선박 회전 시간(Vessel Turnaround Time)과 같은 터미널 수준의 성과 지표와 연결한다.

시뮬레이션(Simulation)과 디지털 트윈(Digital Twin)을 활용하면 실제 시스템에 배포하기 전에 크레인 시퀀스를 검증할 수 있다. 모델은 트롤리 및 호이스트 동역학, 매달린 하중의 흔들림, 스프레더 상호작용, 선박 형상, 차량 인계, 고장 시나리오를 재현할 수 있다. 소프트웨어 인 더 루프(Software-in-the-Loop, SIL) 시험은 시퀀싱 및 최적화 알고리즘을 평가하고, 하드웨어 인 더 루프(Hardware-in-the-Loop, HIL) 시험은 컨트롤러와 인터페이스를 검증한다. 반복 가능한 시뮬레이션은 정상적인 터미널 운용 과정에서는 안전하게 재현하기 어려운 드문 위험 조건을 시험하는 데 특히 유용하다.

안벽 크레인 자동화는 궁극적으로 독립된 장비가 아니라 통합적으로 조정되는 터미널 시스템의 일부로 동작한다. 크레인의 생산성은 자동화 컨테이너 운송(Automated Container Transport), 항만 교통 관리, 컨테이너 식별(Container Identification), 야드 운영(Yard Operation), 터미널 운영 시스템과의 동기화에 의해 결정된다. 따라서 항만 및 물류 자동화(Port and Logistics Automation)는 컨테이너 AMR 운송과 크레인 제어에서 시작하여 교통 관리, 컨테이너 인식, TOS 통합으로 이어지는 상호 연결된 자동화 구조로 발전한다.

미래의 안벽 크레인은 결정론적 산업 제어(Deterministic Industrial Control)와 인지(Perception), 인공지능 지원 최적화(AI-Assisted Optimization)를 더욱 긴밀하게 결합하게 될 것이다. 비전(Vision)은 컨테이너와 스프레더의 정렬 성능을 향상시킬 수 있고, 예측 모델(Predictive Model)은 모션 프로파일을 최적화할 수 있으며, 장비 상태 분석(Equipment-Health Analytics)은 실제 고장이 발생하기 전에 성능 저하를 식별할 수 있다. 이러한 지능형 기능은 검증된 모션 및 안전 계층을 대체하는 것이 아니라 보완해야 하며, 높은 에너지가 사용되는 컨테이너 하역 작업에서는 적응형 최적화(Adaptive Optimization)와 결정론적 보호(Deterministic Protection) 사이의 명확한 경계를 유지해야 한다.

## 09.04. Port Traffic Management System Integration [w/Code]

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

항만 교통 관리 시스템(Port Traffic Management System)은 터미널 도로, 교차로, 크레인 이송 구역, 컨테이너 야드(Container Yard), 게이트(Gate), 서비스 구역에서 자동화 차량과 사람이 운전하는 차량의 이동을 조정한다. 그 목적은 단순한 충돌 회피(Collision Avoidance)를 넘어선다. 시스템은 예측 가능한 물류 흐름을 유지하고, 혼잡과 교착 상태(Deadlock)를 방지하며, 제한 구역을 보호하고, 터미널 처리량(Terminal Throughput)을 유지하면서 차량의 이동을 컨테이너 하역 장비와 동기화해야 한다.

교통 관리 계층(Traffic-Management Layer)은 개별 차량의 자율주행 기능과 상위 수준의 차량군 또는 터미널 물류 시스템 사이에 위치한다. 차량군 관리자(Fleet Manager)는 어떤 AMR 또는 AGV가 운송 임무를 수행할지를 결정하고, 교통 시스템은 여러 차량이 인프라를 안전하게 공유하는 방법을 결정한다. 차량 내비게이션(Vehicle Navigation)은 승인된 경로를 로컬에서 실행한다. 이러한 분리를 통해 차량군 최적화, 교통 조정, 실시간 차량 제어가 일관된 운영 상태를 교환하면서 독립적으로 발전할 수 있다.

디지털 도로망(Digital Road Network)은 교통 조정에 사용되는 기본적인 표현을 제공한다. 터미널 차선, 교차로, 이송 지점, 대기 구역, 충전소, 제한 구역, 유지보수 구역을 그래프 노드(Graph Node), 엣지(Edge) 또는 기하학적 영역(Geometric Region)으로 표현할 수 있다. 각 요소에는 허용 방향, 속도 제한, 차량 등급, 수용 용량, 회전 제한, 안전 여유 거리, 일시적 가용성 등의 속성이 포함되어 소프트웨어가 운영 제약 조건을 판단할 수 있도록 한다.

운송 임무가 할당되면 차량 또는 차량군 서비스(Fleet Service)는 이러한 네트워크를 통과하는 경로를 요청한다. 교통 시스템은 이동 권한을 부여하기 전에 연결성, 거리, 혼잡도, 도로 제한, 목적지 접근 가능성, 다른 활성 차량의 이동 계획을 평가한다. 기하학적으로 가장 짧은 경로가 항상 운영상 최적의 경로인 것은 아니다. 약간 더 긴 경로를 선택함으로써 안벽 크레인(Quay Crane) 주변의 대기열을 줄이거나 이미 포화 상태에 가까운 교차로를 우회할 수 있다.

경로 예약(Route Reservation)은 자동화 차량을 조정하기 위한 일반적인 메커니즘이다. 모든 AMR이 이용 가능한 도로 구간에 독립적으로 진입하도록 허용하는 대신 교통 관리자는 차량이 도착하기 전에 중요한 구간 또는 자원을 예약한다. 예약은 교차로, 좁은 차선, 이송 구역 또는 기타 충돌 가능 영역에 적용될 수 있다. 차량은 필요한 자원을 사용할 수 있을 때만 이동하여 여러 장비가 서로 양립할 수 없는 경로에 동시에 진입할 가능성을 줄인다.

교차로 관리(Intersection Management)는 여러 경로가 동일한 물리적 공간을 사용하기 때문에 특히 정밀한 동기화가 필요하다. 시스템은 도착 순서, 임무 우선순위, 크레인 작업의 긴급성, 혼잡 상태 또는 예상 통과 시간에 따라 이동 권한을 부여할 수 있다. 비활성 차량이 교차로를 무기한 점유하지 않도록 통행 권한에는 명확한 소유권(Ownership)과 만료 규칙(Expiration Rule)이 포함되어야 한다. 중앙 교통 시스템에서 통행 권한을 부여한 이후에도 차량의 로컬 안전 기능은 계속 활성 상태를 유지해야 한다.

교착 상태(Deadlock)는 여러 차량이 서로 보유하고 있거나 필요로 하는 자원을 기다리면서 어느 차량도 진행할 수 없는 순환 구조가 형성될 때 발생한다. 차량들이 물리적으로 서로를 차단한 이후 복구하는 것보다 교착 상태를 사전에 방지하는 것이 바람직하다. 교통 소프트웨어는 자원 순서 규칙(Resource-Ordering Rule)을 적용하거나, 전체 중요 구간을 사전에 예약하거나, 혼잡 구역 진입을 제한하거나, 탈출 공간(Escape Area)을 유지할 수 있다. 그래프 기반 의존성 분석(Graph-Based Dependency Analysis)을 통해 이동 권한이 발행되기 전에 잠재적인 순환 예약 패턴을 식별할 수도 있다.

사전 방지만으로 충분하지 않은 경우에는 교착 상태 감지 및 복구(Deadlock Detection and Recovery)가 필요하다. 시스템은 차량 진행 상태, 대기 시간, 경로 의존성, 예약된 자원을 감시하여 교통 흐름의 정지가 정상적인 대기열 때문인지 실제 순환 충돌 때문인지를 판단한다. 복구 과정에서는 선택된 예약을 해제하거나, 특정 차량의 경로를 재설정하거나, 제어된 후퇴(Controlled Retreat)를 명령하거나, 일시적으로 우선순위를 변경할 수 있다. 대형 컨테이너 운송 차량의 경우 큰 회전 반경과 제한적인 후진 기동 능력을 고려한 복구 전략이 필요하다.

혼잡 관리(Congestion Management)는 교착 상태보다 더 광범위한 문제를 다룬다. 터미널은 차량이 계속 이동하고 있더라도 안벽 크레인, 야드 블록(Yard Block), 이송 스테이션 주변에 지나치게 많은 차량이 집중되면 생산성이 크게 감소할 수 있다. 교통 시스템은 도로 점유율, 대기열 길이, 평균 속도, 대기 시간, 목적지 수요를 감시할 수 있다. 이러한 측정값을 기반으로 동적 경로 설정(Dynamic Routing) 또는 진입 제어(Admission Control)를 수행하여 국부적인 혼잡이 터미널 전체로 확산되기 전에 교통 흐름을 분산할 수 있다.

교통 우선순위(Traffic Priority)는 모든 차량을 동일하게 처리하는 대신 물류 작업의 중요도를 반영해야 한다. 시간에 민감한 컨테이너 인계를 위해 안벽 크레인으로 접근하는 AMR은 주차 구역으로 이동하는 빈 차량보다 높은 우선순위를 받을 수 있다. 긴급 차량이나 유지보수 장비에는 특별한 우선권이 필요할 수 있다. 그러나 높은 우선순위의 교통만 지속적으로 우대하면 일반 임무가 무기한 지연되고 전체 차량군 효율이 감소할 수 있기 때문에 우선순위 정책에는 공정성 메커니즘(Fairness Mechanism)이 포함되어야 한다.

AMR 및 AGV 자율주행 시스템과 통합하기 위해서는 중앙 집중식 교통 조정과 차량 내 제어 사이에 명확한 역할 구분이 필요하다. 교통 시스템은 허용된 경로, 예약된 자원, 속도 제한, 정지 지점을 제공하고, 차량은 로컬 궤적 생성(Local Trajectory Generation)과 즉각적인 장애물 대응을 담당한다. 보행자 또는 예상하지 못한 차량이 경로에 진입한 경우 차량의 인지(Perception) 및 안전 기능은 중앙 교통 시스템의 명령을 기다리지 않고 즉각적으로 대응해야 한다.

혼합 교통(Mixed Traffic)은 사람이 운전하는 트럭과 서비스 차량이 디지털 예약 프로토콜(Digital Reservation Protocol)에 완전히 참여하지 않을 수 있기 때문에 추가적인 복잡성을 발생시킨다. 카메라, 라이다(LiDAR), 레이더(Radar), 노변 센서(Roadside Sensor), 연결형 인프라(Connected Infrastructure)를 통해 이러한 교통 참여자의 상태를 교통 시스템에 제공할 수 있다. 이들의 움직임은 결정론적이 아니라 확률적으로 표현될 수 있다. 이에 따라 자동화 차량에는 사람이 운전하는 차량으로 인해 불확실성이 증가하는 구역에서 보다 보수적인 통행 권한 또는 낮은 속도 제한을 적용할 수 있다.

크레인 이송 구역(Crane Transfer Zone)에서는 교통 시스템과 장비 제어 시스템(Equipment-Control System) 사이의 긴밀한 통합이 필요하다. 차량은 해당 자원을 사용할 수 있고 크레인이 이송 작업을 수행할 준비가 되었을 때만 안벽 크레인 또는 야드 크레인(Yard Crane)의 인계 위치에 진입해야 한다. 교통 관리자는 허가가 부여될 때까지 차량을 대기 구역(Staging Area)에 유지할 수 있다. 이를 통해 크레인 아래에서 불필요한 대기열이 형성되는 것을 방지하고 차량 이동과 컨테이너 하역 작업 사이의 간섭을 줄일 수 있다.

터미널 운영 시스템(Terminal Operating System, TOS)은 교통 관련 의사결정에 운영적 의미를 부여하는 물류 컨텍스트(Logistics Context)를 제공한다. TOS의 작업 계획은 컨테이너 이동 요구를 생성하고, 차량군 관리 소프트웨어는 이러한 이동 요구를 차량 임무로 변환하며, 교통 시스템은 결과적으로 발생하는 물리적 경로를 조정한다. 이후 실행 상태는 다시 시스템 아키텍처를 통해 상위 계층으로 전달된다. 이러한 구조에서 교통 관리는 자동화 컨테이너 운송, 안벽 크레인 자동화, 컨테이너 인식(Container Recognition), TOS 통합 사이를 연결하는 역할을 수행한다.

일관된 교통 상태를 유지하려면 실시간 통신(Real-Time Communication)이 필요하다. 차량은 주기적으로 위치, 속도, 임무 상태, 적재 상태, 경로 진행 상태, 고장 정보를 보고하고, 교통 서비스는 통행 권한, 제한 조건, 경로 재설정 명령, 인프라 상태를 배포한다. 오래된 정보를 감지할 수 있도록 메시지에는 타임스탬프(Timestamp)와 식별자(Identifier)가 포함되어야 한다. 오래된 차량 위치 정보를 기반으로 교통 결정을 내리면 위험하거나 비효율적인 동작이 발생할 수 있기 때문에 통신 지연(Communication Delay)을 명시적으로 고려해야 한다.

시스템은 통신 손실(Communication Loss)에 대한 예측 가능한 동작을 정의해야 한다. 연결이 끊어진 차량이 중앙 서비스에서 이미 만료된 것으로 판단한 예약을 사용하여 무기한 주행해서는 안 된다. 운영 설계에 따라 차량은 이미 승인된 구간까지 이동을 완료하거나, 안전한 위치에서 정지하거나, 즉시 제어된 정지 상태로 전환할 수 있다. 또한 교통 서버는 연결이 끊어진 차량과 해당 차량이 점유하고 있는 자원을 표시하여 다른 차량이 불확실한 공간으로 경로 설정되지 않도록 해야 한다.

동적 제한(Dynamic Restriction)을 사용하면 터미널이 변화하는 운영 조건에 대응할 수 있다. 유지보수, 사고, 건설 작업, 기상 조건, 노면 손상, 임시 장비 배치 등으로 특정 차선이 폐쇄될 수 있다. 운영자 또는 인프라 시스템은 모든 차량을 개별적으로 변경하지 않고 디지털 도로망 정보를 갱신할 수 있다. 이후 새로운 경로 요청은 제한 구역을 우회하고, 이미 해당 구역에 접근 중인 차량은 현재 위치에 따라 경로 재설정 또는 제어된 정지 명령을 받을 수 있다.

안전 구역 설정(Safety Zoning)은 교통 제어에 추가적인 계층을 제공한다. 구역별로 최대 속도, 진행 방향 제한, 최소 이격 거리, 특정 차량 유형에 대한 통행 권한을 설정할 수 있다. 보행자 구역과 유지보수 구역에서는 특히 보수적인 운행 정책이 요구될 수 있다. 교통 시스템에서 배포하는 지오펜스 정책(Geofenced Policy)은 차량 자체의 안전 기능을 보완할 수 있지만, 중앙 집중식 소프트웨어가 차량에 구현된 독립적인 비상 정지(Emergency Stop)와 보호 센싱(Protective Sensing)을 대체해서는 안 된다.

관측 가능성(Observability)은 교통 시스템의 장애가 개별적으로 정상인 여러 구성 요소 사이의 상호작용으로부터 발생하는 경우가 많기 때문에 필수적이다. 모니터링 시스템은 차량 위치, 예약 상태, 대기열, 차단된 자원, 도로 점유 상태, 통신 품질, 경로 변경을 시각화한다. 과거 이벤트 로그(Historical Event Log)를 이용하면 엔지니어가 혼잡 또는 교착 상태가 발생한 원인을 재구성할 수 있다. 평균 이동 시간, 교차로 지연, 대기열 길이, 경로 재설정 빈도, 차량 유휴 시간과 같은 지표는 최적화를 위한 정량적인 근거를 제공한다.

교통 데이터(Traffic Data)는 예측 제어(Predictive Control)에도 활용할 수 있다. 과거 및 실시간 정보를 분석하면 특정 선박 작업 부하에서 특정 교차로나 크레인 접근 구역이 반복적으로 혼잡해지는 패턴을 발견할 수 있다. 예측 모델(Predictive Model)은 미래의 도로 점유 상태를 추정하고 실제 혼잡이 발생하기 전에 경로를 변경할 수 있다. 이를 통해 교통 관리는 반응형 충돌 해결(Reactive Conflict Resolution)에서 선제적 흐름 최적화(Proactive Flow Optimization)로 발전할 수 있지만, 예측 기반 결정은 검증된 경로 설정 및 안전 제약의 범위 내에서 이루어져야 한다.

시뮬레이션(Simulation)과 디지털 트윈(Digital Twin)은 실제 배포 전에 교통 정책을 평가할 수 있는 효과적인 환경을 제공한다. 수백 대의 가상 차량이 터미널 도로망에서 실제와 유사한 임무를 수행하도록 구성하고 차량군 규모, 컨테이너 수요, 크레인 생산성, 교차로 정책, 고장 조건을 변화시킬 수 있다. 스트레스 시험(Stress Test)을 통해 도로 폐쇄, 통신 손실, 교통량 급증, 교착 상태를 의도적으로 발생시켜 조정 알고리즘이 위험한 명령을 생성하지 않고 정상적으로 복구되는지를 검증할 수 있다.

대규모 자동화 차량군에서는 중앙 집중식 교통 관리 시스템이 운영상 핵심 시스템이 될 수 있기 때문에 고가용성(High Availability)이 중요하다. 이중화 서비스(Redundant Service), 복제된 교통 상태(Replicated Traffic State), 상태 감시(Health Monitoring), 제어된 장애 조치(Controlled Failover)를 통해 하나의 서버 고장으로 전체 터미널이 정지하는 것을 방지할 수 있다. 상태 복구(State Recovery) 과정에서는 활성 예약과 차량의 자원 소유권을 정확하게 유지해야 한다. 그렇지 않으면 재시작된 서비스가 실제 차량이 점유하고 있는 물리적 자원에 대해 충돌하는 통행 권한을 발행할 수 있다.

완전히 통합된 항만 교통 관리 시스템(Port Traffic Management System)은 자율주행 차량, 크레인, 차량군 관리, 인프라, 터미널 물류를 연결하는 조정 기반(Coordination Fabric)으로 기능한다. 개별 로봇의 독립적인 이동을 시스템 수준에서 제어된 교통 흐름으로 변환하면서 즉각적인 환경 변화에 대응하기 위한 차량의 로컬 자율성(Local Autonomy)을 유지한다. 터미널이 더 큰 차량군으로 확장되면 예측 경로 설정(Predictive Routing)과 분산 지능(Distributed Intelligence)을 통해 처리량을 향상시킬 수 있지만, 결정론적 자원 소유권(Deterministic Resource Ownership), 안전한 고장 대응(Safe Failure Behavior), 추적 가능한 교통 의사결정(Traceable Traffic Decision)은 여전히 핵심적인 요구사항으로 유지되어야 한다.

## 09.05. Container OCR and ID Recognition AI [w/Code]

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

컨테이너 광학 문자 인식(Container OCR) 및 ID 인식(ID Recognition)은 실제 컨테이너의 이동과 터미널 정보 시스템(Terminal Information System)을 연결하는 디지털 식별 계층(Digital Identification Layer)을 제공한다. 게이트(Gate), 안벽 크레인(Quay Crane), 야드 장비(Yard Equipment), 이송 스테이션(Transfer Station), 자율주행 차량에 설치된 카메라가 컨테이너 표식을 촬영하고, 인공지능 기반 비전 소프트웨어(AI-Based Vision Software)가 식별 정보를 추출한다. 신뢰성 높은 인식을 통해 수작업 검사에 전적으로 의존하지 않고 모든 물리적 하역 이벤트를 올바른 컨테이너 기록과 연결할 수 있다.

표준 화물 컨테이너(Standard Freight Container)는 외부 표면에서 시각적으로 확인할 수 있는 식별 코드(Identification Code)를 갖는다. 인식 시스템은 개별 문자를 해석하기 전에 먼저 관련 표식 영역(Marking Region)을 찾아야 한다. 이미지에는 로고, 경고 라벨, 구조 리브(Structural Rib), 잠금 장치, 오염물, 기타 문자 정보가 함께 존재할 수 있기 때문에 컨테이너 OCR은 단순히 전체 이미지의 문자를 읽는 문제가 아니다. 일반적으로 검출(Detection)과 인식(Recognition)을 서로 연계된 처리 단계로 분리하여 수행한다.

이미지 획득(Image Acquisition)은 인식 정확도에 큰 영향을 준다. 카메라는 심각한 원근 왜곡(Perspective Distortion)과 가림(Occlusion)을 최소화하면서 충분한 해상도를 확보할 수 있는 위치에 설치해야 한다. 노출(Exposure), 셔터 속도(Shutter Speed), 초점(Focus), 프레임 속도(Frame Rate), 조명(Illumination)은 이동하는 차량과 실외 운용 환경을 고려하여 선택해야 한다. 여러 대의 카메라로 컨테이너의 서로 다른 표면을 관찰하면 한 시점에서 코드가 가려지거나 손상되어도 다른 시점에서 확인할 수 있어 물류 프로세스를 중단하지 않고 인식 이중화(Recognition Redundancy)를 높일 수 있다.

첫 번째 인공지능 처리 단계에서는 일반적으로 이미지 내부의 컨테이너 또는 식별 코드 영역을 검출한다. 객체 검출(Object Detection) 또는 문자 영역 검출(Text Detection) 모델을 이용하여 후보 표식 주변에 바운딩 박스(Bounding Box) 또는 폴리곤(Polygon)을 생성할 수 있다. 영역 검출은 OCR 처리 전에 불필요한 시각 정보를 줄이고 서로 다른 위치와 크기로 나타나는 컨테이너를 처리할 수 있도록 한다. 비디오 프레임 간 추적(Tracking)을 적용하면 컨테이너가 카메라 시야를 통과하는 동안 후보 영역의 동일성을 지속적으로 유지할 수 있다.

문자 인식 전에 검출된 영역에 기하학적 및 광학적 전처리(Geometric and Photometric Preprocessing)를 적용할 수 있다. 원근 보정(Perspective Correction)은 비스듬하게 촬영된 문자 영역을 정규화된 정면 형태로 변환하고, 크기 조정(Resizing)과 대비 정규화(Contrast Normalization)는 인식 모델에 입력되는 이미지의 일관성을 향상시킨다. 필요한 경우 노이즈 제거(Noise Reduction), 디블러링(Deblurring), 조명 보정(Illumination Compensation), 그림자 보정(Shadow Correction)을 적용할 수 있다. 지나치게 강한 영상 개선은 문자 획을 제거하거나 잘못된 경계를 생성할 수 있으므로 전처리 과정에서는 원래의 문자 형태를 보존해야 한다.

문자 인식(Character Recognition)은 정규화된 이미지 영역을 문자와 숫자의 시퀀스(Sequence)로 변환한다. 전통적인 OCR 파이프라인은 개별 문자를 분할하여 인식할 수 있지만, 현대적인 딥러닝(Deep Learning) 방식은 전체 문자 시퀀스를 직접 인식할 수 있다. 합성곱 신경망(Convolutional Neural Network), 순환 신경망(Recurrent Neural Network), 어텐션 기반(Attention-Based), 트랜스포머 기반(Transformer-Based) 인식 아키텍처는 문자 패턴 사이의 시각적 관계를 학습하고 문자 시퀀스를 출력할 수 있다. 시퀀스 수준 인식(Sequence-Level Recognition)은 문자 간격이나 분할 경계를 안정적으로 결정하기 어려운 경우 특히 유용하다.

컨테이너 인식(Container Recognition)은 가능한 모든 문자 조합을 동일하게 취급하는 대신 도메인 특화 구조(Domain-Specific Structure)를 활용할 수 있다. 예상되는 식별자 형식, 허용 문자 종류, 알려진 접두부(Prefix), 검사 규칙(Check Rule)을 이용하여 인식 결과를 제한할 수 있다. 모델은 신뢰도 점수(Confidence Score)를 갖는 여러 후보 시퀀스를 출력하고, 이후 검증 로직(Validation Logic)이 컨테이너 식별 규칙에 부합하는 후보를 선택할 수 있다. 시각적 추론(Visual Inference)과 구조적 검증(Structural Validation)을 결합하면 시각적으로 유사한 문자로 인해 발생하는 오류를 크게 줄일 수 있다.

문자 모호성(Character Ambiguity)은 열악한 촬영 조건에서 O와 0, I와 1, B와 8, S와 5처럼 문자와 숫자의 형태가 유사하게 보일 수 있기 때문에 반복적으로 발생하는 문제이다. 인식 소프트웨어는 즉시 하나의 결과만 확정하는 대신 문자 수준 신뢰도(Character-Level Confidence)를 유지해야 한다. 식별자 문법(Identifier Syntax), 검사 숫자(Check Digit), 여러 카메라의 관측 결과, 기존 터미널 기록 등을 이용하여 대체 후보(Alternative Hypothesis)를 평가하고 가장 가능성이 높은 컨테이너 식별 정보를 결정할 수 있다.

비디오 기반 인식에서는 시간적 융합(Temporal Fusion)을 통해 신뢰성을 향상시킬 수 있다. 이동하는 컨테이너는 수십 개의 프레임에 걸쳐 관측될 수 있으며 각 프레임은 조금씩 다른 시점을 제공한다. 시스템은 하나의 프레임에서 얻은 결과를 즉시 채택하는 대신 시간에 따른 예측 결과를 통합하여 합의된 시퀀스(Consensus Sequence)를 선택할 수 있다. 모션 블러(Motion Blur), 눈부심(Glare), 가림, 극단적인 원근 왜곡이 발생한 프레임에는 낮은 가중치를 부여하고 선명한 관측 결과에는 더 높은 가중치를 적용할 수 있다.

다중 카메라 융합(Multi-Camera Fusion)은 동일한 원리를 여러 시점으로 확장한다. AMR에 의해 운송되는 컨테이너는 고정형 카메라 또는 차량 탑재 센서를 통해 전면, 후면, 측면에서 관찰될 수 있다. 이러한 카메라의 인식 결과는 타임스탬프(Timestamp), 차량 식별 정보, 공간적 위치, 임무 정보를 이용하여 서로 연계할 수 있다. 독립적인 관측 결과가 일치하면 신뢰도가 증가하며, 결과가 서로 다르면 불확실한 정보를 터미널 데이터베이스에 그대로 갱신하는 대신 추가적인 검증 절차를 수행한다.

컨테이너 ID 인식은 물리적인 컨테이너 검출(Physical Container Detection)과도 연결되어야 한다. 동일한 장면에 여러 개의 컨테이너가 존재하는 경우 시스템은 인식된 코드가 어떤 실제 컨테이너에 해당하는지를 판단해야 한다. 컨테이너 바운딩 영역(Container Bounding Region)과 검출된 문자 영역 사이의 공간적 연관 관계(Spatial Association)를 이용하여 초기 연결 관계를 설정할 수 있다. 추적, 깊이 정보(Depth Information), 크레인 상태, 차량 위치, 야드 슬롯(Yard Slot) 정보를 추가하면 컨테이너가 인양, 운송, 적재 또는 이송되는 과정에서도 이러한 관계를 유지할 수 있다.

실제 운영 환경에 배포하기 위해서는 신뢰도 관리(Confidence Management)가 필수적이다. 인식 파이프라인은 식별자뿐만 아니라 해당 식별 결과가 얼마나 신뢰할 수 있는지를 나타내는 근거도 함께 출력해야 한다. 신뢰도는 검출 품질, OCR 확률, 구조적 검증 결과, 다중 프레임 일치도, 다중 카메라 일관성을 조합하여 계산할 수 있다. 높은 신뢰도의 결과는 자동으로 승인하고, 중간 신뢰도의 결과는 추가 관측을 요청하며, 낮은 신뢰도의 결과는 운영자 검증(Operator Verification)으로 전달할 수 있다.

인식 실패(Recognition Failure)는 숨겨진 소프트웨어 오류가 아니라 명시적인 운영 이벤트(Operational Event)로 처리해야 한다. 오염, 부식, 손상된 표식, 적재된 컨테이너에 의한 가림, 강한 햇빛, 야간 환경, 비, 모션 블러, 물리적 장애물로 인해 신뢰할 수 있는 OCR이 불가능할 수 있다. 시스템은 코드가 보이지 않는 경우, 문자를 읽을 수 없는 경우, 관측 결과가 충돌하는 경우, 식별 형식이 유효하지 않은 경우, 카메라가 고장 난 경우를 구분해야 한다. 각각의 상태에는 서로 다른 복구 동작(Recovery Action)이 필요하기 때문이다.

자율 컨테이너 운송(Autonomous Container Transport)과 통합하면 인식 기능을 임무 검증(Mission Verification)의 일부로 사용할 수 있다. AMR이 픽업 임무를 수신하면 물류 시스템으로부터 예상 컨테이너 식별 정보를 이미 전달받는다. 운송을 시작하기 전에 카메라 관측 결과를 이용하여 실제 컨테이너와 예상 식별 정보를 비교할 수 있다. 정보가 일치하지 않으면 임무 진행을 중지하고 검증을 요청하여 정상적으로 작동하는 로봇이 잘못된 컨테이너를 잘못된 목적지로 효율적으로 운송하는 상황을 방지할 수 있다.

안벽 크레인(Quay Crane) 및 야드 크레인(Yard Crane)과 통합하면 추가적인 컨테이너 식별 확인 지점을 제공할 수 있다. 크레인 또는 이송 구역 주변에 설치된 카메라는 컨테이너를 인양하기 직전이나 직후에 식별 정보를 인식할 수 있다. 관측된 식별자는 스프레더 잠금 상태(Spreader Lock State), 크레인 위치, 차량 식별 정보, 작업 지시(Work Instruction)와 연계할 수 있다. 이를 통해 최초 계획된 이동 정보에만 의존하지 않고 디지털 컨테이너 기록과 특정 물리적 이송 작업을 연결하는 추적 가능한 이벤트(Traceable Event)를 생성할 수 있다.

터미널 운영 시스템(Terminal Operating System, TOS)과의 통합은 인식 결과를 실제 물류 정보로 변환한다. OCR 서비스는 예상 컨테이너 기록을 입력받고 인식된 식별자, 신뢰도 값, 타임스탬프, 카메라 위치, 관련 장비 정보를 반환할 수 있다. 이후 TOS 또는 장비 제어 계층(Equipment-Control Layer)은 관측된 컨테이너가 계획된 이동 대상과 일치하는지를 검증한다. 이러한 연결을 통해 컨테이너 인식은 전체 항만 자동화 아키텍처에서 물리적 자동화와 디지털 재고 관리(Digital Inventory Management)를 연결하는 역할을 수행한다.

인식 서비스(Recognition Service)는 이후의 감사를 위해 관련 증거를 보존해야 한다. 운영 정책에 따라 관련 이미지, 잘라낸 문자 영역(Cropped Text Region), OCR 후보, 신뢰도 값, 모델 버전(Model Version), 타임스탬프, 장비 식별 정보, 최종 검증 결과를 저장할 수 있다. 이후 컨테이너가 예상하지 못한 위치에서 발견되면 이러한 기록을 이용하여 원인이 인식 오류, 잘못된 임무 할당, 물리적 하역 오류 또는 터미널 데이터베이스의 불일치 때문인지를 분석할 수 있다.

데이터셋 설계(Dataset Design)는 인공지능 인식 성능에 큰 영향을 준다. 학습 및 검증 데이터는 서로 다른 컨테이너 색상, 글꼴, 관측 각도, 코드 위치, 조명 조건, 기상 조건, 카메라 종류, 이동 속도, 오염 수준, 물리적 손상 정도를 포함해야 한다. 운영상 중요하지만 드물게 발생하는 사례가 깨끗한 주간 이미지가 대부분인 데이터셋에 묻혀서는 안 된다. 합성 데이터 증강(Synthetic Augmentation)을 이용하여 원근 변화, 블러, 노이즈, 그림자, 가림 등을 제어된 방식으로 추가함으로써 실제 관측 데이터를 보완할 수 있다.

모델 평가(Model Evaluation)는 단순한 문자 정확도뿐만 아니라 전체 식별 성능을 측정해야 한다. 문자 하나만 잘못 인식해도 실제 컨테이너가 잘못된 디지털 기록과 연결될 수 있기 때문에 전체 시퀀스 정확도(Exact Sequence Accuracy)가 운영상 중요하다. 검출 재현율(Detection Recall), 문자 정확도(Character Accuracy), 전체 ID 정확도(Full-ID Accuracy), 오승인율(False Acceptance Rate), 거부율(Rejection Rate), 신뢰도 보정(Confidence Calibration), 처리 지연 시간(Processing Latency)을 각각 평가할 수 있다. 또한 환경 조건별로 성능을 분석하여 취약한 운용 조건을 파악해야 한다.

엣지 컴퓨팅(Edge Computing)은 크레인, 게이트 또는 자율주행 차량 가까이에서 카메라 스트림을 처리함으로써 인식 지연 시간(Recognition Latency)을 줄일 수 있다. 로컬 추론(Local Inference)을 적용하면 중앙 서버와의 연결이 일시적으로 저하되어도 식별 판단 기능을 유지할 수 있다. 중앙 서비스는 전체 터미널의 인식 결과를 통합하고, 모델 버전을 관리하며, 차량군 수준의 성능을 분석하고, 모델 재학습을 수행할 수 있다. 이러한 분산 아키텍처(Distributed Architecture)는 즉각적인 운영 대응과 터미널 전체 데이터 관리 및 지속적인 성능 개선 사이의 균형을 제공한다.

컨테이너 OCR 및 ID 인식은 궁극적으로 인지와 물류를 연결하는 가교(Perception-to-Logistics Bridge)로 기능한다. 시스템은 실제 터미널에서 획득한 시각적 증거를 검증된 식별 정보로 변환하여 AMR 임무, 크레인 자동화, 교통 조정, 터미널 애플리케이션에서 사용할 수 있도록 한다. 인공지능 모델의 성능이 향상되면서 인식 과정은 더욱 자동화될 수 있지만, 신뢰성 있는 실제 배포를 위해서는 이중화(Redundancy), 신뢰도 기반 의사결정(Confidence-Aware Decision), 구조적 검증, 추적 가능한 증거(Traceable Evidence), 불확실한 결과에 대한 안전한 처리(Safe Handling)가 지속적으로 보장되어야 한다.

## 09.06. Port TOS Integration with Robot Fleet [w/Code]

![](images/image6.png){width="7.268055555555556in" height="7.268055555555556in"}

터미널 운영 시스템(Terminal Operating System, TOS)은 컨테이너 재고(Container Inventory), 선박 운영(Vessel Operation), 야드 위치(Yard Location), 작업 대기열(Work Queue), 터미널 자원(Terminal Resource)을 관리하는 물류 조정 계층(Logistics Coordination Layer)을 제공한다. 로봇 차량군(Robot Fleet)은 안벽 크레인(Quay Crane), 야드 블록(Yard Block), 이송 스테이션(Transfer Station), 게이트(Gate), 기타 운영 구역 사이에서 컨테이너를 이동시키는 물리적 실행 계층(Physical Execution Layer)을 제공한다. 이 두 계층의 통합은 물류 계획을 실행 가능한 로봇 임무(Robot Mission)로 변환하고 실제 수행 결과를 터미널의 디지털 운영 상태로 다시 전달한다.

TOS는 일반적으로 개별 로봇의 세부적인 모션 동작(Motion Behavior)과 독립적으로 유지되어야 한다. TOS는 어떤 컨테이너를 이동해야 하는지, 이동이 어디에서 시작되고 어디에서 종료되어야 하는지, 언제 작업이 필요한지를 지정한다. 차량군 관리 계층(Fleet-Management Layer)은 이러한 비즈니스 수준의 작업 지시를 로봇별 작업으로 변환한다. 이러한 분리를 통해 TOS가 조향, 위치 추정(Localization), 배터리 관리, 장애물 회피(Obstacle Avoidance) 또는 기타 차량 수준의 구현 세부사항을 직접 이해할 필요가 없도록 한다.

컨테이너 이동 요청(Container Movement Request)을 처리하기 위해서는 통합 인터페이스 전체에서 공유되는 일관된 데이터 모델(Data Model)이 필요하다. 일반적인 정보에는 컨테이너 식별 정보, 출발 위치, 목적지 위치, 작업 식별자(Job Identifier), 우선순위, 필요한 장비, 운영 제약 조건, 시간 정보가 포함된다. 추가적인 속성에는 컨테이너 크기, 중량, 위험물 또는 특수 취급 상태, 예상 크레인 인터페이스 등이 포함될 수 있다. 안정적인 식별자를 사용하면 전체 운송 작업 흐름에서 모든 시스템이 동일한 실제 화물을 일관되게 참조할 수 있다.

차량군 관리 시스템(Fleet-Management System)은 운송 작업 지시(Transport Order)를 수신하고 사용 가능한 로봇 차량군을 이용하여 이를 어떻게 실행할지를 결정한다. 할당 로직(Assignment Logic)은 로봇 위치, 적재 능력, 배터리 상태, 유지보수 상태, 현재 임무, 경로 가용성, 예상 완료 시간을 평가할 수 있다. 이렇게 생성된 임무에는 선택된 AMR 또는 AGV가 운송 작업을 수행하는 데 필요한 충분한 정보가 포함되며, 불필요한 차량 세부 정보가 TOS로 다시 노출되지 않도록 한다.

실제 물류 작업은 즉각적으로 완료되는 데이터베이스 트랜잭션(Database Transaction)으로 처리할 수 없기 때문에 임무 상태(Mission State)를 명시적으로 표현해야 한다. 운송 요청은 접수(Accepted), 할당(Assigned), 배차(Dispatched), 픽업 접근(Approaching Pickup), 대기(Waiting), 적재(Loading), 운송(Transporting), 하역(Unloading), 완료(Completed), 실패(Failed), 취소(Cancelled) 등의 상태를 거칠 수 있다. 상태 전환(State Transition)은 통합 계층으로 보고되어 TOS가 계획된 이동과 실제로 픽업 또는 배송이 완료된 컨테이너를 구분할 수 있도록 한다.

컨테이너 식별 정보(Container Identity)는 디지털 작업 지시(Digital Work Order)와 실제 화물을 연결하는 핵심 요소이다. 픽업 전에 로봇, 크레인, OCR 서비스 또는 이송 스테이션은 실제로 관측된 컨테이너가 TOS에서 지정한 식별자와 일치하는지를 확인할 수 있다. 정보가 일치하지 않는 경우 임무를 그대로 진행하는 대신 예외(Exception)를 발생시켜야 한다. 이러한 검증은 전체 항만 자동화 작업 흐름에서 TOS 통합을 컨테이너 OCR 및 ID 인식(Container OCR and ID Recognition) 기능과 직접 연결한다.

픽업 실행(Pickup Execution)에는 일반적으로 로봇 차량군, 교통 시스템(Traffic System), 크레인 제어 시스템(Crane-Control System) 사이의 조정이 필요하다. 할당된 차량은 대기 또는 인계 구역(Handover Area)으로 이동하여 도착 상태를 보고한다. 장비 제어 계층(Equipment-Control Layer)은 이송을 허가하기 전에 크레인과 차량이 모두 준비되었는지를 확인한다. 컨테이너 존재 또는 잠금 상태가 확인되면 임무는 적재 운송(Loaded Transport) 단계로 진행된다. TOS에는 저수준 액추에이터 또는 센서 메시지가 아니라 물류적으로 의미 있는 이벤트가 전달된다.

교통 관리 통합(Traffic-Management Integration)을 통해 차량군 임무가 서로 충돌하는 차량 이동을 발생시키지 않도록 실행할 수 있다. 차량군 관리자는 특정 작업에 가장 적합한 로봇을 선택할 수 있지만, 교통 시스템은 필요한 경로와 이송 자원을 현재 사용할 수 있는지를 결정한다. 혼잡, 도로 폐쇄, 경로 예약(Route Reservation), 크레인 대기열은 실제 임무 실행 시간을 변화시킬 수 있다. 따라서 차량군 스케줄링(Fleet Scheduling)은 차량이 제한 없이 이동할 수 있다고 가정하는 대신 교통 조정 시스템과 경로 및 자원 정보를 교환해야 한다.

배송(Delivery) 과정도 이와 유사한 조정 절차를 따른다. 로봇은 목적지에 접근하고 이송 구역 진입 허가를 획득한 후 최종 위치 정렬(Final Positioning)을 수행하고, 컨테이너를 인수하는 크레인 또는 스테이션과 준비 상태 신호를 교환한다. 로봇이 비적재 상태로 전환되기 전에 컨테이너 해제가 확인되어야 한다. 실제 물리적 인계가 검증된 이후에만 운송 임무가 완료된 것으로 보고하여 디지털 재고 상태가 실제 컨테이너 이동보다 먼저 변경되는 것을 방지해야 한다.

이벤트 기반 통합(Event-Driven Integration)은 여러 시스템이 내부 구현을 강하게 결합하지 않고 상태 변화에 대응해야 하는 터미널 자동화에 적합하다. 이벤트는 임무 생성, 할당, 픽업, 컨테이너 검증, 경로 차단, 도착, 인계, 완료, 실패 등을 표현할 수 있다. 각 이벤트에는 타임스탬프(Timestamp), 발생 소스(Source), 관련 식별자, 상태 정보가 포함되어야 한다. 이를 통해 각 시스템은 권한 있는 데이터(Authoritative Data)의 명확한 소유 관계를 유지하면서 자체적인 운영 상태를 갱신할 수 있다.

응용 프로그래밍 인터페이스(Application Programming Interface, API)와 메시지 지향 미들웨어(Message-Oriented Middleware)는 TOS, 차량군 관리자, 교통 시스템, 장비 제어 서비스, 모니터링 플랫폼 사이의 통신 경계를 제공할 수 있다. 즉각적인 응답이 필요한 경우에는 동기식 요청(Synchronous Request)이 유용하고, 임무 및 상태 이벤트에는 비동기 메시징(Asynchronous Messaging)이 적합하다. 개별 서브시스템이 발전하더라도 인터페이스가 안정적으로 유지되도록 통합 아키텍처는 스키마(Schema), 버전 관리(Versioning), 확인 응답(Acknowledgement), 재시도 정책(Retry Policy), 오류 처리(Error Handling)를 정의해야 한다.

멱등성(Idempotency)은 통신 장애로 인해 메시지가 재전송될 수 있기 때문에 중요하다. 임무 완료 이벤트가 두 번 전달되더라도 TOS가 이를 서로 다른 두 번의 컨테이너 이동으로 해석해서는 안 된다. 고유한 트랜잭션 및 임무 식별자(Unique Transaction and Mission Identifier)를 이용하면 수신 시스템이 중복 요청이나 이벤트를 인식할 수 있다. 또한 필요한 경우 이벤트 순서를 유지하여 지연된 픽업 메시지가 이후에 확인된 배송 완료 상태를 잘못 덮어쓰지 않도록 해야 한다.

일시적인 통신 장애(Temporary Communication Failure)가 발생했다고 해서 진행 중인 실제 물리적 임무를 자동으로 폐기해서는 안 된다. 로봇과 차량군 시스템은 이전에 승인된 이동을 완료하면서 상태 이벤트를 로컬에 버퍼링(Buffering)할 수 있다. 연결이 복구되면 저장된 이벤트를 올바른 순서로 TOS와 동기화할 수 있다. 그러나 운영 정책에 따라 새로운 임무 또는 중요한 상태 변경에는 통신 연결이 필수적일 수 있다. 따라서 자율적인 임무 지속(Autonomous Continuation)과 의무적인 정지(Mandatory Stop) 사이의 경계를 명확하게 정의해야 한다.

예외 관리(Exception Management)는 TOS와 차량군 통합에서 가장 중요한 책임 중 하나이다. 사용 가능한 로봇 부재, 경로 차단, 잘못된 컨테이너, 크레인 고장, 통신 손실, 배터리 부족, 안전 정지(Safety Stop), 접근 불가능한 목적지 등의 이유로 임무가 실패할 수 있다. 차량군 계층은 예외를 분류하고 영향을 받은 임무와 현재 실제 컨테이너 상태를 함께 보고해야 한다. 그러면 TOS는 화물 추적성(Cargo Traceability)을 잃지 않으면서 작업을 재스케줄링하거나 다른 자원을 선택하거나 운영자 개입을 요청할 수 있다.

임무 취소(Mission Cancellation)는 디지털 취소 명령이 실제 물리적 작업이 이미 시작된 이후 도착할 수 있기 때문에 특히 주의가 필요하다. 아직 할당되지 않은 작업을 취소하는 것은 단순하지만 컨테이너를 운반 중인 로봇의 임무를 취소하려면 안전한 대체 목적지 또는 복구 절차가 필요하다. 따라서 통합 계층은 취소 요청을 승인하기 전에 현재 임무 단계를 평가해야 한다. TOS의 비즈니스 명령이 로봇으로 하여금 정의되지 않았거나 안전하지 않은 상태에서 실제 작업을 중단하도록 강제해서는 안 된다.

차량군 가용성 정보(Fleet Availability Information)는 TOS 계획을 향상시킬 수 있다. 통합 계층은 사용 가능한 차량 수, 충전 중인 로봇, 유지보수 중인 차량, 예상 임무 완료 시간, 혼잡 지표(Congestion Indicator), 장비 제약 조건 등을 제공할 수 있다. TOS는 무제한의 운송 능력이 존재한다고 가정하는 대신 이러한 정보를 컨테이너 작업 순서를 결정할 때 활용할 수 있다. 이를 통해 물류 계획이 실제 로봇 실행 자원의 상태를 인식하는 피드백 루프(Feedback Loop)가 형성된다.

에너지 관리(Energy Management)는 물류와 차량군 운영 사이에 또 다른 연결 관계를 형성한다. 충전 일정은 사용 가능한 로봇의 수에 영향을 미치고, 선박 및 크레인의 작업량은 향후 운송 수요를 결정한다. 차량군 소프트웨어는 계획된 TOS 작업을 기반으로 필요한 에너지를 예측하고 운송 능력이 부족해지기 전에 충전을 예약할 수 있다. 반대로 차량군의 에너지 가용성이 일시적으로 제한되면 TOS가 낮은 우선순위의 작업을 조정하여 터미널 수준의 자원 활용률을 향상시킬 수 있다.

여러 시스템에서 생성된 이벤트를 통합할 때는 시간 동기화(Time Synchronization)가 중요하다. TOS 기록, 로봇 텔레메트리(Robot Telemetry), 교통 예약, 크레인 핸드셰이크(Crane Handshake), OCR 관측 정보, 안전 이벤트는 서로 다른 관점에서 동일한 컨테이너 이동을 표현할 수 있다. 일관된 타임스탬프를 사용하면 이러한 이벤트의 순서를 정확하게 재구성할 수 있다. 또한 차량 이동 시간, 크레인 대기 시간, 이송 시간, 혼잡 지연, 시스템 응답 지연(System-Response Latency)을 분리하여 성능을 분석할 수 있다.

모니터링(Monitoring)은 각 계층의 책임을 혼동하지 않으면서 물류 수준과 로봇 수준의 가시성을 모두 제공해야 한다. 운영자는 하나의 운영 화면에서 컨테이너 작업, 할당된 차량, 임무 진행 상태, 지연된 이송, 차단된 경로, 장비 고장, 통신 상태를 확인해야 할 수 있다. 필요한 경우 상세 보기(Drill-Down)를 통해 세부적인 로봇 텔레메트리를 확인할 수 있다. 이러한 계층형 관측 가능성(Layered Observability)을 통해 컨테이너 지연이 TOS 스케줄링, 차량군 할당, 교통 혼잡, 크레인 가용성 또는 차량 고장 중 어떤 원인에서 발생했는지를 판단할 수 있다.

사이버보안(Cybersecurity)은 TOS 통합이 기업 물류 소프트웨어와 실제 물리적 이동이 가능한 장비를 연결하기 때문에 매우 중요하다. 시스템은 통신 서비스를 인증(Authentication)하고, 임무 관련 동작에 대한 권한을 부여(Authorization)하며, 메시지 무결성(Message Integrity)을 보호하고, 주요 명령 및 상태 변경에 대한 감사 기록(Audit Record)을 유지해야 한다. 네트워크 분할(Network Segmentation)을 통해 기업, 운영, 안전 관련 도메인을 분리할 수 있다. 침해된 비즈니스 애플리케이션이 차량 액추에이터나 안전 기능에 제한 없이 직접 접근할 수 있어서는 안 된다.

시뮬레이션 및 통합 시험(Simulation and Integration Testing)은 TOS 작업 생성부터 실제 임무 완료까지 전체 작업 흐름을 재현해야 한다. 가상 로봇, 크레인, 교통 서비스, OCR 구성 요소, 장비 인터페이스를 시험용 TOS 또는 통합 환경과 연결할 수 있다. 시험 사례에는 정상 운송뿐만 아니라 중복 메시지, 지연된 이벤트, 통신 손실, 컨테이너 불일치, 경로 차단, 임무 취소, 서브시스템 재시작을 포함하여 기능적 동작과 상태 일관성(State Consistency)을 모두 검증해야 한다.

로봇 및 자동화 장비의 수가 증가할수록 확장 가능한 통합(Scalable Integration)의 중요성도 증가한다. TOS는 수백 대의 개별 장비와 직접 세션을 유지하기보다 차량군 및 장비 서비스(Fleet and Equipment Service)를 중심으로 통신해야 한다. 계층적 조정(Hierarchical Coordination)은 인터페이스 복잡성을 줄이고 터미널 비즈니스 로직을 다시 설계하지 않고도 로봇을 교체하거나 업그레이드할 수 있도록 한다. 표준화된 임무 및 이벤트 모델(Standardized Mission and Event Model)은 서로 다른 세대 또는 제조사의 이기종 차량군(Heterogeneous Fleet)도 지원할 수 있도록 한다.

항만 TOS와 로봇 차량군의 통합은 궁극적으로 폐쇄형 디지털-물리 물류 루프(Closed Digital-to-Physical Logistics Loop)를 구성한다. TOS가 운영 의도(Operational Intent)를 표현하면 차량군 소프트웨어가 이를 실행 가능한 임무로 변환하고, 교통 및 장비 시스템이 실제 물리적 자원을 조정하며, 로봇이 이동 작업을 수행한 후 검증된 실행 이벤트가 다시 터미널 상태를 갱신한다. 신뢰성 높은 자동화를 위해서는 일관된 식별 정보, 명시적인 상태 전환, 강건한 예외 처리(Robust Exception Handling), 추적 가능한 이벤트, 안전한 인터페이스(Secure Interface), 명확한 책임 경계(Responsibility Boundary)를 유지해야 한다.

## 09.07. Last Mile Delivery AMR Urban Environment [w/Code]

![](images/image7.png){width="7.268055555555556in" height="7.268055555555556in"}

라스트 마일 배송 자율 이동 로봇(Last-Mile Delivery AMR)은 통제된 창고 및 터미널에서 수행되던 자율 물류(Autonomous Logistics)를 공공 또는 준공공 도시 환경(Urban Environment)으로 확장한다. 이러한 로봇은 지역 물류 거점과 최종 목적지 사이에서 소포, 음식, 의료 물품, 소매 상품 또는 기타 소형 화물을 운송한다. 구조화된 산업 시설 내부에서 운용되는 산업용 AMR과 달리 도시형 배송 로봇은 보도, 횡단 구역, 건물 출입구, 보행자, 자전거, 임시 장애물, 지속적으로 변화하는 환경 조건을 고려하여 주행해야 한다.

도시 공간은 부분적으로만 구조화되어 있기 때문에 운용 환경 자체가 어려운 인지 문제(Perception Problem)를 발생시킨다. 보도의 경계가 명확하지 않을 수 있고, 공사로 인해 익숙한 경로가 변경될 수 있으며, 주차된 차량이 시야를 차단하고, 보행자가 예측하기 어려운 방식으로 움직일 수 있다. 따라서 로봇은 사전에 정의된 지도에만 의존하지 않고 지속적인 환경 인지(Environmental Perception)를 수행해야 한다. 카메라(Camera), 라이다(LiDAR), 레이더(Radar), 초음파 센서(Ultrasonic Sensor), 관성 측정(Inertial Measurement)은 안전한 주행을 위한 상호 보완적인 정보를 제공할 수 있다.

위치 추정(Localization)은 전역 및 지역 위치 정보를 결합하여 배송 임무 전체에서 로봇의 자세 및 위치(Robot Pose)를 추정한다. GNSS는 실외의 지리적 위치를 제공할 수 있으며, 비전(Visual), 라이다, 관성 센서, 휠 오도메트리(Wheel Odometry)는 지역적인 정확도와 위치 추정의 연속성을 지원한다. 고층 건물이 밀집한 지역에서는 GNSS 다중 경로(GNSS Multipath) 또는 신호 차단이 발생할 수 있기 때문에 센서 융합(Sensor Fusion)이 특히 중요하다. 위치 신뢰도가 낮아질 때 주행 동작을 보다 보수적으로 변경할 수 있도록 위치 추정 시스템은 불확실성(Uncertainty)도 함께 추정해야 한다.

도시 지도(Urban Map)는 단순한 기하학적 점유 지도(Geometric Occupancy Map)보다 더 많은 의미 정보를 포함한다. 로봇은 보도, 보행자 횡단 구역, 차량 진출입로, 건물 출입구, 경사로, 계단, 연석(Curb), 자전거 도로, 차도, 제한 구역, 배송 구역을 구분해야 할 수 있다. 의미론적 매핑(Semantic Mapping)은 기하학적 내비게이션과 운영 규칙을 연결한다. 따라서 단순히 장애물이 경로를 차단하는 경우뿐만 아니라 노면이나 특정 구역이 배송 로봇의 주행에 적합하지 않거나 통행이 금지된 경우에도 해당 경로를 제외할 수 있다.

전역 경로 계획(Global Route Planning)은 배차 지점에서 배송 목적지까지 이동할 수 있는 실행 가능한 경로를 선택한다. 서로 다른 경로에는 급경사, 좁은 보도, 통과하기 어려운 횡단 구역, 공사 구간, 높은 보행자 밀도, 접근하기 어려운 연석 등이 존재할 수 있기 때문에 거리만으로 경로를 결정하는 것은 충분하지 않다. 경로 계획기는 지도 속성과 과거 주행 정보(Historical Traversal Information)를 이용하여 경로 비용(Route Cost)을 추정할 수 있다. 임무 계획에는 로봇이 대기하거나 접근 가능성을 확인하거나 원격 지원을 요청해야 하는 중간 체크포인트(Checkpoint)도 포함될 수 있다.

지역 궤적 계획(Local Trajectory Planning)은 보행자와 움직이는 장애물과의 즉각적인 상호작용을 처리한다. 로봇은 단기적인 주행 가능 공간(Free Space)을 지속적으로 예측하고 전역 경로와 일치하는 충돌 없는 궤적(Collision-Free Trajectory)을 선택한다. 사람은 갑자기 정지하거나 방향을 바꾸거나 로봇에 접근할 수 있으므로 경로 계획에서는 충분한 정지 거리를 확보하고 공격적인 기동을 피해야 한다. 사회적으로 적절한 내비게이션(Socially Appropriate Navigation)은 기하학적으로 통과 가능한 경로가 존재하더라도 로봇이 보행자에게 불필요하게 가까이 접근하는 것을 방지한다.

보행자 상호작용(Pedestrian Interaction)은 창고 환경에서의 단순한 장애물 회피와 근본적으로 다르다. 사람은 주변 상황에 영향을 받으면서 의도적으로 이동하는 에이전트(Agent)이며 미래의 이동 궤적은 불확실하다. 인지 소프트웨어는 보행자를 추적하고 속도 또는 단기 움직임을 추정할 수 있으며, 경로 계획 소프트웨어는 가능한 상호작용을 평가한다. 보수적인 속도, 명확한 양보 동작(Yielding Behavior), 예측 가능한 궤적을 적용하면 사람이 로봇의 의도를 쉽게 이해하고 불편한 상호작용을 줄일 수 있다.

도로 및 차량 진출입로 횡단(Road and Driveway Crossing)은 차량과의 고위험 상호작용을 발생시킨다. AMR은 횡단 구역을 인식하고, 접근하는 차량을 평가하며, 안전하게 통과할 충분한 시간이 있는지를 판단하고, 안전한 회피 또는 정지 전략을 유지해야 한다. 배치 환경에 따라 횡단 동작은 인프라 정보(Infrastructure Information) 또는 원격 감독(Remote Supervision)을 활용할 수도 있다. 고속으로 이동하는 차량이 장면에 진입할 수 있기 때문에 로봇은 일시적으로 시야가 확보되었다는 이유만으로 통행 우선권이 보장된 것으로 판단해서는 안 된다.

연석, 경사로, 노면 불연속(Surface Discontinuity), 작은 장애물은 계획된 경로를 실제로 주행할 수 있는지에 영향을 준다. 지형 인지(Terrain Perception)는 기동을 시작하기 전에 단차 높이, 경사도, 노면 거칠기, 이용 가능한 통과 폭을 추정할 수 있다. 모션 계획기(Motion Planner)는 휠 직경, 지상고(Ground Clearance), 최대 경사도, 제동 성능, 안정성 한계 등 플랫폼의 기계적 성능을 이해해야 한다. 외관상 개방된 경로라 하더라도 기계적으로는 주행이 불가능할 수 있다.

기상 및 조명 조건(Weather and Illumination)은 도시 환경의 자율주행 성능에 상당한 영향을 줄 수 있다. 비는 노면 마찰력을 변화시키고 카메라 시야를 방해할 수 있으며, 직사광선은 눈부심(Glare)을 발생시키고, 어두운 환경에서는 수동 광학 정보(Passive Visual Information)가 감소하며, 눈이나 고인 물은 노면 경계를 가릴 수 있다. 센서 융합은 특정 센싱 방식 하나에 대한 의존성을 줄이고, 환경 모니터링(Environmental Monitoring)을 통해 속도 또는 경로 정책을 변경할 수 있다. 안전한 주행을 보장할 수 없는 심각한 환경에서는 임무를 중단해야 할 수도 있다.

배송 적재함(Delivery Compartment)은 자율주행과 물류 서비스 사이의 물리적 인터페이스(Physical Interface)를 구성한다. 로봇이 이동하는 동안 화물은 안전하게 보관되어야 하며 허가된 수령인 또는 운영자만 접근할 수 있어야 한다. 전자식 잠금장치(Electronic Lock), 적재함 센서(Compartment Sensor), 도어 상태 모니터링(Door-State Monitoring), 사용자 인증(User Authentication)을 임무 상태와 연결할 수 있다. 로봇이 목적지에 도착했다는 이유만으로 배송을 완료 처리해서는 안 되며, 정상적인 화물 접근 또는 인계도 함께 확인해야 한다.

임무 관리(Mission Management)는 배차부터 복귀 또는 재할당까지 전체 배송 생명주기(Delivery Lifecycle)를 조정한다. 하나의 임무에는 화물 적재, 목적지 확인, 경로 획득, 자율주행, 대기, 고객 알림(Customer Notification), 인증, 적재함 개방, 배송 확인, 물류 거점 또는 충전 지점으로의 복귀가 포함될 수 있다. 명확한 임무 상태(Explicit Mission State)를 사용하면 지연, 경로 차단, 통신 중단, 배송 실패가 발생한 이후에도 시스템이 올바르게 복구할 수 있다.

여러 배송 AMR이 동일한 지역이나 서비스 구역을 공유할 경우 차량군 관리(Fleet Management)가 중요해진다. 차량군 서비스(Fleet Service)는 로봇 위치, 배터리 수준, 화물 용량, 목적지, 예상 이동 시간, 현재 가용성을 기반으로 임무를 할당한다. 또한 동일한 보행 구역에 지나치게 많은 로봇이 집중되는 것을 방지할 수 있다. 차량 적재 용량과 서비스 시간 요구조건을 만족하는 경우 배치 계획(Batch Planning)을 통해 서로 호환되는 여러 배송을 결합하여 단일 목적지 임무보다 효율적인 다중 경유 임무(Multi-Stop Mission)를 구성할 수 있다.

실외 주행의 전력 소비는 거리, 경사도, 적재량, 온도, 노면 상태, 반복적인 정지 및 출발 동작에 따라 달라지므로 에너지 인지형 계획(Energy-Aware Planning)이 필요하다. 로봇은 배송 임무를 완료하고 충전 또는 복구 지점까지 도달하는 데 충분한 에너지가 남아 있는지를 추정한다. 차량군 소프트웨어는 임무 사이에 충전 시간을 예약하거나 서비스 신뢰성에 영향을 미치기 전에 에너지가 부족한 로봇의 경로를 변경할 수 있다. 따라서 배터리 상태는 단순한 유지보수 변수가 아니라 물류 계획의 일부가 된다.

통신 링크(Communication Link)는 AMR을 차량군 서비스, 모니터링 시스템, 고객 애플리케이션(Customer Application), 원격 운영자(Remote Operator)와 연결한다. 로봇은 위치, 임무 상태, 배터리 상태, 고장, 주요 안전 이벤트를 보고하면서 경로 업데이트 또는 운영 지시를 수신한다. 건물 사이 또는 건물 내부에서는 연결 품질이 일시적으로 저하될 수 있으므로 즉각적인 충돌 회피와 안전 정지가 지속적인 클라우드 통신(Cloud Communication)에 의존해서는 안 된다. 필수적인 자율주행 기능은 로봇 내부에서 계속 사용할 수 있어야 한다.

원격 지원(Remote Assistance)은 자율주행 소프트웨어가 높은 신뢰도로 해결할 수 없는 상황에 대한 복구 메커니즘(Recovery Mechanism)을 제공한다. 보도가 예상하지 못하게 차단되었을 때 운영자가 센서 정보를 확인하거나, 비정상적인 통로가 안전한지를 판단하거나, 상위 수준의 내비게이션 명령을 제공할 수 있다. 원격 지원이 기본적인 자율주행 기능을 대체해서는 안 된다. 그 목적은 드물게 발생하는 불확실성을 해결하면서 원격 명령이 로봇의 로컬 안전 시스템(Local Safety System)에서 어느 범위까지 허용되는지 명확한 제한을 유지하는 것이다.

안전 아키텍처(Safety Architecture)는 로봇과 화물뿐만 아니라 보행자도 보호해야 한다. 독립적인 비상 정지(Emergency Stop), 속도 감시(Speed Supervision), 장애물 보호 영역(Obstacle Protection Zone), 액추에이터 감시(Actuator Monitoring), 제동 진단(Braking Diagnostics), 고장 감지(Fault Detection)는 자율주행 소프트웨어를 보완할 수 있다. 운행 속도는 보행자 밀도, 가시성, 통로 폭, 위치 추정 신뢰도, 환경 조건에 따라 달라질 수 있다. 요구되는 안전 조건이 충족되지 않으면 배송을 계속하는 대신 로봇을 제어된 안전 상태(Controlled Safe State)로 전환해야 한다.

도시 환경에서의 운용은 예외 이벤트(Exceptional Event)에 대한 체계적인 처리도 필요하다. 공사로 인해 경로가 차단되거나, 수령인이 부재하거나, 적재함 잠금이 해제되지 않거나, 위치 추정 성능이 저하되거나, 로봇의 물리적 성능을 초과하는 지형을 만날 수 있다. 예외 처리 로직(Exception Logic)은 상황을 분류한 후 경로 재계획(Rerouting), 대기, 재시도, 지원 요청, 거점 복귀(Return to Base), 안전 정지 중 적절한 대응을 선택해야 한다. 복구 과정 전체에서 임무와 화물 상태의 추적성(Traceability)이 유지되어야 한다.

사이버보안(Cybersecurity)과 개인정보 보호(Privacy)는 배송 로봇이 통신 서비스를 사용하고 사람과 건물 주변에서 지속적으로 센서 데이터를 수집하기 때문에 공공 환경에서 더욱 중요하게 나타난다. 인증(Authentication)은 차량군 명령과 화물 접근 기능을 보호하고, 권한 관리(Authorization)는 원격 동작을 제한한다. 저장된 운영 데이터는 사용 목적과 보존 정책(Retention Policy)에 따라 관리되어야 한다. 보안 아키텍처는 고객 대상 서비스(Customer-Facing Service)의 침해가 차량 움직임에 대한 직접적인 비인가 제어(Unauthorized Control)로 이어지지 않도록 해야 한다.

운영 모니터링(Operational Monitoring)은 로봇 정보와 배송 서비스 정보를 통합한다. 차량군 운영자는 로봇 위치, 활성 임무, 지연된 배송, 배터리 상태, 통신 품질, 개입 요청, 고장 상태를 확인할 수 있다. 과거 텔레메트리(Historical Telemetry)를 분석하면 반복적으로 차단되는 경로, 통과하기 어려운 횡단 구역, 위치 추정 취약 구간, 배송 지연, 에너지 소비 패턴을 발견할 수 있다. 이러한 관측 결과를 이용하여 지도, 경로 계획 정책, 차량군 할당, 유지보수 일정, 서비스 구역 설계를 개선할 수 있다.

대규모 도시 환경에 배포하기 전에 시뮬레이션(Simulation)과 구조화된 현장 시험(Structured Field Testing)을 수행하는 것이 필수적이다. 가상 환경에서는 보행자, 차량, 교차로, 연석, 기상 조건, 통신 손실, 차단된 보도를 재현할 수 있으며, 통제된 실제 시험을 통해 센싱과 모션 동작을 검증할 수 있다. 시나리오 기반 평가(Scenario-Based Evaluation)에는 일반적인 운용 상황뿐만 아니라 드물지만 안전에 중요한 상황도 포함되어야 한다. 반복적인 시험을 통해 실제 차량군에 소프트웨어 업데이트를 배포하기 전에 기존의 알려진 시나리오와 비교하여 성능을 검증할 수 있다.

라스트 마일 배송 AMR(Last-Mile Delivery AMR)은 궁극적으로 자율 로봇 기술과 도시 물류 서비스(Urban Logistics Service)를 연결한다. 그 효과는 단순히 목적지에 도착하는 능력만으로 결정되지 않으며 인지, 위치 추정, 내비게이션, 인간과의 상호작용, 화물 보안(Cargo Security), 차량군 관리, 에너지, 통신, 예외 복구(Exception Recovery)를 통합적으로 조정하는 능력에 의해 결정된다. 따라서 성공적인 시스템은 예측하기 어려운 실제 도시 환경에서 적응 가능한 자율 동작(Adaptable Autonomous Behavior), 보수적인 안전 경계(Conservative Safety Boundary), 추적 가능한 물류 실행(Traceable Logistics Execution)을 함께 제공해야 한다.

## 09.08. Cargo UAV Port to Ship Delivery SW [w/Code]

![](images/image8.png){width="7.268055555555556in" height="7.268055555555556in"}

화물 무인항공기 항만-선박 배송 소프트웨어(Cargo UAV Port-to-Ship Delivery Software)는 육상 물류 지점과 부두, 정박지 또는 기타 허가된 해상 운용 구역에 위치한 선박 사이의 자율 항공 운송을 조정한다. 목적지가 이동할 수 있고 항만 공역(Port Airspace)이 제한될 수 있으며 바람 조건이 빠르게 변화할 수 있기 때문에 단순한 지점 간 비행만으로는 충분하지 않다. 따라서 임무 소프트웨어(Mission Software)는 물류, 내비게이션, 비행 제어, 선박 추적, 안전, 통신, 화물 취급 기능을 통합해야 한다.

배송 임무(Delivery Mission)는 화물 정보, 픽업 위치, 대상 선박, 배송 지점, 시간 제약 조건, 운영 우선순위를 포함하는 구조화된 운송 요청(Structured Transport Request)으로 시작된다. 소프트웨어는 요청된 탑재물이 UAV의 적재 능력과 호환되는지, 그리고 출항 비행, 배송, 비상 대응, 복귀에 필요한 충분한 에너지가 확보되어 있는지를 검증한다. 항공기, 탑재물, 기상, 경로 또는 목적지 조건이 정의된 운용 한계(Operating Limit)를 위반하는 경우 임무를 배정해서는 안 된다.

임무 관리 계층(Mission-Management Layer)은 물류 요청을 실행 가능한 비행 시퀀스(Flight Sequence)로 변환한다. 일반적인 단계에는 비행 전 검증(Preflight Validation), 화물 적재, 이륙, 출발 회랑 내비게이션(Departure Corridor Navigation), 해상 비행, 선박 접근, 배송 위치 정렬, 화물 이송, 선박 이탈, 복귀 비행, 착륙이 포함된다. 명확한 임무 상태(Explicit Mission State)를 사용하면 소프트웨어가 각 운용 단계에서 가능한 복구 동작을 판단할 수 있으므로 비정상적인 상황을 보다 효과적으로 관리할 수 있다.

경로 계획(Route Planning)은 항공 운용 제약과 항만 운영 조건을 모두 고려해야 한다. 기하학적으로 가장 짧은 경로가 제한 구역, 크레인 운용 공간, 위험 화물 구역, 인구 밀집 공간 또는 선박 기동 구역을 통과할 수 있다. 경로 계획기(Route Planner)는 허용 비행 회랑, 고도 제한, 비행 금지 구역(Exclusion Zone), 비상 착륙 구역, 임시 제한 구역을 표현할 수 있다. 동적 업데이트(Dynamic Update)를 적용하면 크레인 작업, 선박 이동 또는 지역적 제한으로 사용 가능한 비행 공간이 변경되는 경우 임무가 이에 대응할 수 있다.

항만 및 연안 환경에서의 위치 추정(Localization)은 일반적으로 GNSS와 관성 센싱(Inertial Sensing)을 결합하며, 구조물과 선박 주변에서는 추가적인 비전 또는 거리 측정 정보를 이용하여 상대 내비게이션(Relative Navigation)을 향상시킬 수 있다. 다중 경로(Multipath), 간섭, 신호 차단 또는 위성 배치 상태 악화로 내비게이션 품질이 저하될 수 있으므로 위치 불확실성(Position Uncertainty)을 지속적으로 감시해야 한다. 위치 추정 신뢰도가 운용 임계값 이하로 떨어지면 UAV는 정의된 성능 저하 내비게이션(Degraded Navigation) 또는 복구 동작으로 전환해야 한다.

대상 선박(Target Vessel)은 일반적인 고정 지점 배송에서는 존재하지 않는 이동 기준점 문제(Moving-Reference Problem)를 발생시킨다. 부두에 접안하거나 정박한 선박도 조수, 바람, 파도, 계류 움직임 또는 운영 활동으로 인해 위치와 방향이 변화할 수 있다. 따라서 소프트웨어는 선박 자세(Vessel Pose)와 의도된 배송 위치를 지속적으로 갱신하여 추정해야 한다. 최종 접근 단계에서는 지리 좌표만으로 충분한 정밀도를 확보하지 못할 수 있기 때문에 상대 내비게이션의 중요성이 더욱 커진다.

선박 검출(Vessel Detection)과 상대 자세 추정(Relative Pose Estimation)에는 카메라, 라이다(LiDAR), 레이더(Radar), 협력형 마커(Cooperative Marker) 또는 선박 시스템에서 제공되는 정보를 사용할 수 있다. 인지 계층(Perception Layer)은 선박, 갑판 영역, 착륙 또는 이송 구역, 주변 장애물을 식별한다. 센서 관측 결과는 알려진 선박 형상 및 내비게이션 데이터와 융합하여 안정적인 상대 기준(Relative Reference)을 유지할 수 있다. 불확실한 목표 식별 결과가 자동으로 최종 하강이나 화물 해제를 유발하지 않도록 신뢰도를 명시적으로 평가해야 한다.

바람(Wind)은 항만-선박 비행에서 중요한 계획 및 제어 변수이다. 연안의 바람은 고도에 따라 달라질 수 있으며 크레인, 건물, 컨테이너, 선박 상부 구조물 주변에서 난류(Turbulence)가 발생할 수 있다. 비행 시스템은 현재 조건에서 위치와 속도를 요구되는 한계 범위 내에 유지할 수 있는지를 평가해야 한다. 또한 잔잔한 기상에서는 가능한 임무라도 강한 맞바람을 받으며 복귀할 경우 훨씬 많은 에너지 예비량이 필요할 수 있으므로 에너지 예측(Energy Prediction)에 바람의 영향도 포함해야 한다.

비행 제어 소프트웨어(Flight-Control Software)는 계획된 궤적을 안정적인 항공기 움직임으로 변환하면서 외란(Disturbance)을 보상한다. 위치, 속도, 자세, 추력 제어(Position, Velocity, Attitude, and Thrust Control)는 서로 다른 시간 척도에서 동작하며 상위 수준의 물류 명령과 독립적으로 유지되어야 한다. 임무 소프트웨어는 웨이포인트(Waypoint) 또는 상대 접근 궤적을 요청할 수 있지만 저수준 제어기(Low-Level Controller)는 항공기의 안정성을 유지한다. 이러한 분리는 물류 또는 네트워크 서비스의 지연이 기본적인 비행 안정화에 직접 영향을 미치는 것을 방지한다.

최종 접근(Final Approach) 단계에서는 점진적으로 더욱 엄격한 안전 및 정확도 요구조건을 적용해야 한다. UAV는 먼저 선박 중심의 접근 지점으로 이동한 후 최종 구간에서 상대 센싱(Relative Sensing)으로 전환할 수 있다. 항공기가 이송 구역에 가까워질수록 속도와 허용 위치 오차를 줄일 수 있다. 목표 구역이 장애물로 차단되거나 선박 움직임이 한계를 초과하거나 상대 위치 추정의 신뢰성이 낮아지면 불확실한 접근을 계속하는 대신 대기, 후퇴 또는 임무 중단을 수행해야 한다.

화물 이송(Cargo Transfer)은 착륙, 제어된 하강 방식의 화물 전달, 윈치 배송(Winch Delivery) 또는 기타 플랫폼별 메커니즘을 통해 수행할 수 있다. 각 방식은 서로 다른 비행 및 안전 제약 조건을 발생시키므로 소프트웨어는 어떤 이송 방식이 사용되고 있는지를 이해해야 한다. 화물 존재 여부, 부착 상태, 해제 상태, 적재함 또는 윈치 상태를 감시해야 한다. 시스템이 올바른 목적지를 확인하고 요구되는 이송 조건을 충족한 이후에만 화물 해제 명령을 실행해야 한다.

선박 측 인계 프로토콜(Shipboard Handover Protocol)을 이용하여 UAV와 선박 승무원 또는 자동화된 수령 장비 사이의 작업을 조정할 수 있다. 선박은 지정된 구역이 준비되었음을 보고하고 UAV는 접근 상태와 화물 상태를 전달할 수 있다. 이송 승인(Transfer Authorization)은 단순한 도착 상태와 구분되어야 한다. 화물 해제 전의 명확한 승인과 이송 후의 확인 절차를 통해 실제 화물이 정상적으로 인수되지 않았는데도 디지털 물류 시스템이 배송 완료로 처리하는 상황을 방지할 수 있다.

통신 아키텍처(Communication Architecture)는 일반적인 임무 데이터와 안전 관련 운용 상황 인식(Safety-Related Operational Awareness)을 모두 지원해야 한다. UAV는 지상 제어 시스템 또는 차량군 시스템과 위치, 임무 상태, 배터리 상태, 탑재물 상태, 내비게이션 품질, 고장 정보를 교환할 수 있다. 해상 또는 항만 구조물 주변에서는 통신 품질이 저하될 수 있으므로 기본적인 비행 안정화, 충돌 회피, 비상 상황 처리, 안전 복귀 기능이 지속적인 원격 통신에 전적으로 의존해서는 안 된다.

통신 손실(Loss of Communication)에 대해서는 사전에 정의된 동작이 필요하다. 임무 단계, 잔여 에너지, 현재 위치, 운영 정책에 따라 UAV는 위치 유지(Hold Position), 안전 지점으로 복귀, 이전에 승인된 구간의 계속 비행 또는 비상 절차를 수행할 수 있다. 선박 또는 혼잡한 항만 주변에서는 하나의 일반적인 자동 복귀(Return-to-Home) 동작이 적절하지 않을 수 있다. 따라서 비상 대응 로직(Contingency Logic)은 현재 비행 상황과 해상 및 육상 환경의 안전성을 함께 고려해야 한다.

장애물 회피(Obstacle Avoidance)는 정적 및 동적 위험 요소를 모두 고려해야 한다. 크레인, 마스트(Mast), 케이블, 안테나, 컨테이너 적재물, 건물, 선박 구조물은 복잡한 3차원 장애물을 형성하며 다른 UAV, 서비스 장비 또는 이동하는 선박은 환경을 동적으로 변화시킬 수 있다. 인지 및 매핑 소프트웨어(Perception and Mapping Software)는 알려진 구조물과 충분한 안전거리를 유지하고 예상하지 못한 위험 요소를 감지해야 한다. 회피 기동(Avoidance Maneuver)은 허가된 비행 구역과 항공기 성능 한계 내부에서 수행되어야 한다.

에너지 관리(Energy Management)는 UAV가 충분한 안전 예비량(Safety Reserve)을 확보한 상태로 임무를 완료할 수 있는지를 결정한다. 소프트웨어는 탑재물 질량, 경로 거리, 고도 프로파일(Altitude Profile), 바람, 호버링 시간(Hover Time), 예상 이송 시간, 배터리 상태를 기반으로 에너지 소비량을 추정한다. 비상 착륙 선택지가 제한되는 해상 또는 수상 비행에서는 예비 에너지 임계값을 더욱 보수적으로 설정할 수 있다. 실제 에너지 소비량이 예측값과 크게 달라지는 경우 임무 지속 가능성을 다시 평가해야 한다.

여러 대의 화물 UAV가 동시에 항만 물류를 지원하는 경우 차량군 관리(Fleet Management)가 필요하다. 차량군 서비스(Fleet Service)는 탑재 능력, 항공기 위치, 배터리 상태, 유지보수 상태, 대상 선박, 공역 가용성을 기반으로 임무를 할당할 수 있다. 공용 비행 회랑이나 선박 접근 구역의 혼잡을 방지하도록 출발 시간을 조정할 수도 있다. 충전, 점검, 화물 적재, 임무 전환 작업(Turnaround Activity) 역시 공유 운영 자원으로 스케줄링할 수 있다.

터미널 운영 시스템(Terminal Operating System, TOS) 또는 물류 플랫폼(Logistics Platform)과의 통합은 항공 배송을 더 넓은 화물 작업 흐름과 연결한다. 상위 시스템은 배송 의도(Delivery Intent)와 화물 식별 정보를 제공하고 UAV 서비스는 임무 수락, 출발, 접근, 이송, 완료 또는 실패 상태를 보고한다. 이 인터페이스에서는 원시 비행 제어 명령이 아니라 물류 이벤트(Logistics Event)를 교환해야 한다. UAV는 안전한 항공기 운용을 담당하고 터미널 시스템은 비즈니스 수준의 운송 프로세스에 대한 책임을 유지한다.

운영 모니터링(Operational Monitoring)은 비행 정보와 물류 정보를 통합하여 추적 가능한 임무 기록(Traceable Mission Record)을 생성해야 한다. 관련 데이터에는 비행 경로 기록, 기체 상태, 배터리 사용량, 바람 추정값, 내비게이션 품질, 통신 상태, 선박 상대 위치, 화물 상태, 운영자 개입, 주요 고장 정보가 포함될 수 있다. 배송이 지연되거나 중단되면 이러한 기록을 이용하여 원인이 기상, 항공기 상태, 선박 준비 상태, 공역 제한 또는 소프트웨어 동작 중 어디에서 발생했는지를 판단할 수 있다.

예외 관리(Exception Management)는 과도한 바람, 배터리 부족, 내비게이션 성능 저하, 차단된 배송 구역, 선박 이동, 화물 장치 고장, 통신 손실, 예상하지 못한 장애물 등의 상황을 처리해야 한다. 각 예외는 대기, 경로 재계획(Replanning), 복귀, 대체 복구 지점(Alternate Recovery Location) 선택 또는 안전한 임무 종료와 같은 통제된 대응으로 연결되어야 한다. 복구 과정 전체에서 화물 상태를 지속적으로 파악하여 물류 기록이 실제 물리적 상태를 계속 반영하도록 해야 한다.

안전 기능(Safety Function)은 임무 최적화보다 우선적인 권한을 가져야 한다. 지오펜싱(Geofencing), 고도 제한, 비행 영역 감시(Flight-Envelope Monitoring), 추진 시스템 진단(Propulsion Diagnostics), 배터리 보호, 내비게이션 품질 확인, 비상 절차는 상위 수준의 소프트웨어가 안전하지 않은 임무를 계속 수행하는 것을 방지할 수 있다. 따라서 자동 배송은 제약된 자율성(Constrained Autonomy)으로 설계되어야 하며, 검증된 운용 경계 내부에서만 임무를 최적화하고 해당 경계를 위반하면 안전 대응으로 전환해야 한다.

많은 해상 환경의 경계 사례(Edge Case)는 실제 항공기를 이용하여 반복적으로 재현하기 어렵거나 비용이 많이 들기 때문에 시뮬레이션(Simulation)과 시나리오 기반 시험(Scenario-Based Testing)이 특히 중요하다. 시뮬레이션에서는 선박 움직임, 바람, GNSS 성능 저하, 통신 손실, 이동 장애물, 배송 구역 차단, 에너지 불확실성을 모델링할 수 있다. 소프트웨어 인 더 루프(Software-in-the-Loop, SIL) 및 하드웨어 인 더 루프(Hardware-in-the-Loop, HIL) 시험을 통해 임무 상태 전환과 인터페이스를 검증한 후 통제된 비행 시험으로 대표적인 항만 환경에서 전체 시스템을 검증할 수 있다.

화물 무인항공기 항만-선박 배송 소프트웨어(Cargo UAV Port-to-Ship Delivery Software)는 궁극적으로 자동화된 항만 물류를 공중 영역으로 확장한다. 신뢰성 높은 운용을 위해서는 물류 오케스트레이션(Logistics Orchestration), 3차원 내비게이션(Three-Dimensional Navigation), 선박 상대 인지(Vessel-Relative Perception), 강건한 비행 제어(Robust Flight Control), 에너지 인지형 계획(Energy-Aware Planning), 안전한 통신(Secure Communication), 화물 검증, 명시적인 비상 상황 관리(Explicit Contingency Management)가 하나의 통합된 시스템으로 동작해야 한다. 목표는 단순한 자율 비행이 아니라 터미널 물류 네트워크에서 올바른 선박까지 추적 가능하고 안전하게 제약된 물리적 배송을 실현하는 것이다.

## 09.09. Port Robot Safety and Maritime Regulation

![](images/image9.png){width="7.268055555555556in" height="7.268055555555556in"}

항만 로봇 안전(Port Robot Safety)은 동일한 운영 환경에서 자율 기계, 중량 화물, 크레인, 차량, 작업자, 선박, 해양 인프라(Maritime Infrastructure)가 상호작용하는 상황을 다루어야 한다. 격리된 공장 자동화와 달리 항만 로봇은 혼합 교통(Mixed Traffic)과 지속적으로 변화하는 위험 요소가 존재하는 넓은 영역에서 운용된다. 따라서 안전 공학(Safety Engineering)은 기계 수준의 보호, 자율 시스템 감독, 운영 절차, 인프라 제어, 관련 해양 및 산업안전 요구사항을 통합해야 한다.

안전은 로봇의 전체 생명주기(Robot Lifecycle)에 걸친 체계적인 위험 식별(Hazard Identification)에서 시작된다. 주요 위험에는 작업자 또는 차량과의 충돌, 컨테이너 충격, 조향 또는 제동 기능 상실, 위치 추정 실패, 제어되지 않은 움직임, 통신 손실, 배터리 고장, 크레인 상호작용 오류, 환경적 영향 등이 포함된다. 위험 평가(Risk Assessment)는 이러한 사건의 심각도와 발생 가능성을 평가하고 자율 운용을 허용하기 전에 필요한 기술적 또는 절차적 대책을 결정한다.

계층형 안전 아키텍처(Layered Safety Architecture)는 하나의 인지 모델이나 소프트웨어 기능에 대한 의존을 방지한다. 임무 계획과 자율 내비게이션은 정상적인 충돌 회피 기능을 제공할 수 있으며, 독립적인 안전 계층(Safety Layer)은 보호 영역, 속도, 제동 능력, 액추에이터 상태, 비상 정지 신호를 감시한다. 자율주행 스택(Autonomy Stack)이 안전하지 않은 명령을 생성하거나 사용할 수 없는 상태가 되더라도 안전 계층은 움직임을 제한하거나 로봇을 정의된 안전 상태(Safe State)로 전환할 수 있는 충분한 권한을 유지해야 한다.

중량 항만 차량은 즉시 정지할 수 없기 때문에 비상 정지(Emergency Stopping)는 신중하게 설계해야 한다. 안전 정지 거리(Safe Stopping Distance)는 속도, 적재량, 도로 경사도, 타이어 상태, 노면 마찰력, 제동 능력, 시스템 반응 시간에 따라 달라진다. 따라서 보호 센싱(Protective Sensing)은 모든 상황에서 고정된 거리를 사용하는 대신 동적 정지 영역(Dynamic Stopping Envelope)을 고려해야 한다. 적재 차량과 비적재 차량에는 서로 다른 속도 제한과 보호 영역 설정이 필요할 수 있다.

기능 안전 원칙(Functional Safety Principle)은 구성 요소가 고장 났을 때 안전 관련 제어 기능이 어떻게 동작해야 하는지를 결정하는 데 사용된다. 안전 기능에는 비상 정지, 안전 토크 제거(Safe Torque Removal), 속도 제한, 조향 감시(Steering Supervision), 보호 영역 감시, 브레이크 감시, 의도하지 않은 움직임 방지 등이 포함될 수 있다. 물류 소프트웨어의 고장이 필수적인 물리적 보호 기능을 제거하지 못하도록 필요한 경우 안전 관련 하드웨어와 소프트웨어를 일반적인 임무 최적화 기능과 분리해야 한다.

혼합형 항만 환경에서는 사람 감지(Human Detection)가 특히 중요하다. 카메라, 라이다(LiDAR), 레이더(Radar) 또는 안전 등급 센싱 장치(Safety-Rated Sensing Device)를 이용하여 자율주행 차량과 이송 장비 주변 영역을 감시할 수 있다. 감지 성능은 컨테이너, 차량, 기계 또는 열악한 조명으로 인해 작업자의 신체 일부가 가려지는 상황까지 고려해야 한다. 필요한 안전 이격 거리(Safety Separation)를 유지할 수 없는 경우 모든 사람이 예측 가능하게 행동할 것이라고 가정하는 대신 시스템이 속도를 줄이거나 정지해야 한다.

지오펜싱(Geofencing)은 로봇이 운용될 수 있는 위치와 각 영역에서 허용되는 동작을 소프트웨어적으로 표현한다. 서로 다른 구역에는 최대 속도, 허용 차량 종류, 진행 방향 제한, 정지 요구사항, 자율 운용 허용 여부 등을 정의할 수 있다. 유지보수 작업, 사고, 크레인 운용 또는 위험 화물 작업 주변에는 임시 출입 제한 구역(Temporary Exclusion Area)을 설정할 수 있다. 지오펜스 적용 상태는 실제 물리적 운용 환경과 지속적으로 동기화되어야 한다.

로봇과 안벽 또는 야드 크레인 사이의 상호작용에는 명확한 안전 조정(Safety Coordination)이 필요하다. 차량의 내비게이션 경로가 비어 있다는 이유만으로 이송 구역에 진입해서는 안 된다. 이동을 진행하기 전에 크레인 상태, 스프레더 위치(Spreader Position), 이송 승인(Transfer Authorization), 컨테이너 상태, 차량 준비 상태를 고려해야 한다. 인터록(Interlock)과 핸드셰이크 로직(Handshake Logic)은 크레인과 로봇이 각각 개별적으로는 정상적인 동작이지만 동시에 실행될 경우 위험해질 수 있는 작업을 독립적으로 수행하는 것을 방지한다.

교통 안전(Traffic Safety)은 여러 차량 사이의 상호작용을 제어함으로써 단순한 장애물 회피를 넘어선다. 교차로, 좁은 통로, 이송 구역, 공유 도로 구간은 자율주행 장비와 사람이 운전하는 장비 사이의 충돌 지점(Conflict Point)이 될 수 있다. 교통 관리 시스템은 예약(Reservation) 또는 우선순위를 할당할 수 있으며, 차량 내 시스템은 즉각적인 충돌 방지 책임을 유지한다. 중앙 시스템의 통행 승인을 예상하지 못한 로컬 장애물과 충돌해도 된다는 허가로 해석해서는 안 된다.

해양 터미널(Maritime Terminal)은 실내 자동화에서는 일반적이지 않은 환경 조건에도 로봇을 노출시킨다. 비, 안개, 염분 오염(Salt Contamination), 바람, 고인 물, 온도 변화, 진동, 낮은 가시성은 센서, 브레이크, 전자장치, 통신 장비의 성능을 저하시킬 수 있다. 안전 검증(Safety Validation)을 통해 환경 운용 한계(Environmental Operating Limit)를 설정하고 해당 한계를 초과했을 때의 대응 방법을 정의해야 한다. 요구되는 인지 또는 제동 성능을 유지할 수 없는 로봇은 정상적인 자율 운용을 계속해서는 안 된다.

연결된 로봇은 통신 네트워크를 통해 임무, 경로 업데이트, 소프트웨어 설정, 원격 명령을 수신하기 때문에 사이버보안(Cybersecurity)은 물리적 안전에 직접적으로 영향을 준다. 인증(Authentication), 권한 부여(Authorization), 메시지 무결성(Message Integrity), 안전한 소프트웨어 업데이트(Secure Software Update), 네트워크 분할(Network Segmentation)은 비인가 접근이 실제 물리적 움직임에 영향을 줄 가능성을 줄인다. 상위 물류 또는 기업 시스템이 침해되더라도 안전 필수 기능(Safety-Critical Function)은 보호된 상태를 유지해야 한다.

운영 안전(Operational Safety)은 누가 로봇을 시작, 정지, 복구, 유지보수하거나 원격으로 지원할 수 있는지를 통제하는 것에도 의존한다. 역할 기반 권한(Role-Based Permission)을 통해 일반 배차 작업과 유지보수 및 안전 기능을 분리할 수 있다. 복구 절차(Recovery Procedure)는 작업자가 정지된 로봇에 접근하는 방법, 저장 에너지 상태를 확인하는 방법, 제한 구역에 진입하는 방법, 장비를 다시 운용 상태로 전환하는 방법을 정의해야 한다. 원격 개입(Remote Intervention)은 기록되어야 하며 운영자가 의도하지 않게 로컬 안전 보호 기능을 우회하지 못하도록 제한되어야 한다.

해양 규제(Maritime Regulation)는 항만 운영이 선박 안전, 항만 당국 규칙, 위험물 취급, 세관 통제 구역, 지역 운송 요구사항과 연계되기 때문에 추가적인 거버넌스 계층(Governance Layer)을 형성한다. 정확한 규제 의무는 관할 지역, 터미널 유형, 장비 종류, 운용 개념에 따라 달라진다. 따라서 로봇 배치는 하나의 로봇 표준만으로 모든 규제 준수 요구사항이 정의된다고 가정하는 대신 규제 적용성 분석(Regulatory Applicability Analysis)에서 시작해야 한다.

국제 해양 프레임워크(International Maritime Framework)는 AMR의 내부 설계를 직접 규정하지 않더라도 운영 환경에 영향을 줄 수 있다. 안전한 항만 운영, 선박 인터페이스, 위험 화물, 보안, 해양 환경 보호와 관련된 요구사항은 로봇 장비가 어디에서 어떻게 사용될 수 있는지에 영향을 미칠 수 있다. 터미널 운영자는 이러한 의무를 지역 규정, 항만 당국 절차, 장비 표준, 현장별 운영 규칙(Site-Specific Operating Rule)에 연결해야 한다.

위험물 작업(Dangerous-Goods Operation)에서는 컨테이너 식별 정보, 위치, 취급 조건, 접근 제한에 대한 특히 엄격한 관리가 필요하다. 규제 대상 화물을 운송하도록 할당된 로봇에는 경로 제약(Route Constraint), 제한된 주차 구역, 추가적인 안전 이격 거리 또는 특수 비상 절차가 필요할 수 있다. 터미널 운영 시스템(Terminal Operating System, TOS)과의 통합을 통해 화물 분류와 취급 제한 정보를 운송이 시작된 이후가 아니라 임무 할당 전에 사용할 수 있도록 해야 한다.

안전 사례(Safety Case)는 자동화 운용이 허용 가능한 수준으로 안전한 이유를 체계적으로 입증하는 방법을 제공한다. 안전 사례는 식별된 위험, 위험 통제(Risk Control), 설계 요구사항, 검증 증거(Verification Evidence), 운영 절차, 교육, 잔여 위험(Residual Risk)을 추적 가능한 논리 구조로 연결할 수 있다. 복잡한 항만 자동화에서는 안전성이 하나의 인증된 구성 요소가 아니라 로봇, 인프라, 소프트웨어, 사람, 운영 절차 사이의 상호작용에 의해 결정되므로 이러한 접근 방식이 특히 중요하다.

검증(Verification)은 각 안전 메커니즘이 정상 조건과 고장 조건 모두에서 올바르게 동작하는지를 입증해야 한다. 시험에서는 센서 손실, 통신 중단, 위치 추정 성능 저하, 브레이크 고장, 예상하지 못한 보행자, 경로 차단, 잘못된 컨테이너 정보, 충돌하는 장비 명령 등을 발생시킬 수 있다. 목적은 정상적인 동작의 성공 여부만 확인하는 것이 아니라 고장이 발생했을 때 제어되지 않은 작업 지속이 아니라 통제되고 예측 가능한 동작으로 전환되는지를 확인하는 것이다.

시뮬레이션(Simulation)을 이용하면 실제 대형 항만 장비로 위험한 시나리오를 시험하기 전에 이를 반복적으로 검증할 수 있다. 디지털 트윈(Digital Twin)과 시나리오 기반 환경(Scenario-Based Environment)은 교통 충돌, 크레인 상호작용, 낮은 가시성, 통신 손실, 센서 성능 저하, 비상 정지 상황을 재현할 수 있다. 소프트웨어 인 더 루프(Software-in-the-Loop, SIL)와 하드웨어 인 더 루프(Hardware-in-the-Loop, HIL) 시험을 통해 안전 로직을 반복적으로 평가하고, 통제된 현장 시험을 통해 모델링된 동작이 실제 플랫폼에서도 유효한지를 최종적으로 확인할 수 있다.

자율 시스템은 최초 배포 이후에도 지속적으로 발전하기 때문에 변경 관리(Change Management)가 필수적이다. 새로운 인지 모델, 내비게이션 소프트웨어, 지도, 교통 규칙, 센서, 펌웨어 또는 운용 영역은 기존에 평가된 위험을 변화시킬 수 있다. 따라서 소프트웨어 업데이트는 형상 관리(Configuration Control), 회귀 시험(Regression Testing), 안전 영향 평가(Safety-Impact Assessment), 통제된 배포 절차(Controlled Release Procedure)를 거쳐야 한다. 성공적인 업데이트는 단순히 성능을 향상시키는 것이 아니라 배포된 시스템에서 검증된 안전 특성을 유지해야 한다.

사고 및 준사고 보고(Incident and Near-Miss Reporting)는 지속적인 안전 개선을 위한 피드백을 제공한다. 로그에는 비정상적인 이벤트 전후의 로봇 상태, 명령, 센서 상태, 위치 추정 품질, 교통 정보, 장비 상호작용, 운영자 동작, 관련 타임스탬프가 보존되어야 한다. 분석을 통해 사고의 원인이 하드웨어 고장, 인지 성능의 취약점, 잘못된 절차, 인프라 설정 또는 시스템 통합에서 발생했는지를 확인할 수 있다. 이후 시정 조치(Corrective Action)는 후속 검증 과정까지 추적할 수 있어야 한다.

안전 성능(Safety Performance)은 최초 인증 또는 시운전 단계에서만 평가하는 것이 아니라 지속적으로 모니터링해야 한다. 지표에는 비상 정지, 보호 영역 활성화, 최소 이격 거리 이벤트, 위치 추정 성능 저하, 제동 이상, 운영자 개입, 통신 장애, 반복적인 경로 충돌 등이 포함될 수 있다. 이러한 이벤트의 추세를 분석하면 장비 상태의 악화 또는 안전하지 않은 운용 패턴이 더욱 심각한 사고로 발전하기 전에 발견할 수 있다.

고도로 자동화된 터미널에서도 교육(Training)은 여전히 필요하다. 운영자와 유지보수 인력은 로봇 운용 구역, 경고 표시, 비상 절차, 복구 규칙, 수동 제어 제한, 크레인 및 교통 시스템과의 상호작용을 이해해야 한다. 로봇과 동일한 환경을 공유하는 작업자는 정상적인 로봇 동작을 예측하고 비정상 상태를 식별할 수 있어야 한다. 자동화는 사람의 책임을 변화시키지만 운영 역량(Operational Competence)의 필요성을 제거하지는 않는다.

항만 로봇 안전 및 해양 규제(Port Robot Safety and Maritime Regulation)는 궁극적으로 시스템 수준의 거버넌스 접근 방식(System-Level Governance Approach)을 요구한다. 안전한 자동화는 로봇 하드웨어, 자율주행 소프트웨어, 독립적인 보호 기능, 교통 관리, 터미널 인프라, 작업자 절차, 사이버보안, 규제 준수가 결합되어 동작할 때 구현된다. 따라서 확장 가능한 자동화 터미널에는 지능형 로봇뿐만 아니라 장비, 소프트웨어, 항만 운영이 변화하더라도 지속적으로 유효한 추적 가능한 위험 통제(Traceable Risk Control)와 검증된 운용 경계(Verified Operational Boundary)가 필요하다.

## 09.10. Fully Automated Container Terminal Case

![](images/image10.png){width="7.268055555555556in" height="7.268055555555556in"}

완전 자동화 컨테이너 터미널(Fully Automated Container Terminal)은 크레인, 자율 운송 차량, 야드 시스템(Yard System), 식별 서비스(Identification Service), 교통 관리(Traffic Management), 터미널 운영 시스템(Terminal Operating System, TOS)이 하나의 통합된 사이버-물리 물류 시스템(Cyber-Physical Logistics System)으로 동작하는 방식을 보여준다. 자동화는 단순히 개별 장비를 로봇으로 교체하는 것만으로 구현되지 않는다. 터미널은 선박 계획, 컨테이너 이동, 장비 제어, 안전, 정보 흐름을 연결하여 실제 물리적 운영 상태가 디지털 물류 계획을 지속적으로 반영하도록 해야 한다.

운영 주기(Operational Cycle)는 선박이 도착하기 전부터 시작된다. 터미널 운영 시스템(TOS)은 선박, 컨테이너, 야드, 일정 정보를 수신하고 하역 및 선적을 위한 작업 계획을 수립한다. 컨테이너는 운영 요구사항에 따라 목적지 또는 야드 위치에 할당된다. 장비 제어(Equipment Control) 및 차량군 관리 서비스(Fleet-Management Service)는 자원 가용성과 예상 작업량을 고려하여 이러한 계획을 안벽 크레인(Quay Crane), 자율 운송 차량, 자동화 야드 크레인(Automated Yard Crane)이 실행할 수 있는 작업 대기열(Work Queue)로 변환한다.

선박 하역 작업 중 안벽 크레인은 선박에서 컨테이너를 들어 올려 육상 측 인터페이스(Landside Interface)로 이송한다. 크레인 자동화(Crane Automation)는 트롤리(Trolley), 호이스트(Hoist), 스프레더(Spreader), 흔들림 방지(Anti-Sway), 위치 정렬, 컨테이너 잠금 기능을 조정한다. 크레인 제어 시스템은 운영 상태를 터미널 조정 계층(Terminal Coordination Layer)에 보고한다. 컨테이너가 이송 지점에 도착하기 전에 다음 운송 자원을 준비하여 차량 대기로 인해 크레인 생산성이 불필요하게 저하되는 것을 방지한다.

컨테이너에 할당된 AGV 또는 AMR은 차량군 및 교통 조정(Fleet and Traffic Coordination)에 따라 안벽 이송 구역(Quay Transfer Zone)에 접근한다. 물리적인 주행 차선이 비어 있다는 이유만으로 차량이 진입하는 것은 아니며 경로 예약(Route Reservation), 크레인 상태, 이송 구역 승인(Transfer-Zone Authorization), 로컬 안전 조건(Local Safety Condition)이 모두 진입을 허용해야 한다. 정밀 위치 정렬(Precise Positioning)을 통해 차량을 크레인 인터페이스에 맞춘다. 컨테이너 배치와 적재 상태가 확인되면 차량 임무는 픽업에서 적재 운송(Loaded Transport) 상태로 전환된다.

컨테이너 식별(Container Identification)은 실제 물리적 하역 작업과 디지털 기록 사이의 연속성을 형성한다. OCR 카메라 또는 기타 식별 메커니즘을 이용하여 크레인 작업이나 이송 과정에서 컨테이너를 확인할 수 있다. 관측된 식별 정보는 TOS가 생성한 작업 지시(Work Instruction)와 비교된다. 예상 식별자와 관측된 식별자가 일치하지 않으면 검증을 위해 이동 작업을 중단할 수 있다. 이를 통해 고도로 자동화된 시스템에서 하나의 식별 오류가 이후의 운송 및 적재 작업 전체로 빠르게 전파되는 것을 방지할 수 있다.

픽업이 완료되면 자율주행 차량은 안벽 구역에서 할당된 야드 블록(Yard Block)으로 이동한다. 교통 관리 시스템(Traffic-Management System)은 차량군 전체의 교차로, 공유 도로 구간, 대기 구역, 이송 구역을 조정한다. 경로 선택은 단순한 거리뿐만 아니라 혼잡과 자원 예약(Resource Reservation)을 고려한다. 차량 내 자율주행(Onboard Autonomy)은 즉각적인 장애물 대응을 담당하고, 중앙 조정(Centralized Coordination)은 동시에 운용되는 여러 차량 사이에서 발생할 수 있는 구조적인 충돌을 줄인다.

자동화 야드 크레인(Automated Yard Crane)은 도착 예정인 컨테이너와 계획된 적재 위치에 대한 정보를 수신한다. 차량 도착과 크레인 준비 상태를 동기화하여 어느 한쪽의 자원도 이송 인터페이스를 불필요하게 점유하지 않도록 한다. 차량이 지정된 위치에 도착하면 핸드셰이크(Handshake)를 통해 두 시스템이 모두 준비되었는지를 확인한다. 크레인은 컨테이너를 들어 올리고 정상적인 이송을 확인한 후 할당된 적재 위치에 배치하며, 차량은 다음 임무에 사용할 수 있는 상태로 전환된다.

선적 작업(Loading Operation)은 물리적인 흐름을 반대 방향으로 실행하지만 동일하게 정밀한 작업 순서 제어가 필요하다. 컨테이너는 선박 적재 계획(Vessel Loading Plan)에 따라 야드 스택에서 반출되어 안벽 방향으로 운송된다. 지나치게 일찍 도착하면 크레인 주변에 혼잡이 발생할 수 있고, 늦게 도착하면 고가의 안벽 장비가 작업 없이 대기하게 될 수 있다. 따라서 터미널은 야드 반출, 차량 배차, 이동 시간, 크레인 수요를 조정하여 적절한 운영 시간 구간(Operational Window) 내에 컨테이너가 도착하도록 한다.

TOS는 컨테이너 재고와 계획된 이동에 대한 비즈니스 수준의 표현(Business-Level Representation)을 유지하고, 장비 시스템은 세부적인 실행 상태를 유지한다. 두 시스템 사이의 통합은 작업 승인, 픽업, 이송, 도착, 완료, 실패, 취소와 같은 명확한 이벤트에 의존한다. 디지털 컨테이너 위치는 해당 물리적 이벤트가 검증된 경우에만 변경되어야 한다. 이러한 이벤트 기반 관계(Event-Driven Relationship)는 정보 시스템의 상태가 실제 터미널 상태와 불일치하는 것을 방지한다.

차량군 관리(Fleet Management)는 사용 가능한 차량에 운송 작업을 지속적으로 할당한다. 할당 과정에서는 차량 위치, 현재 임무, 배터리 상태, 적재 호환성, 유지보수 상태, 경로 가용성, 예상 완료 시간을 고려한다. 국지적으로 최적인 할당이라도 혼잡을 증가시키거나 중요한 크레인의 작업을 지연시키면 전체 터미널 관점에서는 최적의 결과를 만들지 못할 수 있다. 따라서 차량군 최적화(Fleet Optimization)는 각각의 운송 요청을 독립적으로 처리하기보다 교통 상황과 장비 작업량의 상호작용을 함께 고려해야 한다.

자동화 규모가 증가할수록 교통 조정(Traffic Coordination)의 중요성도 증가한다. 수백 개의 이동 작업이 동시에 수행되면 개별 차량이 모두 유효한 경로를 따르더라도 혼잡이 발생할 수 있다. 예약 메커니즘(Reservation Mechanism)을 이용하여 교차로, 좁은 구간, 이송 구역의 접근을 제어할 수 있다. 예측 교통 알고리즘(Predictive Traffic Algorithm)은 예정된 임무를 기반으로 미래의 충돌을 예측하고 대기열이 형성되기 전에 차량 경로를 변경할 수 있다. 여러 자원 의존성을 정상적으로 해결할 수 없는 경우에는 교착 상태 감지 및 복구(Deadlock Detection and Recovery)가 추가적인 보호 기능을 제공한다.

충전으로 인해 차량이 실제 작업에서 제외되므로 에너지 관리(Energy Management)는 생산 계획(Production Planning)과 통합된다. 차량군 시스템은 계획된 컨테이너 이동을 기반으로 에너지 수요를 예측하고 작업량이 허용하는 시간에 충전을 예약한다. 배터리 상태, 예상 경로 길이, 적재량, 대기 시간, 향후 임무 수요가 배차 결정에 영향을 줄 수 있다. 조정된 충전(Coordinated Charging)은 선박 작업이 집중되는 시간대에 지나치게 많은 차량이 사용 불가능한 상태가 되는 것을 방지하고 중요한 작업 중 불필요한 충전 중단을 줄인다.

예외 처리(Exception Handling)는 강건한 자동화 터미널과 이상적인 조건에서만 작동하는 시스템을 구분하는 중요한 요소이다. 도로 차단, 차량 고장, 크레인 고장, 판독할 수 없는 컨테이너 ID, 통신 손실, 배터리 부족, 사용할 수 없는 야드 위치 등이 계획된 작업 흐름을 중단시킬 수 있다. 제어 아키텍처(Control Architecture)는 영향을 받은 컨테이너와 자원을 식별하고 문제를 격리한 후 복구 동작(Recovery Action)을 선택해야 하며, 안전이 보장되는 범위에서는 관련되지 않은 다른 터미널 작업이 계속 수행될 수 있도록 해야 한다.

일상적인 컨테이너 이동이 고도로 자동화되더라도 운영자(Human Operator)는 여전히 중요한 역할을 수행한다. 운영자의 역할은 지속적인 장비 직접 제어에서 시스템 감독, 예외 해결, 유지보수 조정, 운영 의사결정 지원(Operational Decision Support)으로 변화한다. 모니터링 인터페이스(Monitoring Interface)는 컨테이너 작업, 장비 상태, 교통 상황, 경보, 개입 요청, 시스템 의존성을 표시해야 한다. 운영자는 복구를 승인하거나 운영 계획을 변경하기 전에 자동화 시스템이 정지한 이유를 이해할 수 있는 충분한 상황 정보를 확보해야 한다.

안전 기능(Safety Function)은 처리량 최적화(Throughput Optimization)와 독립적으로 유지되어야 한다. 비상 정지(Emergency Stopping), 보호 센싱(Protective Sensing), 속도 감시(Speed Supervision), 지오펜싱(Geofencing), 제동 감시(Braking Monitoring), 장비 인터록(Equipment Interlock), 이송 구역 보호(Transfer-Zone Protection)는 필요한 경우 임무 실행보다 우선할 수 있다. 중앙 스케줄링은 안전하지 않은 로컬 움직임을 승인할 수 없으며, 로컬 자율주행도 인프라 제한을 무시할 수 없다. 이러한 분리를 통해 높은 생산성이라는 목표는 검증된 물리적 및 운영 안전 경계 내부에서만 추구된다.

통신 인프라(Communication Infrastructure)는 TOS, 차량군 서비스, 교통 관리자, 크레인, 로봇, OCR 시스템, 안전 서비스, 모니터링 플랫폼을 연결한다. 신뢰성 있는 메시징(Reliable Messaging)을 위해서는 일관된 식별자, 타임스탬프(Timestamp), 인터페이스 스키마(Interface Schema), 확인 응답 규칙(Acknowledgement Rule), 고장 복구 동작(Fault-Recovery Behavior)이 필요하다. 일시적인 네트워크 성능 저하가 서로 모순되는 컨테이너 상태를 발생시켜서는 안 된다. 시스템은 이벤트를 버퍼링하거나 정의된 성능 저하 모드(Degraded Mode)로 전환할 수 있지만 중요한 의사결정에서는 물리적 안전과 트랜잭션 일관성(Transactional Consistency)을 모두 유지해야 한다.

관측 가능성(Observability)은 터미널 성능을 이해하는 데 필요한 데이터를 제공한다. 장비 텔레메트리(Equipment Telemetry)와 물류 이벤트를 이용하여 크레인 사이클 시간, 차량 이동 시간, 대기열 시간, 이송 지연, 야드 처리 시간, 에너지 소비, 임무 실패, 운영자 개입 등을 측정할 수 있다. 이러한 측정 결과를 통해 단순히 전체 터미널 통계에 의존하지 않고 처리량의 제한 요인이 크레인 생산성, 차량 가용성, 도로 혼잡, 야드 용량, 소프트웨어 조정 또는 다른 서브시스템 중 어디에 있는지를 파악할 수 있다.

디지털 트윈(Digital Twin)은 선박 작업량, 크레인, 운송 차량군, 도로망, 야드 블록, 충전 자원, 운영 규칙 사이의 관계를 재현할 수 있다. 교통 정책이나 차량군 규모를 변경하기 전에 운영자는 이러한 변화가 혼잡과 처리량에 미치는 영향을 시뮬레이션할 수 있다. 동일한 환경을 소프트웨어 인 더 루프(Software-in-the-Loop, SIL) 및 하드웨어 인 더 루프(Hardware-in-the-Loop, HIL) 시험에도 활용하여 새로운 알고리즘이나 인터페이스를 실제 운영 환경에 배포하기 전에 대표적인 작업량과 고장 시나리오를 대상으로 평가할 수 있다.

터미널 전체의 조정 기능에 장애가 발생하면 동시에 많은 장비가 영향을 받을 수 있으므로 고가용성(High Availability)이 필수적이다. 핵심 서비스에는 이중화(Redundancy), 복제된 상태(Replicated State), 상태 감시(Health Monitoring), 통제된 장애 전환(Controlled Failover), 영구 이벤트 저장(Persistent Event Storage)을 적용할 수 있다. 시스템 재시작 이후 모든 작업을 처음부터 다시 시작한다고 가정하는 대신 진행 중인 임무와 실제 컨테이너 상태를 복원해야 한다. 중앙 조정 기능을 일시적으로 사용할 수 없는 경우에도 분산된 장비는 예측 가능한 안전 동작으로 전환해야 한다.

사이버보안(Cybersecurity)은 기업 물류 시스템과 실제 물리적 자동화 사이의 경계를 보호한다. 서비스 인증(Service Authentication), 권한 부여(Authorization), 네트워크 분할(Network Segmentation), 안전한 소프트웨어 배포(Secure Software Deployment), 메시지 무결성(Message Integrity), 감사 로깅(Audit Logging)은 침해된 정보 시스템이 장비 움직임에 영향을 줄 위험을 줄인다. 비즈니스 명령과 안전 필수 제어(Safety-Critical Control) 사이의 분리를 유지하여 계획 애플리케이션에 대한 비인가 접근이 액추에이터를 직접 제어하거나 보호 기능을 비활성화하지 못하도록 해야 한다.

지속적인 최적화(Continuous Optimization)는 운영 이력을 이용하여 스케줄링, 경로 계획, 에너지 계획, 유지보수, 자원 할당을 개선한다. 예측 모델(Predictive Model)은 크레인 수요, 혼잡, 장비 고장, 임무 소요 시간을 예측하여 오케스트레이션 계층(Orchestration Layer)에 권고 사항을 제공할 수 있다. 이러한 지능형 기능은 운영 책임성을 불명확하게 만들지 않으면서 의사결정을 향상시켜야 한다. 자동화된 권고 사항은 해당 결과를 생성한 임무, 자원 상태, 제약 조건까지 추적 가능해야 한다.

완전 자동화 컨테이너 터미널은 결과적으로 폐쇄형 디지털-물리 제어 루프(Closed Digital-to-Physical Control Loop)로 동작한다. TOS가 물류 의도(Logistics Intent)를 정의하면 오케스트레이션 서비스가 자원을 할당하고, 교통 관리 시스템이 공유 공간을 조정하며, 크레인과 로봇이 실제 물리적 작업을 수행하고, 인지 시스템(Perception System)이 컨테이너 식별 정보와 환경 상태를 검증한 후 확인된 이벤트가 다시 디지털 기록을 갱신한다. 터미널의 성능은 특정 장비 하나의 속도가 아니라 이러한 기능 전체의 동기화에서 결정된다.

이 사례는 산업용 항만 자동화(Industrial Port Automation)의 더 광범위한 발전 방향을 보여준다. 개별 자동화 장비는 조정된 차량군(Coordinated Fleet)으로 발전하고, 궁극적으로는 하나의 통합 터미널 시스템(Integrated Terminal System)으로 확장된다. 확장 가능한 자동화를 위해서는 표준화된 인터페이스(Standardized Interface), 명시적인 상태 모델(Explicit State Model), 결정론적 안전 경계(Deterministic Safety Boundary), 복원력 있는 통신(Resilient Communication), 추적 가능한 이벤트(Traceable Event), 시스템 전체 최적화(System-Wide Optimization)가 필요하다. 궁극적인 목표는 높은 처리량으로 복잡한 컨테이너 흐름을 실행하면서도 관측 가능하고, 복구 가능하며, 안전하고, 운영상 신뢰할 수 있는 터미널을 구현하는 것이다.
