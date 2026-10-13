**Volume 26. Industrial Robot Applications**

# Chapter 10. Industrial Failure Analysis

## 10.01. Industrial Robot Failure Taxonomy SW HW AI

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

산업용 로봇(Industrial Robot)의 고장은 개별 부품의 결함이 아니라 시스템 수준 사건(System-Level Event)으로 분류해야 한다. 로봇이 정지하는 현상은 손상된 액추에이터(Actuator) 때문에 발생할 수 있지만, 동일한 운용 증상은 소프트웨어 타이밍(Software Timing), 센서 성능 저하(Sensor Degradation), 통신 손실(Communication Loss), 잘못된 설정(Configuration), 인공지능 의사결정(AI Decision)에서도 발생할 수 있다. 따라서 실용적인 고장 분류체계(Failure Taxonomy)는 하드웨어(Hardware), 소프트웨어(Software), 인공지능(AI), 통신(Communication), 환경(Environment), 인적 요인(Human-Induced Failure)을 구분하면서 이들 사이의 인과관계(Causal Relationship)를 함께 보존해야 한다.

하드웨어 고장(Hardware Failure)은 모터(Motor), 엔코더(Encoder), 브레이크(Brake), 기어박스(Gearbox), 배터리(Battery), 전력 변환기(Power Converter), 카메라(Camera), 라이다(LiDAR), 케이블(Cable), 커넥터(Connector), 냉각 장치(Cooling Device), 컴퓨팅 모듈(Computing Module)과 같은 물리적 구성요소에서 발생한다. 대표적인 증상에는 과도한 진동(Excessive Vibration), 열 차단(Thermal Shutdown), 전압 불안정(Voltage Instability), 엔코더 드리프트(Encoder Drift), 간헐적 통신 장애(Intermittent Communication), 토크 감소(Reduced Torque), 기계적 마모(Mechanical Wear)가 있다. 하드웨어 결함은 점진적으로 진행되는 경우가 많으므로 텔레메트리 추세(Telemetry Trend)와 예방 점검(Preventive Inspection)이 중요한 진단 자원이 된다.

소프트웨어 고장(Software Failure)은 애플리케이션 로직(Application Logic), 미들웨어(Middleware), 운영체제(Operating System), 드라이버(Driver), 설정(Configuration), 자원 관리(Resource Management), 실시간 실행(Real-Time Execution)의 결함으로 인해 로봇 동작이 의도된 기능에서 벗어날 때 발생한다. 대표적인 사례에는 프로세스 충돌(Process Crash), 메모리 누수(Memory Leak), 교착상태(Deadlock), 경쟁 상태(Race Condition), 잘못된 상태 전이(Invalid State Transition), 메시지 시간 초과(Message Timeout), 부적절한 예외 처리(Exception Handling)가 있다. 광범위한 소프트웨어 아키텍처(Software Architecture)의 임베디드(Embedded), 실시간(Real-Time), 제어(Control), 미들웨어(Middleware), 통신(Communication), 데이터(Data), 배포(Deployment) 계층 모두 이러한 고장에 관여할 수 있다.

제어 시스템 고장(Control-System Failure)은 소프트웨어와 하드웨어 사이의 중요한 경계 영역을 형성한다. 불안정한 제어기(Unstable Controller), 잘못된 게인(Gain), 지연된 피드백(Delayed Feedback), 액추에이터 포화(Actuator Saturation), 불량한 궤적 추종(Trajectory Tracking), 일관되지 않은 좌표 변환(Coordinate Transformation)은 기계적 고장과 유사한 물리적 이상 동작을 발생시킬 수 있다. 따라서 산업 현장의 고장 진단에서는 문제를 즉시 하드웨어 또는 소프트웨어로 단정하기보다 명령 운동(Commanded Motion), 측정 운동(Measured Motion), 액추에이터 전류(Actuator Current), 제어 오차(Control Error), 타이밍(Timing), 안전 상태 전이(Safety-State Transition)를 함께 분석해야 한다.

인공지능 고장(AI Failure)은 소프트웨어 관점에서 시스템이 정상적으로 실행되고 있음에도 잘못된 추론(Inference)을 생성할 수 있기 때문에 다른 방식으로 해석해야 한다. 인식 모델(Perception Model)은 장애물을 놓치거나 객체를 잘못 분류하고, 부정확한 자세(Pose)를 생성하거나 조명, 날씨, 가림(Occlusion), 센서 오염(Sensor Contamination), 미경험 환경(Unfamiliar Environment)에서 실패할 수 있다. 계획 모델(Planning Model)과 학습 정책(Learned Policy) 역시 모든 소프트웨어 프로세스가 정상적으로 동작하고 기존 예외(Exception)가 발생하지 않는 상황에서도 안전하지 않거나 비효율적인 행동을 선택할 수 있다.

데이터 관련 인공지능 고장(Data-Related AI Failure)은 모델 구현 결함(Model Implementation Defect)과 구분해야 한다. 학습 데이터(Training Data)가 실제 배포 환경에서 발생하는 희귀 객체(Rare Object), 환경 조건(Environmental Condition), 장비 구성(Equipment Configuration), 고장 상태(Failure State)를 충분히 표현하지 못할 수 있다. 운영 환경이 변화하면 분포 이동(Distribution Shift)으로 모델 신뢰성이 점진적으로 감소할 수 있으며, 라벨 오류(Label Error), 클래스 불균형(Class Imbalance), 보정 문제(Calibration Problem), 센서 도메인 차이(Sensor-Domain Difference), 부적절한 전처리(Preprocessing)는 물리적 부품 손상 없이도 체계적인 고장을 발생시킬 수 있다.

내비게이션 고장(Navigation Failure)은 다차원 고장 분류체계(Multidimensional Failure Taxonomy)가 필요한 이유를 잘 보여준다. 로봇이 움직이지 못하는 고착(Stuck) 상태는 휠 엔코더(Wheel Encoder) 결함, 위치추정 발산(Localization Divergence), 손상된 지도(Corrupted Map), 경로 차단(Blocked Path), 플래너 진동(Planner Oscillation), 부정확한 장애물 인식(Obstacle Detection), 통신 중단(Communication Interruption), 플릿 수준 교통 충돌(Fleet-Level Traffic Conflict) 등에서 발생할 수 있다. 따라서 내비게이션의 고착과 교착상태(Deadlock)는 모든 이동 문제를 하나의 하위 시스템에 귀속시키지 않고 독립적인 분석 범주로 다루어야 한다.

조작 고장(Manipulation Failure) 역시 여러 영역에 걸쳐 발생한다. 물체 낙하(Dropped Object)는 그리퍼 마모(Gripper Wear), 부족한 파지력(Insufficient Force), 부정확한 자세 추정(Pose Estimation), 캘리브레이션 드리프트(Calibration Drift), 궤적 오류(Trajectory Error), 예상하지 못한 물체 특성(Object Property), 지연시간(Latency), 인공지능 파지 선택 오류(AI Grasp-Selection Error)에서 발생할 수 있다. 픽업 실패(Missed Pick)와 삽입 실패(Insertion Failure)는 인식(Perception), 계획(Planning), 제어(Control), 액추에이터(Actuator), 엔드 이펙터(End-Effector), 물체(Object), 환경(Environment) 요인으로 분해하여 서로 다른 근본 원인을 추적할 수 있어야 한다.

통신 및 인프라 고장(Communication and Infrastructure Failure)에는 패킷 손실(Packet Loss), 과도한 지연시간(Excessive Latency), 동기화 오류(Synchronization Error), 네트워크 혼잡(Network Congestion), 미들웨어 탐색 문제(Middleware Discovery Problem), API 장애(API Failure), 데이터베이스 장애(Database Outage), 플릿 서버 중단(Fleet-Server Interruption), 클라우드 또는 온프레미스 서비스(Cloud or On-Premise Service) 손실이 포함된다. 현대 로봇은 임베디드 버스(Embedded Bus)에서 ROS 2, 플릿 API(Fleet API), 엣지 시스템(Edge System), 클라우드 서비스(Cloud Service)에 이르는 통신 계층에 의존하므로 통신 결함 하나가 여러 로봇으로 확산될 수 있다.

환경 고장(Environmental Failure)은 운용 조건이 하드웨어, 소프트웨어 또는 인공지능 설계에 내재된 가정을 벗어날 때 발생한다. 먼지(Dust), 비(Rain), 안개(Fog), 온도(Temperature), 진동(Vibration), 반사 표면(Reflective Surface), 불량한 조명(Poor Lighting), 불규칙 지형(Uneven Terrain), 전자기 간섭(Electromagnetic Interference), 동적 장애물(Dynamic Obstacle)은 센싱이나 연산 성능을 저하시킬 수 있다. 이러한 상황에서는 로봇 자체가 기술적으로 정상 동작 상태를 유지하면서도 실제 운용 능력(Operational Capability)이 안전한 임무 수행에 필요한 수준 아래로 떨어질 수 있다는 점이 중요하다.

인적 및 운용 고장(Human and Operational Failure)에는 잘못된 설정(Incorrect Configuration), 유지보수 실수(Maintenance Mistake), 부적절한 적재(Improper Payload Loading), 안전하지 않은 임무 정의(Unsafe Mission Definition), 승인되지 않은 파라미터 변경(Unauthorized Parameter Change), 불완전한 캘리브레이션(Incomplete Calibration), 부적절한 복구 조치(Recovery Action)가 포함된다. 이를 단순한 작업자 오류(Operator Error)로 처리하기보다 인터페이스(Interface), 절차(Procedure), 권한(Permission), 진단 기능(Diagnostics), 안전 메커니즘(Safety Mechanism)이 예측 가능한 인간 행동을 시스템 고장으로 발전시키도록 허용했는지를 분석해야 한다.

고장은 시간적 동작 특성(Temporal Behavior)에 따라서도 분류해야 한다. 영구 고장(Permanent Fault)은 수리할 때까지 지속되고, 간헐 고장(Intermittent Fault)은 예측하기 어렵게 반복되며, 일시 고장(Transient Fault)은 짧은 외란 이후 사라진다. 진행성 고장(Progressive Fault)은 마모나 성능 저하에 따라 점차 악화된다. 심각도(Severity) 측면에서도 경미한 성능 저하(Performance Reduction)는 임무 중단(Mission Abortion), 생산 중단(Production Stoppage), 장비 손상(Equipment Damage), 안전 중요 사건(Safety-Critical Event)과 명확히 구분해야 하며, 발생 빈도(Frequency)와 검출 가능성(Detectability)도 관리 우선순위를 결정하는 핵심 요소가 된다.

결함(Fault), 오류(Error), 고장(Failure), 결과(Consequence)의 차이를 명확히 구분하는 것은 신뢰성 있는 분석의 핵심이다. 결함(Fault)은 근본적인 비정상 조건(Abnormal Condition)을 의미하며, 오류(Error)는 해당 결함에 의해 발생한 잘못된 내부 상태(Incorrect Internal State)를 의미한다. 고장(Failure)은 외부에서 요구되는 동작을 더 이상 제공할 수 없는 상태이며, 결과(Consequence)는 그로 인한 운용 영향을 나타낸다. 이러한 계층을 유지하면 "로봇 정지(Robot Stopped)"와 같은 증상을 근본 원인(Root Cause)으로 잘못 기록하는 것을 방지할 수 있다.

교차 영역 전파(Cross-Domain Propagation)는 산업용 로봇에서 특히 중요하다. 오염된 카메라(Contaminated Camera)가 인식 성능을 저하시키고, 부정확한 장애물 추정(Obstacle Estimation)을 생성하며, 반복적인 재계획(Replanning)을 발생시켜 프로세서 부하(Processor Load)를 증가시킬 수 있다. 그 결과 제어 메시지(Control Message)가 지연되고 최종적으로 안전 정지(Safety Stop)가 발생할 수 있다. 최종 사건은 소프트웨어 시간 초과(Software Timeout)처럼 보이지만 최초 조건은 환경 문제일 수 있으므로, 고장 기록에는 시작 결함(Initiating Fault), 전파 경로(Propagation Path), 검출 메커니즘(Detection Mechanism), 복구 조치(Recovery Action), 최종 결과(Final Consequence)가 함께 포함되어야 한다.

플릿 운영(Fleet Operation)은 개별 로봇의 문제가 집단적인 문제(Collective Problem)로 발전할 수 있기 때문에 또 다른 고장 분류 계층을 추가한다. 한 대의 로봇이 통로에서 정지하면 공유 통로(Shared Aisle)를 차단하고, 교통 혼잡(Traffic Congestion), 임무 대기열(Mission Queue)을 발생시키며, 수십 또는 수백 대 로봇의 처리량(Throughput)을 감소시킬 수 있다. 따라서 플릿 고장(Fleet Failure)은 개별 로봇의 결함뿐 아니라 디스패치 오류(Dispatch Error), 자원 충돌(Resource Conflict), 충전 혼잡(Charging Congestion), 교착상태(Deadlock), 동기화 문제(Synchronization Problem), 공유 서비스 장애(Shared-Service Outage), 연쇄 고장(Cascading Failure)을 포함해야 한다.

실용적인 산업용 고장 분류체계(Industrial Failure Taxonomy)의 최종 목적은 단순히 고장에 이름을 붙이는 것이 아니라 진단(Diagnosis)과 개선(Improvement)을 지원하는 것이다. 각각의 사고 기록(Incident Record)은 관찰된 증상(Observed Symptom)을 영향받은 하위 시스템(Affected Subsystem), 고장 영역(Failure Domain), 심각도(Severity), 지속시간(Duration), 운용 상황(Operational Context), 추정 원인(Probable Cause), 복구 방법(Recovery Method), 재발 이력(Recurrence History)과 연결해야 한다. 이렇게 구조화된 기록은 이후 근본 원인 분석(Root Cause Analysis), 로그 패턴 마이닝(Log Pattern Mining), 인식 성능 개선(Perception Improvement), 다운타임 측정(Downtime Measurement), 예측 고장 탐지(Predictive Failure Detection), 개발 피드백(Development Feedback)을 수행하기 위한 기반이 된다.

## 10.02. Root Cause Analysis RCA Methodology for Robots [w/Code]

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

산업용 로봇(Industrial Robot)의 근본 원인 분석(Root Cause Analysis, RCA)은 단순히 무엇이 작동을 멈추었는지를 설명하는 것이 아니라 운용 고장(Operational Failure)이 왜 발생했는지를 식별하기 위한 체계적인 방법론이다. 로봇 정지(Robot Shutdown), 내비게이션 오류(Navigation Error), 물체 낙하(Dropped Object), 안전 정지(Safety Stop)는 관찰 가능한 결과(Observable Consequence)로 취급한다. 근본 원인 분석(RCA)은 이러한 결과에서 역방향으로 소프트웨어(Software), 하드웨어(Hardware), 인공지능(AI), 통신(Communication), 환경(Environment), 운용(Operational) 계층을 추적하여 최초 발생 조건(Initiating Condition)과 기여 메커니즘(Contributing Mechanism)을 식별한다.

효과적인 근본 원인 분석(RCA)은 정확한 문제 정의(Problem Definition)에서 시작한다. 조사 과정에서는 로봇이 어떤 작업을 수행하도록 명령받았는지, 실제로 어떤 일이 발생했는지, 언제 어디에서 정상 동작과의 편차가 나타났는지, 어떤 하위 시스템(Subsystem)이 동작하고 있었는지, 운용에 어떤 영향을 미쳤는지를 확인해야 한다. "로봇이 고장났다"와 같은 표현은 진단 가치가 거의 없다. 유용한 문제 정의에는 임무(Mission), 운용 상태(Operating State), 고장 발생 시각(Failure Timestamp), 관찰된 증상(Observed Symptom), 영향받은 기능(Affected Function), 복구 동작(Recovery Behavior), 생산 영향(Production Consequence)이 포함되어야 한다.

원인에 대한 가정이 지배적으로 형성되기 전에 증거 수집(Evidence Collection)이 이루어져야 한다. 로봇 로그(Robot Log), 센서 기록(Sensor Recording), 제어기 상태(Controller State), 액추에이터 전류(Actuator Current), CPU 및 GPU 사용률(Utilization), 네트워크 통계(Network Statistics), 위치추정 신뢰도(Localization Confidence), 인공지능 추론 결과(AI Inference Output), 안전 이벤트(Safety Event), 작업자 조작(Operator Action), 플릿 서버 기록(Fleet-Server Record)을 고장 발생 구간을 중심으로 시간 동기화해야 한다. 로봇 재시작, 경보 해제, 설정 변경은 최초 사건을 재구성하는 데 필요한 정보를 제거할 수 있으므로 원시 증거(Raw Evidence)를 보존하는 것이 중요하다.

시간 동기화(Time Synchronization)는 분산 로봇 시스템(Distributed Robot System)에서 특히 중요하다. 인식(Perception), 위치추정(Localization), 계획(Planning), 제어(Control), 안전(Safety), 플릿 관리(Fleet Management), 외부 인프라(External Infrastructure)는 서로 다른 컴퓨터나 제어기에 이벤트를 기록할 수 있다. 공통 시간 기준(Common Temporal Reference)이 없으면 조사자가 원인과 결과의 순서를 반대로 판단할 수 있다. 따라서 근본 원인 분석(RCA)은 이상 발생 이전의 로봇 상태, 최초 사건(Initiating Event), 중간 전파(Intermediate Propagation), 이상 검출(Detection), 보호 대응(Protective Response), 복구 시도(Recovery Attempt), 최종 운용 결과(Operational Outcome)를 보여주는 통합 이벤트 타임라인(Unified Event Timeline)을 재구성해야 한다.

첫 번째 분석 단계에서는 증상(Symptom), 고장 형태(Failure Mode), 기여 요인(Contributing Factor), 근본 원인(Root Cause)을 구분해야 한다. 안전 정지(Safety Stop)는 일반적으로 근본 원인이 아니라 증상 또는 보호 대응(Protective Response)에 해당한다. 고장 형태는 위치추정 손실(Loss of Localization)일 수 있으며, 낮은 조도(Poor Illumination)와 카메라 오염(Camera Contamination)이 기여 요인이 될 수 있다. 최종적인 근본 원인은 성능이 저하된 인식 시스템이 위치추정 신뢰도가 붕괴할 때까지 계속 사용되도록 허용한 부적절한 센서 상태 감시 메커니즘(Sensor-Health Mechanism)일 수 있다.

실용적인 근본 원인 분석(RCA)은 하향식 추론(Top-Down Reasoning)과 상향식 추론(Bottom-Up Reasoning)을 결합한다. 하향식 분석은 관찰된 고장에서 시작하여 어떤 조건이 해당 고장을 발생시킬 수 있었는지를 반복적으로 추적한다. 상향식 분석은 비정상 텔레메트리(Abnormal Telemetry), 로그(Log), 하드웨어 측정값(Hardware Measurement), 하위 시스템 이벤트(Subsystem Event)를 조사하여 최종 고장으로 어떻게 전파되었는지를 확인한다. 두 방향의 분석 결과가 일치할 때 최종 오류 메시지나 최초 비정상 로그만으로 설명하는 것보다 훨씬 강력한 근거를 확보할 수 있다.

5회 왜 분석(Five Whys)은 비교적 단순한 로봇 사고(Robot Incident)를 분석하는 데 유용하지만, 각각의 "왜(Why)"는 추측이 아니라 증거로 뒷받침되어야 한다. 자율이동로봇(AMR)이 위치추정 손실로 정지했다면 위치추정 신뢰도가 왜 감소했는지, 센서 관측(Sensor Observation)이 왜 불안정해졌는지, 성능 저하가 왜 검출되지 않았는지, 시스템이 왜 자율 운행을 계속했는지를 단계적으로 질문할 수 있다. 이 방법은 즉각적인 기술적 증상에서 설계(Design), 모니터링(Monitoring), 유지보수(Maintenance), 프로세스(Process)의 구조적 취약점으로 분석 범위를 확장할 때 효과적이다.

피시본 분석(Fishbone Analysis) 또는 원인-결과 분석(Cause-and-Effect Analysis)은 여러 영역이 동시에 영향을 줄 가능성이 있을 때 더욱 적합하다. 후보 원인은 하드웨어(Hardware), 소프트웨어(Software), 인공지능 및 데이터(AI and Data), 통신(Communication), 환경(Environment), 인간 운용(Human Operation), 유지보수(Maintenance), 프로세스(Process)를 중심으로 구성할 수 있다. 반복적인 조작 실패(Manipulation Failure)의 경우 특정 하위 시스템을 성급하게 원인으로 결정하기보다 그리퍼 마모(Gripper Wear), 캘리브레이션 오류(Calibration Error), 자세 추정 불확실성(Pose-Estimation Uncertainty), 궤적 파라미터(Trajectory Parameter), 물체 변화(Object Variation), 지연시간(Latency), 작업자 설정(Operator Setup)을 함께 비교해야 한다.

결함 트리 분석(Fault Tree Analysis, FTA)은 안전 중요 고장(Safety-Critical Failure)이나 복잡한 고장에 더욱 형식적인 분석 방법을 제공한다. 충돌(Collision), 비제어 운동(Uncontrolled Motion), 화물 낙하(Dropped Payload), 임무 손실(Mission Loss)과 같은 바람직하지 않은 최상위 사건(Top Event)을 논리적 관계(Logical Relationship)로 연결된 하위 수준 사건(Lower-Level Event)의 조합으로 분해한다. 이를 통해 여러 조건이 동시에 발생해야 고장이 나타나는지 또는 하나의 조건만으로도 사건이 발생할 수 있는지를 식별할 수 있으며, 외형적으로 이중화된 로봇 하위 시스템을 동시에 무력화할 수 있는 공통 원인 고장(Common-Cause Failure)도 발견할 수 있다.

소프트웨어 근본 원인 분석(Software RCA)은 애플리케이션(Application), 미들웨어(Middleware), 운영체제(Operating System), 임베디드(Embedded) 계층 사이의 상관관계를 분석해야 한다. 플래너 시간 초과(Planner Timeout)는 과도한 연산(Excessive Computation), 메모리 압박(Memory Pressure), 통신 차단(Blocked Communication), 교착상태(Deadlock), 드라이버 지연(Driver Delay), 상위 센서 과부하(Upstream Sensor Overload)에서 발생할 수 있다. 따라서 스택 추적(Stack Trace)과 오류 코드(Error Code)는 자원 사용률(Resource Utilization), 메시지 지연시간(Message Latency), 프로세스 생명주기 이벤트(Process Lifecycle Event), 소프트웨어 버전(Software Version), 설정 변경(Configuration Change), 배포 이력(Deployment History)과 함께 분석해야 한다.

인공지능 관련 근본 원인 분석(AI-Related RCA)은 인공지능 구성요소가 연산상 정상 상태를 유지하면서도 잘못된 결과를 생성할 수 있기 때문에 기존 예외 로그(Exception Log)의 범위를 넘어야 한다. 조사자는 모델 버전(Model Version), 입력 센서 데이터(Input Sensor Data), 전처리 파라미터(Preprocessing Parameter), 신뢰도 값(Confidence Value), 출력 예측(Output Prediction), 환경 조건(Environmental Condition), 후속 의사결정(Downstream Decision)을 보존해야 한다. 동일한 입력을 오프라인 재생(Offline Replay)함으로써 고장의 재현 가능성을 확인하고 원인이 센싱(Sensing), 전처리(Preprocessing), 모델 동작(Model Behavior), 분포 이동(Distribution Shift), 의사결정 임계값(Decision Threshold) 중 어디에 존재하는지 판단할 수 있다.

하드웨어 근본 원인 분석(Hardware RCA)은 갑작스러운 부품 고장(Sudden Component Failure)을 점진적인 성능 저하(Progressive Degradation) 및 2차 손상(Secondary Damage)과 구분해야 한다. 모터 전류(Motor Current), 온도(Temperature), 진동(Vibration), 엔코더 일관성(Encoder Consistency), 배터리 전압(Battery Voltage), 전력 품질(Power Quality), 커넥터 상태(Connector Condition), 기계적 검사(Mechanical Inspection)를 통해 사건 이전부터 진행된 성능 저하를 발견할 수 있다. 고장 부품을 교체하면 운용은 복구될 수 있지만, 과부하(Overload), 열 스트레스(Thermal Stress), 오염(Contamination), 부적절한 유지보수(Inadequate Maintenance), 제조 편차(Manufacturing Variation), 부적합한 운용 조건(Operating Condition) 등 부품이 고장난 이유가 확인될 때까지 분석을 계속해야 한다.

내비게이션 및 플릿 사고(Navigation and Fleet Incident)는 원인이 하나의 로봇을 넘어서는 경우가 많으므로 시스템 수준 재구성(System-Level Reconstruction)이 필요하다. 차단된 자율이동로봇(AMR)은 재계획(Replanning)을 발생시키고, 교통 예약 충돌(Traffic Reservation Conflict), 대기열 증가(Queue Growth)를 거쳐 결국 플릿 전체의 혼잡(Fleet-Wide Congestion)을 초래할 수 있다. 조사자는 로컬 내비게이션 로그(Local Navigation Log)를 지도(Map), 장애물 관측(Obstacle Observation), 예약 상태(Reservation State), 임무 할당(Mission Assignment), 플릿 명령(Fleet Command), 주변 로봇 궤적(Nearby Robot Trajectory)과 연계하여 집단 조정 실패(Collective Coordination Failure)가 단순한 로컬 내비게이션 문제로 잘못 분류되는 것을 방지해야 한다.

시정 조치(Corrective Action)는 단순히 서비스를 복구하는 것이 아니라 검증된 인과 메커니즘(Causal Mechanism)을 해결해야 한다. 즉각적인 봉쇄 조치(Immediate Containment)에는 프로세스 재시작, 하드웨어 교체, 센서 재보정(Recalibration), 로봇 수동 복구가 포함될 수 있다. 영구 시정 조치(Permanent Corrective Action)는 소프트웨어 수정, 추가 진단 기능(Additional Diagnostics), 인공지능 임계값 수정, 하드웨어 재설계, 환경 보호 개선, 유지보수 변경, 운용 절차 개선을 요구할 수 있다. 이후 예방 조치(Preventive Action)를 통해 동일한 메커니즘이 다른 로봇, 사이트(Site), 소프트웨어 버전에도 존재하는지 확인해야 한다.

근본 원인 분석(RCA)은 시정 조치가 검증될 때까지 완료된 것으로 간주해서는 안 된다. 수정된 시스템은 시뮬레이션(Simulation), 로그 재생(Log Replay), 소프트웨어 시험(Software Testing), 하드웨어 인더루프 시험(Hardware-in-the-Loop Testing), 통제된 현장 시험(Controlled Field Testing), 생산 모니터링(Production Monitoring)을 통해 최초 운용 조건을 재현해야 한다. 성공적인 검증은 단순히 로봇이 다시 동작한다는 것을 의미하는 것이 아니라 식별된 인과 사슬(Causal Chain)이 차단되었으며 동일한 조건에서 최초 고장이 다시 발생하지 않는다는 것을 입증해야 한다.

산업용 근본 원인 분석(Industrial RCA)은 최종적으로 지속적인 엔지니어링 피드백 루프(Continuous Engineering Feedback Loop)의 일부가 되어야 한다. 각각의 사고 기록에는 고장 시그니처(Failure Signature), 증거 패키지(Evidence Package), 인과 사슬(Causal Chain), 확인된 근본 원인(Confirmed Root Cause), 시정 조치(Corrective Action), 검증 결과(Verification Result), 영향받은 버전(Affected Version), 교훈(Lessons Learned)을 검색 가능한 지식 기반(Searchable Knowledge Base)에 보존해야 한다. 이러한 기록을 축적하면 반복되는 고장 패턴을 발견할 수 있으며, 근본 원인 분석을 로그 패턴 마이닝(Log Pattern Mining), 인공지능 고장 개선(AI Failure Improvement), 다운타임 분석(Downtime Analysis), 예측 유지보수(Predictive Maintenance), 개발 피드백(Development Feedback)으로 직접 연결할 수 있다.

## 10.03. SW Failure Log Analysis and Pattern Mining [w/Code]

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

소프트웨어 고장 로그 분석(Software Failure Log Analysis)은 원시 운용 기록(Raw Operational Record)을 산업용 로봇이 어떻게 그리고 왜 오작동했는지를 설명할 수 있는 증거로 변환한다. 현대 로봇은 임베디드 제어기(Embedded Controller), 운영체제(Operating System), ROS 2 미들웨어(Middleware), 인식(Perception), 위치추정(Localization), 계획(Planning), 제어(Control), 안전(Safety), 플릿 관리(Fleet Management), 외부 서비스(External Service)에서 지속적으로 로그를 생성한다. 목표는 단순히 오류 메시지를 검색하는 것이 아니라 분산된 정보원에서 비정상 동작을 재구성하고 반복되는 고장 시그니처(Failure Signature)를 발견하는 것이다.

유용한 로깅 아키텍처(Logging Architecture)는 일관된 이벤트 구조(Event Structure)에서 시작한다. 각 기록에는 타임스탬프(Timestamp), 로봇 식별자(Robot Identifier), 소프트웨어 구성요소(Software Component), 프로세스 또는 노드(Process or Node), 심각도 수준(Severity Level), 이벤트 유형(Event Type), 메시지(Message), 임무 식별자(Mission Identifier), 소프트웨어 버전(Software Version), 관련 상태 변수(State Variable)가 포함되어야 한다. 구조화 형식(Structured Format)은 수천 개의 임무와 여러 로봇 플랫폼에서 발생한 이벤트를 수동 해석에만 의존하지 않고 필터링, 집계, 상관분석, 자동 처리할 수 있으므로 자유 형식 텍스트보다 적합하다.

분산 로그(Distributed Log)를 분석하기 전에 시간 정렬(Time Alignment)이 필수적이다. 장애물 감지 이벤트(Obstacle Detection Event), 위치추정 경고(Localization Warning), 플래너 시간 초과(Planner Timeout), 제어기 결함(Controller Fault), 안전 정지(Safety Stop)는 각각 시간이 조금씩 다른 별도의 프로세서에서 발생할 수 있다. 작은 타임스탬프 오류조차 결과가 원인보다 먼저 발생한 것처럼 보이게 만들 수 있다. 시계를 동기화하고 타임스탬프를 정규화하면 순서화된 이벤트 시퀀스(Event Sequence)를 구성하고 최초 이상에서 최종 로봇 고장까지의 전파 경로(Propagation Path)를 식별할 수 있다.

로그 전처리(Log Preprocessing)는 진단에 필요한 정보를 보존하면서 불필요한 잡음(Noise)을 제거한다. 반복적인 하트비트 메시지(Heartbeat Message), 정상 상태 업데이트(Status Update), 중복 경고(Duplicated Warning), 고주파 텔레메트리(High-Frequency Telemetry)는 의미 있는 이벤트를 압도할 수 있다. 파싱(Parsing), 필터링(Filtering), 중복 제거(Deduplication), 타임스탬프 정규화(Timestamp Normalization), 심각도 매핑(Severity Mapping), 구성요소 식별(Component Identification)을 통해 이질적인 로그를 공통 표현(Common Representation)으로 변환한다. 그러나 전처리 오류나 새롭게 발견된 가설을 원본 증거를 이용해 다시 조사할 수 있도록 원시 로그(Raw Log)는 변경 불가능한 상태로 보존해야 한다.

고장 분석(Failure Analysis)은 일반적으로 사고 발생 전후의 시간 구간(Time Window)을 중심으로 시작한다. 최종 예외(Exception)만 조사하는 대신 시스템은 고장 발생 수초 또는 수분 전후의 이벤트를 검색한다. 내비게이션 정지(Navigation Stop)의 경우 그 이전에 센서 시간 초과(Sensor Timeout), 위치추정 신뢰도 감소(Localization Confidence Degradation), 반복적인 재계획(Replanning), CPU 사용률 증가, 명령 지연(Command Latency), 최종적인 안전 상태 전이(Safety Transition)가 나타날 수 있다. 이러한 시간적 문맥(Temporal Context)은 최초 이상 현상과 시스템이 이미 성능 저하 상태에 진입한 이후 생성된 2차 오류(Secondary Error)를 구분하게 한다.

이벤트 상관분석(Event Correlation)은 동일한 인과 시퀀스(Causal Sequence)에 속하는 메시지를 연결한다. 임무 식별자(Mission ID), 요청 식별자(Request ID), ROS 2 토픽(Topic), 노드 이름(Node Name), 장치 식별자(Device Identifier), 로봇 식별자(Robot ID), 타임스탬프를 사용하여 분산 이벤트를 연계할 수 있다. 하나의 하위 시스템에서 발생한 경고가 다른 하위 시스템의 상태 변경을 유발하는 경우 상관분석은 특히 중요하다. 이렇게 생성된 이벤트 체인(Event Chain)은 개별 로그 라인보다 강력한 진단 증거를 제공하며 근본 원인 분석(Root Cause Analysis, RCA)에서 생성된 인과 가설(Causal Hypothesis)과 직접 비교할 수 있다.

패턴 마이닝(Pattern Mining)은 개별 사고 분석을 대규모 운용 이력(Operational History)으로 확장한다. 센서 경고(Sensor Warning) → 위치추정 성능 저하(Localization Degradation) → 플래너 복구(Planner Recovery) → 안전 정지(Safety Stop)와 같이 반복되는 시퀀스를 고장 시그니처(Failure Signature)로 표현할 수 있다. 시퀀스 마이닝(Sequence Mining), 빈발 패턴 탐색(Frequent-Pattern Discovery), 클러스터링(Clustering), 통계적 집계(Statistical Aggregation)를 통해 알려진 고장 이전에 반복적으로 나타나는 이벤트 조합을 식별할 수 있다. 이러한 패턴은 개별 사고를 따로 조사할 때 쉽게 발견하기 어려운 관계를 엔지니어링 팀이 찾도록 지원한다.

템플릿 추출(Template Extraction)은 수백만 개의 텍스트 로그 메시지를 관리 가능한 이벤트 클래스(Event Class)로 축소할 수 있다. 타임스탬프, 좌표(Coordinate), 객체 식별자(Object ID), 메모리 주소(Memory Address), 수치 측정값(Numerical Measurement)과 같은 가변 요소를 각 메시지의 안정적인 구조에서 분리한다. 반복되는 플래너 시간 초과 보고와 같은 메시지는 파라미터를 이후 분석을 위해 유지하면서 공통 템플릿(Common Template)으로 그룹화할 수 있다. 템플릿 빈도(Template Frequency)와 전이(Transition)는 로봇 소프트웨어 동작을 간결하게 표현할 수 있는 수단을 제공한다.

클러스터링(Clustering)은 고장 범주(Failure Category)가 아직 정의되지 않은 경우 유용하다. 사고를 이벤트 빈도(Event Frequency), 로그 템플릿(Log Template), 시간적 시퀀스(Temporal Sequence), 하위 시스템 상태(Subsystem State), 학습된 임베딩(Learned Embedding)을 이용해 표현하고 유사성(Similarity)에 따라 그룹화할 수 있다. 하나의 클러스터는 위치추정 고장, 다른 클러스터는 네트워크 중단(Network Interruption), 또 다른 클러스터는 자원 고갈(Resource Exhaustion)을 나타낼 수 있다. 엔지니어는 각 클러스터의 대표 사례를 검토하고 반복되는 그룹을 공식적인 고장 클래스(Failure Class), 진단 규칙(Diagnostic Rule), 회귀 시험(Regression Test)으로 변환할 수 있다.

이상 탐지(Anomaly Detection)는 고장 시그니처가 드물거나 이전에 알려지지 않은 경우를 처리한다. 정상 임무(Normal Mission)의 이벤트 발생률(Event Rate), 지연시간 분포(Latency Distribution), CPU 및 메모리 동작, 경고 빈도(Warning Frequency), 메시지 타이밍(Message Timing), 상태 전이 패턴(State-Transition Pattern)을 이용하여 기준선(Baseline)을 학습할 수 있다. 명시적인 오류가 보고되지 않더라도 이 기준선에서 크게 벗어나는 현상은 소프트웨어 성능 저하(Software Degradation)의 시작을 나타낼 수 있다. 이는 유지보수 담당자가 재현하기 전에 사라지는 간헐적 결함(Intermittent Fault)을 탐지하는 데 특히 유용하다.

많은 고장은 점진적으로 발생하므로 소프트웨어 자원 지표(Software Resource Metric)를 이벤트 로그와 연계해야 한다. 증가하는 메모리 사용량(Memory Consumption)은 메모리 부족 종료(Out-of-Memory Termination)에 앞서 나타날 수 있고, CPU 포화(CPU Saturation)는 마감시간 누락(Missed Deadline)을 발생시킬 수 있다. 저장공간 고갈(Storage Exhaustion)은 로깅이나 지도 업데이트를 방해할 수 있으며 과도한 GPU 사용률은 인공지능 추론(AI Inference)을 지연시킬 수 있다. 자원 텔레메트리(Resource Telemetry)와 애플리케이션 이벤트를 결합하면 기능 알고리즘 오류와 동일한 외부 증상을 유발하는 인프라 또는 성능 저하를 구분할 수 있다.

분산 미들웨어(Distributed Middleware)는 통신 고장이 애플리케이션 고장처럼 나타나는 경우가 많으므로 추가적인 분석이 필요하다. ROS 2 탐색 변경(Discovery Change), DDS 메시지 손실(Message Loss), 서비스 품질 불일치(Quality of Service Mismatch), 토픽 지연시간(Topic Latency), 서비스 사용 불가(Unavailable Service), 생명주기 전이(Lifecycle Transition)는 관련 노드가 충돌하지 않더라도 데이터 흐름을 중단시킬 수 있다. 따라서 로그 분석은 애플리케이션 상태와 함께 통신 상태(Communication State)를 재구성하여 센서 데이터 누락을 보고한 플래너가 최초 고장의 원인 구성요소로 잘못 식별되지 않도록 해야 한다.

플릿(Fleet) 전체의 고장을 마이닝할 때 버전 정보(Version Information)는 매우 중요하다. 모든 사고는 가능한 경우 소프트웨어 릴리스(Software Release), 펌웨어 버전(Firmware Version), 설정 리비전(Configuration Revision), 인공지능 모델 버전(AI Model Version), 지도 버전(Map Version), 배포 시점(Deployment Timestamp)과 연결되어야 한다. 이를 통해 업데이트 전후의 고장률(Failure Rate)을 비교할 수 있다. 특정 고장 시그니처가 릴리스 직후 증가한다면 해당 변경 집합(Change Set)은 중요한 진단 후보가 되며 롤백(Rollback)이나 회귀 시험(Regression Testing) 절차와 연결할 수 있다.

플릿 규모 집계(Fleet-Scale Aggregation)는 개별 로봇의 고장을 운용 신뢰성 지식(Operational Reliability Knowledge)으로 변환한다. 로봇마다 운용 시간이나 임무 수행량이 다를 수 있으므로 단순한 고장 횟수만으로는 충분하지 않다. 따라서 고장 빈도는 운용 시간(Operating Hours), 이동 거리(Distance), 임무 수(Missions), 조작 사이클(Manipulation Cycles) 또는 적절한 노출량(Exposure Measure)을 기준으로 정규화해야 한다. 로봇, 사이트(Site), 하드웨어 리비전(Hardware Revision), 소프트웨어 버전, 환경 조건, 임무 유형별 정규화 고장률을 비교하면 문제가 개별적인지 시스템 전체에 걸친 것인지 파악할 수 있다.

시각화(Visualization)와 자동 요약(Automated Summary)은 마이닝된 패턴을 엔지니어와 작업자가 실제로 활용할 수 있는 정보로 만든다. 타임라인(Timeline)은 이벤트 전파를 보여주고, 히트맵(Heat Map)은 구성요소 사이의 관계를 나타내며, 추세 화면(Trend View)은 고장 발생 전 증가하는 경고 빈도를 보여줄 수 있다. 더욱 중요한 것은 분석 시스템이 각각의 패턴을 대표 원시 증거(Representative Raw Evidence), 영향받은 로봇(Affected Robot), 재발 빈도(Recurrence Frequency), 운용 영향(Operational Impact), 기존에 확인된 근본 원인 분석(RCA) 기록과 연결하여 통계적 연관성(Statistical Association)이 입증된 인과관계로 잘못 해석되지 않도록 하는 것이다.

최종 목표는 고장 로그(Failure Log)를 지속적으로 개선되는 진단 지식 기반(Diagnostic Knowledge Base)으로 변환하는 것이다. 확인된 시그니처는 모니터링 규칙(Monitoring Rule), 경보(Alert), 자동 트리아지 로직(Automated Triage Logic), 회귀 시험(Regression Test), 예측 특징(Predictive Feature)으로 전환할 수 있다. 새로운 사고는 알려진 패턴과 비교하고 일치하지 않는 사례는 심층 조사로 전달한다. 이를 통해 현장 운용(Field Operation), 근본 원인 분석(RCA), 소프트웨어 개발(Software Development), 검증(Validation), 후속 예측 고장 탐지(Predictive Failure Detection)를 산업 고장 분석(Industrial Failure Analysis)의 전체 과정 안에서 하나의 폐쇄 루프(Closed Loop)로 연결할 수 있다.

## 10.04. AI Perception Failure Analysis and Improvement [w/Code]

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

인공지능 인식 고장(AI Perception Failure)은 인식 파이프라인(Perception Pipeline)이 정상적으로 실행되면서도 물리적 환경에 대한 잘못된 해석을 생성할 수 있다는 점에서 기존 소프트웨어 고장(Software Failure)과 다르다. 객체 탐지기(Object Detector), 세그멘테이션 네트워크(Segmentation Network), 자세 추정기(Pose Estimator), 깊이 모델(Depth Model), 추적 시스템(Tracking System), 센서 융합 알고리즘(Sensor-Fusion Algorithm)은 문법적으로 유효하지만 운용 관점에서는 잘못된 결과를 반환할 수 있다. 따라서 고장 분석은 연산 상태(Computational Health)와 인식 결과의 의미적 정확성(Semantic Correctness)을 함께 평가해야 한다.

효과적인 분석은 인식 고장 형태(Perception Failure Mode)를 정확하게 정의하는 것에서 시작한다. 대표적인 형태에는 미탐(False Negative), 오탐(False Positive), 잘못된 분류(Incorrect Classification), 부정확한 바운딩 박스(Inaccurate Bounding Box), 세그멘테이션 오류(Segmentation Error), 깊이 추정 오류(Depth Estimation Error), 자세 오류(Pose Error), 추적 손실(Track Loss), 식별자 전환(Identity Switch), 잘못된 자유 공간 또는 점유 영역 추정(Free-Space or Occupancy Estimation)이 포함된다. 각 고장은 로봇 상태, 센서 입력, 환경 조건, 모델 버전, 신뢰도 값(Confidence Value), 잘못된 출력의 영향을 받은 후속 의사결정(Downstream Decision)과 연결되어야 한다.

미탐(False Negative)은 관련 객체가 환경에 실제로 존재하면서도 인식 결과에 나타나지 않을 수 있기 때문에 안전 측면에서 특히 중요하다. 작은 객체(Small Object), 원거리 대상(Distant Target), 부분 가림(Partial Occlusion), 모션 블러(Motion Blur), 비정상적인 시점(Unusual Viewpoint), 낮은 조도(Poor Illumination), 낮은 센서 해상도(Low Sensor Resolution)는 미탐 가능성을 증가시킨다. 분석에서는 객체가 센서 데이터 자체에 존재하지 않았는지, 전처리(Preprocessing) 과정에서 손실되었는지, 학습 데이터에서 충분히 표현되지 않았는지, 또는 신뢰도 및 후처리 임계값(Post-Processing Threshold)에 의해 제거되었는지를 판단해야 한다.

오탐(False Positive)은 다른 형태의 운용 문제를 발생시킨다. 반사(Reflection), 그림자(Shadow), 식생(Vegetation), 구조적 패턴(Structural Pattern), 센서 잡음(Sensor Noise), 익숙하지 않은 객체(Unfamiliar Object)가 장애물이나 특정 대상 클래스로 잘못 해석될 수 있다. 자율이동로봇(AMR)에서 반복적인 가짜 장애물(False Obstacle)은 불필요한 제동(Braking), 재계획(Replanning), 진동 동작(Oscillation), 임무 지연(Mission Delay)을 발생시킬 수 있다. 따라서 엔지니어링 목표는 단순히 탐지 정확도(Detection Accuracy)를 최대화하는 것이 아니라 인식 오류가 내비게이션, 조작, 안전, 생산 성능으로 어떻게 전파되는지를 이해하는 것이다.

중요한 인식 사고(Perception Incident)가 발생할 때마다 환경 문맥(Environmental Context)을 함께 기록해야 한다. 조도(Illumination), 비(Rain), 안개(Fog), 먼지(Dust), 눈부심(Glare), 반사 표면(Reflective Surface), 카메라 오염(Camera Contamination), 진동(Vibration), 온도(Temperature), 동적 혼잡(Dynamic Crowding)은 센서 특성을 크게 변화시킬 수 있다. 환경 속성(Environmental Attribute)에 따라 고장을 비교하면 개별적인 모델 오류와 체계적인 운용 영역 취약점(Operating-Domain Weakness)을 구분할 수 있으며 검증 데이터셋(Validation Dataset)에 더욱 강하게 반영해야 할 조건을 식별할 수 있다.

인공지능 모델(AI Model)에 대한 결론을 내리기 전에 센서 수준 분석(Sensor-Level Analysis)을 수행해야 한다. 성능이 저하된 카메라, 잘못된 노출(Incorrect Exposure), 라이다 오염(LiDAR Contamination), 동기화 오류(Synchronization Error), 캘리브레이션 드리프트(Calibration Drift), 패킷 손실(Packet Loss), 불안정한 센서 장착(Unstable Sensor Mounting)은 예상 분포(Expected Distribution)를 벗어난 입력을 생성할 수 있다. 이러한 문제를 모델 오류와 구분하지 않으면 실제 원인이 아니었던 신경망을 불필요하게 재학습할 수 있으므로 센서 상태 지표(Sensor Health Indicator)와 원시 데이터(Raw Data)를 인공지능 추론 기록과 함께 보존해야 한다.

전처리(Preprocessing)와 후처리(Post-Processing) 역시 잠재적인 고장 원인이 될 수 있다. 이미지 크기 조정(Image Resizing), 정규화(Normalization), 좌표 변환(Coordinate Transformation), 포인트 클라우드 필터링(Point-Cloud Filtering), 관심 영역 자르기(Region Cropping), 비최대 억제(Non-Maximum Suppression), 신뢰도 임계값(Confidence Threshold), 클래스 매핑(Class Mapping)은 정상적인 모델 출력을 변경할 수 있다. 오프라인 재생(Offline Replay)은 신경망만 시험하는 것이 아니라 전체 추론 파이프라인(Inference Pipeline)을 재현해야 하며, 이를 통해 불일치가 모델 이전, 모델 내부 또는 모델 이후 어느 단계에서 발생했는지를 식별할 수 있다.

데이터셋 분석(Dataset Analysis)은 인식 성능 개선의 핵심이다. 고장 샘플(Failure Sample)을 학습 및 검증 데이터 분포와 비교하여 유사한 객체, 시점(Viewpoint), 거리(Distance), 조명 조건(Lighting Condition), 배경(Background), 센서 특성이 충분히 표현되었는지를 확인해야 한다. 희귀 사건의 과소 표현(Rare-Event Underrepresentation), 어노테이션 오류(Annotation Error), 클래스 불균형(Class Imbalance), 지리적 편향(Geographic Bias), 부족한 네거티브 예제(Negative Example)는 전체 벤치마크 지표가 양호하더라도 숨겨진 체계적 취약점을 발생시킬 수 있다.

분포 이동(Distribution Shift)은 현장 데이터(Field Data)가 모델 개발 과정에서 표현된 조건과 달라질 때 발생한다. 깨끗한 창고에서 학습된 모델은 먼지가 많은 공장, 야외 작업장, 건설 현장, 농장, 항만 또는 날씨가 지속적으로 변화하는 환경에서 성능이 저하될 수 있다. 입력 통계(Input Statistics), 특징 분포(Feature Distribution), 신뢰도 패턴(Confidence Pattern), 고장률(Failure Rate)을 모니터링하면 이러한 변화를 탐지할 수 있다. 따라서 현장 고장은 단순한 유지보수 사고로 남겨두지 않고 새로운 데이터를 확보하기 위한 통제된 데이터 소스(Controlled Data Source)로 활용해야 한다.

신뢰도 보정(Confidence Calibration)은 신경망의 원시 신뢰도가 실제 정답 확률을 반드시 의미하지 않기 때문에 중요하다. 모델이 잘못된 예측에 높은 신뢰도를 부여할 경우 단순한 임계값 기반 안전 로직(Threshold-Based Safety Logic)은 신뢰하기 어렵다. 보정 분석(Calibration Analysis)은 클래스와 운용 조건별로 예측 신뢰도(Predicted Confidence)와 실제 정확도(Observed Accuracy)를 비교한다. 보정 성능이 낮은 영역은 임계값 조정, 모델 보정(Model Calibration), 불확실성 추정(Uncertainty Estimation), 추가 센싱(Additional Sensing), 추가 검증을 통해 개선할 수 있다.

시간적 일관성(Temporal Consistency)은 또 다른 중요한 진단 증거를 제공한다. 물리적 객체는 일반적으로 연속된 프레임에서 지속적으로 존재하지만 일시적인 인식 오류는 짧게 나타난 후 사라질 수 있다. 추적(Tracking)과 시간적 필터링(Temporal Filtering)은 순간적인 오탐을 억제할 수 있지만 잘못된 탐지를 시간적으로 계속 전파할 수도 있다. 따라서 고장 분석에서는 개별 이미지만 독립적으로 평가하기보다 프레임 수준 예측(Frame-Level Prediction), 트랙(Track), 객체 이력(Object History), 운동 추정(Motion Estimation), 상태 전이(State Transition)를 함께 분석해야 한다.

다중 센서 융합(Multi-Sensor Fusion)은 서로 다른 센싱 모달리티(Sensing Modality)가 상호 보완적인 고장 특성을 가질 때 강건성(Robustness)을 향상시킬 수 있다. 카메라는 풍부한 의미 정보를 제공하지만 조명에 민감하고, 라이다(LiDAR)는 서로 다른 한계를 가지면서 기하학적 측정값을 제공한다. 레이더(Radar), 깊이 센서(Depth Sensor), 관성측정장치(IMU) 등도 추가적인 증거를 제공할 수 있다. 그러나 잘못된 캘리브레이션, 동기화, 가중치(Weighting), 데이터 연관(Data Association)은 개별적으로 정상적인 센서 측정값을 잘못된 융합 결과로 변환할 수 있으므로 센서 융합 고장도 면밀하게 분석해야 한다.

개선(Improvement)은 무분별한 재학습(Retraining)이 아니라 분류된 고장 증거(Categorized Failure Evidence)를 기반으로 수행해야 한다. 어려운 사례(Hard Example)를 학습 데이터에 추가하고, 어노테이션 오류를 수정하며, 클래스 균형을 개선하고, 데이터 증강(Data Augmentation)을 확대하거나 임계값을 재보정하고, 전처리 또는 모델 아키텍처(Model Architecture)를 변경할 수 있다. 일부 문제는 센서 재설계(Sensor Redesign), 추가 센싱, 시간적 추론(Temporal Reasoning), 안전 로직(Safety Logic)을 통해 해결하는 것이 더 적절할 수 있으므로 시정 조치(Corrective Action)는 검증된 고장 메커니즘에 직접 대응해야 한다.

개선 이후의 평가(Evaluation)는 변경을 유발한 고장 조건을 반드시 재현해야 한다. 정밀도(Precision), 재현율(Recall), 교집합 대비 합집합(Intersection over Union, IoU), 평균 정밀도(Average Precision, AP), 자세 오차(Pose Error), 추적 정확도(Tracking Accuracy)와 같은 표준 검증 지표는 여전히 유용하지만 시나리오별 시험(Scenario-Specific Test)을 함께 수행해야 한다. 예를 들어 저조도 운용을 개선한 모델은 통제된 여러 조도 수준에서 평가해야 하며 동시에 정상 조건에서 성능 회귀(Performance Regression)가 발생하지 않았는지도 확인해야 한다.

인식 고장은 후속 운용 위험(Downstream Operational Risk)에 따라서도 평가해야 한다. 멀리 떨어진 무해한 객체를 놓치는 것과 로봇 이동 경로 근처의 사람을 놓치는 것은 동일한 결과가 아니다. 마찬가지로 작은 자세 오차는 내비게이션에는 문제가 없을 수 있지만 정밀 삽입(Precision Insertion) 작업에서는 허용할 수 없을 수 있다. 따라서 고장 우선순위(Failure Prioritization)는 인공지능 성능 지표와 함께 객체 중요도(Object Relevance), 거리, 로봇 속도(Robot Speed), 작업 단계(Task Phase), 안전 결과(Safety Consequence), 후속 시스템의 복구 능력(Recovery Capability)을 종합하여 결정해야 한다.

배포(Deployment) 이후에도 인식 품질은 변화할 수 있으므로 지속적인 모니터링(Continuous Monitoring)이 필요하다. 모델 버전, 센서 리비전(Sensor Revision), 환경 조건, 신뢰도 분포(Confidence Distribution), 개입 이벤트(Intervention Event), 현장 고장률(Field Failure Rate)을 전체 로봇 플릿에 걸쳐 추적해야 한다. 새롭게 발견된 고장 사례는 검토를 위해 자동 수집하고, 오프라인에서 재현하며, 회귀 데이터셋(Regression Dataset)에 포함하여 모델 업데이트가 여러 사이트와 운용 조건에서 실제로 신뢰성을 향상시키는지를 판단해야 한다.

이러한 과정은 현장 운용(Field Operation), 고장 로깅(Failure Logging), 근본 원인 분석(Root Cause Analysis, RCA), 데이터셋 큐레이션(Dataset Curation), 모델 학습(Model Training), 검증(Validation), 배포(Deployment), 모니터링(Monitoring)을 연결하는 폐쇄형 인식 개선 루프(Closed Perception Improvement Loop)를 형성한다. 잘못된 인공지능 예측을 개별적인 모델 결함으로만 취급하는 대신 조직은 고장 시나리오(Failure Scenario)와 검증된 시정 조치의 라이브러리를 지속적으로 구축한다. 이를 통해 실제 산업 현장에서 축적된 경험을 점차 더 강건한 인식 모델(Robust Perception Model)과 더욱 안전한 로봇 동작으로 전환할 수 있다.

## 10.05. Navigation Failure Stuck Deadlock Analysis [w/Code]

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

산업용 로봇(Industrial Robot)의 내비게이션 고장(Navigation Failure)은 단일 내비게이션 알고리즘만의 문제로 발생하는 경우가 드물다. 자율이동로봇(AMR)은 위치추정(Localization), 경로 계획(Path Planning), 모터 제어(Motor Control)가 각각 정상적으로 동작하는 상황에서도 정지할 수 있다. 고장은 인식(Perception), 지도(Map), 위치추정, 전역 계획(Global Planning), 지역 계획(Local Planning), 장애물 회피(Obstacle Avoidance), 제어(Control), 교통 관리(Traffic Management), 인프라(Infrastructure) 사이의 상호작용에서 발생한다. 따라서 분석에서는 로봇을 단순히 고착(Stuck) 또는 교착(Deadlock) 상태로 분류하기 전에 전체 내비게이션 상태를 재구성해야 한다.

고착 상태(Stuck Condition)는 로봇이 내비게이션 기능을 계속 실행하고 있음에도 할당된 목표를 향해 의미 있는 진행을 하지 못하는 상태를 의미한다. 로봇이 작은 전진 및 후진 동작을 반복하거나, 탈출하지 못한 채 회전하거나, 재계획(Replanning)을 수행하면서 정지 상태를 유지하거나, 사용 가능한 궤적(Trajectory)을 지속적으로 거부할 수 있다. 고착 탐지는 단순히 차량 속도가 0인지 확인하는 것보다 명령 속도(Commanded Velocity), 측정 속도(Measured Velocity), 변위(Displacement), 목표 거리 감소(Goal-Distance Reduction), 플래너 동작(Planner Activity), 장애물 상태(Obstacle State), 경과 시간(Elapsed Time)을 종합적으로 고려해야 한다.

고착 동작의 물리적 원인에는 휠 슬립(Wheel Slip), 불충분한 접지력(Insufficient Traction), 캐스터 간섭(Caster Interference), 적재하중에 따른 이동성 제한(Payload-Related Mobility Limitation), 바닥 불규칙성(Floor Irregularity), 기계적 접촉(Mechanical Contact), 좁은 여유 공간(Narrow Clearance), 센서 시야 아래에 존재하는 장애물이 포함된다. 로봇의 회전 반경(Turning Radius)이 주변 공간의 기하학적 구조와 맞지 않을 때도 물리적으로 구속될 수 있다. 따라서 내비게이션 분석에서는 소프트웨어 상태를 휠 속도, 모터 전류, 오도메트리(Odometry), 관성측정장치(IMU) 측정값, 조향 상태(Steering State), 환경 관측(Environmental Observation)과 연계해야 한다.

위치추정 고장(Localization Failure)은 물리적으로 움직이지 못하는 상태와 유사한 증상을 발생시킬 수 있다. 라이다(LiDAR) 또는 비전 기반 위치추정(Visual Localization)은 반복적인 구조(Repetitive Structure), 특징이 부족한 복도(Feature-Poor Corridor), 반사 표면(Reflective Surface), 변화하는 환경, 센서 오염(Sensor Contamination), 캘리브레이션 드리프트(Calibration Drift), 지도 불일치(Map Inconsistency)로 인해 불안정해질 수 있다. 갑작스러운 자세 점프(Pose Jump) 또는 증가하는 위치추정 불확실성(Localization Uncertainty)은 실제 이동 경로가 비어 있어도 플래너가 궤적을 거부하거나 안전 로직(Safety Logic)이 이동을 정지시키도록 만들 수 있다. 따라서 모든 사고에서 자세 이력(Pose History)과 위치추정 신뢰도(Localization Confidence)를 보존해야 한다.

지도 관련 고장(Map-Related Failure)은 내비게이션 표현(Navigation Representation)이 실제 물리적 환경과 크게 다를 때 발생한다. 임시 장비(Temporary Equipment), 팔레트(Pallet), 공사로 인한 변경, 잘못 모델링된 벽, 오래된 진입 금지 영역(Keep-Out Zone), 부정확한 인플레이션 파라미터(Inflation Parameter)는 유효한 경로를 사용할 수 없게 만들 수 있다. 반대로 누락된 장애물은 플래너가 물리적으로 실행할 수 없는 경로를 생성하게 만들 수 있다. 특정 위치에서 반복되는 고장을 진단할 때는 운용 지도(Operational Map), 로컬 코스트맵(Local Costmap), 센서 관측, 실제 현장 상태를 비교하는 것이 필수적이다.

전역 계획 고장(Global Planning Failure)은 시스템이 현재 자세에서 목표까지 실행 가능한 경로를 생성할 수 없을 때 발생한다. 연결되지 않은 지도 영역(Disconnected Map Region), 과도한 장애물 인플레이션(Obstacle Inflation), 잘못된 목표 위치(Invalid Goal Position), 제한 구역(Restricted Zone), 잘못된 차량 풋프린트(Vehicle Footprint) 파라미터, 그래프 연결성 오류(Graph Connectivity Error)는 목적지를 수학적으로 도달 불가능하게 만들 수 있다. 반복적인 플래너 재시도는 토폴로지(Topology) 또는 설정 문제를 해결할 수 없으므로 분석에서는 실제 경로 실행 불가능성과 알고리즘 자체의 계획 실패를 구분해야 한다.

지역 계획 고장(Local Planning Failure)은 유효한 전역 경로가 존재하지만 로봇이 안전한 단기 이동(Short-Horizon Motion)을 생성하지 못할 때 발생한다. 동적 장애물(Dynamic Obstacle), 좁은 통로(Narrow Passage), 과도한 안전 마진(Safety Margin), 부정확한 속도 제한(Velocity Limit), 잘못된 궤적 평가(Trajectory Scoring), 상충되는 목적 함수(Conflicting Objective)는 반복적인 궤적 거부를 발생시킬 수 있다. 로봇은 전진하지 못한 채 대체 동작 사이에서 진동(Oscillation)할 수 있다. 후보 궤적(Candidate Trajectory), 비용 값(Cost Value), 장애물 거리, 명령 속도, 복구 상태 전이(Recovery Transition)를 분석하면 지역 이동이 반복적으로 실패한 이유를 확인할 수 있다.

복구 동작(Recovery Behavior) 자체가 지속적인 내비게이션 고장을 발생시킬 수도 있다. 코스트맵 초기화(Costmap Clearing), 제자리 회전(Rotation in Place), 후진(Backing Away), 재계획, 작업자 지원 요청은 일시적인 장애를 복구할 수 있지만 반복적인 복구 사이클(Recovery Cycle)은 시스템을 무한히 갇힌 상태로 만들 수 있다. 분석에서는 복구 유형(Recovery Type), 진입 조건(Entry Condition), 지속시간(Duration), 결과(Result), 반복 횟수(Repetition Count)를 기록해야 한다. 제한된 복구 정책(Bounded Recovery Policy)은 플릿 가용성(Fleet Availability)을 감소시키는 무한한 자율 복구 시도를 허용하는 대신 일정 조건 이후 사고를 상위 단계로 에스컬레이션(Escalation)해야 한다.

교착(Deadlock)은 여러 로봇 또는 공유 자원(Shared Resource) 사이의 상호 의존성(Mutual Dependency) 때문에 진행이 차단된다는 점에서 일반적인 고착 상태와 다르다. 좁은 통로에서 서로 마주 보는 두 로봇이 상대방이 먼저 이동하기를 기다릴 수 있다. 더 복잡한 교착은 여러 로봇이 경로 구간(Route Segment), 교차로(Intersection), 엘리베이터(Elevator), 자동문(Door), 충전소(Charging Station), 상하차 위치(Loading Position)를 점유하면서 다른 로봇이 보유한 자원을 기다리는 상황에서 발생할 수 있다. 이 경우 개별 로봇 자체에는 지역 내비게이션 결함이 존재하지 않을 수도 있다.

따라서 플릿 수준 교착 분석(Fleet-Level Deadlock Analysis)은 자원 소유(Resource Ownership)와 대기 관계(Waiting Relationship)를 재구성해야 한다. 교통 예약(Traffic Reservation), 경로 잠금(Route Lock), 교차로 상태(Intersection State), 임무 우선순위(Mission Priority), 로봇 위치, 대기 중인 요청(Pending Request)을 대기 관계(Wait-For Relationship)로 표현할 수 있다. 순환 구조(Cycle)가 존재한다면 각 참여자가 동일한 의존성 체인(Dependency Chain) 안에서 다른 참여자를 기다리고 있음을 의미한다. 이러한 구조를 식별하는 것이 개별 로봇 오류 로그만으로 문제를 진단하는 것보다 신뢰성이 높다.

교통 혼잡(Traffic Congestion) 역시 교착과 구분해야 한다. 혼잡 상태에서는 처리량(Throughput)과 이동 시간(Travel Time)이 크게 악화되더라도 로봇은 계속 진행한다. 반면 교착에서는 시스템이 자원 할당을 변경하거나 강제적인 복구 조치를 수행하지 않는 한 의존 관계 때문에 진행할 수 없다. 그러나 지속적인 혼잡은 대기열(Queue)이 핵심 교차로를 점유하거나 로봇이 예약 자원을 해제하지 못하게 하면서 교착으로 발전할 수 있으므로 플릿 전체의 시간적 분석(Temporal Analysis)이 중요하다.

통신 고장(Communication Failure)은 외관상 내비게이션 또는 교착과 유사한 증상을 발생시킬 수 있다. 지연된 플릿 명령(Fleet Command), 손실된 예약 업데이트(Reservation Update), 오래된 로봇 위치 정보(Stale Robot Position), 미들웨어 중단(Middleware Interruption), 네트워크 혼잡(Network Congestion), 서버 사용 불가(Server Unavailability)는 로봇이 도착하지 않는 승인이나 명령을 계속 기다리게 할 수 있다. 사고를 계획 알고리즘(Planning Algorithm)의 문제로 판단하기 전에 내비게이션 로그를 네트워크 지연시간(Network Latency), 메시지 손실(Message Loss), 플릿 서버 이벤트(Fleet-Server Event), 예약 타임스탬프(Reservation Timestamp), 통신 상태와 연계하여 분석해야 한다.

고착 및 교착 탐지(Stuck and Deadlock Detection)는 명시적인 운용 임계값(Operational Threshold)을 사용해야 한다. 진행 상태(Progress)는 변위, 목표까지의 거리 감소, 웨이포인트(Waypoint) 완료, 정의된 시간 내 예약 자원 해제 여부 등을 통해 측정할 수 있다. 임계값은 임무 유형(Mission Type), 로봇 크기(Robot Size), 예상 대기 동작(Expected Waiting Behavior), 교통 밀도(Traffic Density), 환경 조건을 고려해야 한다. 지나치게 민감한 탐지기는 불필요한 복구를 발생시키며, 둔감한 탐지기는 로봇이 핵심 자원을 지나치게 오랫동안 점유하도록 만든다.

근본 원인 분석(Root Cause Analysis, RCA)은 최종 내비게이션 시간 초과(Navigation Timeout)를 원인으로 취급하는 대신 최초의 비정상 조건에서부터 사고를 재구성해야 한다. 차단된 통로(Blocked Aisle)는 지역 재계획(Local Replanning), 경로 예약 변경(Route Reservation Change), 대기열 형성(Queue Formation), 상호 대기(Mutual Waiting)를 순차적으로 발생시켜 최종적으로 플릿 전체의 교착으로 이어질 수 있다. 마지막 로봇은 단순히 목표 시간 초과(Goal Timeout)만 보고할 수 있다. 내비게이션 로그, 지도, 텔레메트리(Telemetry), 인식 기록, 플릿 이벤트를 결합하면 이러한 전파 사슬(Propagation Chain)을 확인하고 최초 원인과 2차 결과(Secondary Consequence)를 구분할 수 있다.

시정 조치(Corrective Action)는 검증된 고장 메커니즘에 따라 달라져야 한다. 물리적 고착은 기계적 변경(Mechanical Modification)이나 지형 대응 능력(Terrain Handling)의 개선이 필요할 수 있으며, 위치추정 고장은 지도 업데이트(Map Update), 센서 유지보수(Sensor Maintenance), 센서 융합 개선(Fusion Improvement)이 필요할 수 있다. 계획 고장은 파라미터 또는 알고리즘 변경이 필요하고, 플릿 교착은 예약 시스템 재설계(Reservation Redesign), 우선순위 규칙(Priority Rule), 경로 재설정(Rerouting), 자원 선점(Resource Preemption), 전용 탈출 전략(Escape Strategy)이 필요할 수 있다. 복구는 단순한 내비게이션 재시작이 아니라 실제 인과 메커니즘을 해결해야 한다.

검증(Validation)에서는 대표적인 고착, 혼잡, 교착 시나리오를 의도적으로 재현해야 한다. 시험에는 차단된 복도(Blocked Corridor), 좁은 통로, 임시 장애물(Temporary Obstacle), 위치추정 성능 저하(Localization Degradation), 통신 지연(Communication Delay), 서로 마주 보는 로봇, 교차로 경합(Intersection Contention), 자원 충돌(Resource Conflict)이 포함되어야 한다. 성공 여부는 최종적인 임무 완료 여부뿐 아니라 탐지 시간(Detection Time), 복구 시간(Recovery Time), 불필요한 개입 비율(Unnecessary Intervention Rate), 안전 동작(Safety Behavior), 전체 플릿 처리량에 미치는 영향을 기준으로 측정해야 한다.

현장 사고(Field Incident)는 최종적으로 지속적으로 확장되는 내비게이션 고장 지식 기반(Navigation Failure Knowledge Base)에 반영되어야 한다. 각 사례에는 위치(Location), 지도 버전(Map Version), 로봇 구성(Robot Configuration), 교통 상태(Traffic State), 고장 시그니처(Failure Signature), 인과 사슬(Causal Chain), 복구 결과(Recovery Result), 검증된 시정 조치(Verified Corrective Action)를 보존할 수 있다. 반복되는 공간적 또는 시간적 패턴(Spatial or Temporal Pattern)을 통해 문제가 있는 지도 영역, 파라미터, 인프라 또는 교통 정책(Traffic Policy)을 식별할 수 있다. 이를 통해 내비게이션 운용, 고장 분석, 근본 원인 분석(RCA), 검증, 플릿 최적화(Fleet Optimization)를 하나의 폐쇄 루프(Closed Loop)로 연결할 수 있다.

## 10.06. Manipulation Failure Drop Miss Analysis [w/Code]

![](images/image6.png){width="7.268055555555556in" height="7.268055555555556in"}

조작 고장(Manipulation Failure)은 전체 작업 명령이 유효함에도 로봇이 객체와의 물리적 상호작용(Physical Interaction)을 안정적으로 완료하지 못할 때 발생한다. 대표적인 고장에는 파지 실패(Missed Grasping), 객체 낙하(Object Dropping), 불안정한 파지(Unstable Holding), 부정확한 배치(Inaccurate Placement), 삽입 실패(Insertion Failure), 충돌(Collision), 과도한 접촉력(Excessive Contact Force), 불완전한 해제(Incomplete Release)가 포함된다. 조작은 인식(Perception), 동작 계획(Motion Planning), 제어(Control), 기계 시스템(Mechanics), 객체 물리 특성(Object Physics)을 결합하므로 고장 분석에서는 최종 그리퍼 상태만 조사하는 것이 아니라 전체 상호작용 과정을 재구성해야 한다.

미스(Miss)는 엔드 이펙터(End Effector)가 의도한 접촉 또는 파지를 형성하지 못할 때 발생한다. 원인은 잘못된 객체 탐지(Object Detection), 부정확한 자세 추정(Pose Estimation), 캘리브레이션 오류(Calibration Error), 로봇 기구학 오차(Robot Kinematic Error), 궤적 편차(Trajectory Deviation), 객체 이동(Object Motion), 부적절한 파지 형상(Grasp Geometry)에서 발생할 수 있다. 분석에서는 추정된 객체 자세(Estimated Object Pose), 명령된 엔드 이펙터 자세(Commanded End-Effector Pose), 측정된 로봇 자세(Measured Robot Pose), 접촉 상태(Contact State), 실제 객체 위치(Actual Object Location)를 비교하여 조작 파이프라인에서 공간적 오차(Spatial Error)가 어느 단계에서 유입되었는지를 판단해야 한다.

객체 낙하(Object Dropping)는 겉으로 성공적인 파지가 이루어진 이후 발생하므로 다른 형태의 진단 증거(Diagnostic Evidence)가 필요하다. 불충분한 파지력(Gripping Force), 부적절한 접촉 위치(Contact Location), 낮은 마찰력(Friction), 객체 변형(Object Deformation), 예상하지 못한 적재물 특성(Payload Property), 가속도(Acceleration), 진동(Vibration), 그리퍼 마모(Gripper Wear), 액추에이터 결함(Actuator Fault)은 파지 안정성(Grasp Stability)을 감소시킬 수 있다. 안정성 상실의 원인을 식별하기 위해 파지 형성부터 낙하 발생까지 힘, 토크(Torque), 핑거 위치(Finger Position), 모터 전류, 촉각 측정(Tactile Measurement), 로봇 가속도, 객체 움직임을 분석해야 한다.

인식 불확실성(Perception Uncertainty)은 접촉 지점 부근에서 작은 공간적 오차도 치명적인 문제가 될 수 있기 때문에 조작 오류의 주요 원인이다. 객체 탐지기가 올바른 객체를 식별하더라도 자세 추정 오차가 충분히 크면 파지 실패나 충돌이 발생할 수 있다. 가림(Occlusion), 반사 표면(Reflective Surface), 투명 재질(Transparent Material), 부정확한 깊이 센싱(Depth Sensing), 복잡한 환경(Clutter), 변화하는 조명(Changing Illumination)은 추정 성능을 더욱 저하시킬 수 있다. 고장 기록에는 원시 센서 데이터(Raw Sensor Data), 탐지된 형상(Detected Geometry), 신뢰도(Confidence), 자세 공분산(Pose Covariance), 계획에 사용된 좌표 변환(Transformation)을 보존해야 한다.

캘리브레이션 오류(Calibration Error)는 정상적인 조작 명령을 일정한 방향으로 체계적으로 이동시킬 수 있다. 카메라-로봇 외부 캘리브레이션(Camera-to-Robot Extrinsic Calibration), 도구 중심점 캘리브레이션(Tool-Center-Point Calibration), 관절 오프셋(Joint Offset), 그리퍼 형상(Gripper Geometry), 좌표계 변환(Coordinate-Frame Transformation)은 인식과 제어 전체에서 일관성을 유지해야 한다. 수 밀리미터 수준의 오차는 일반적인 운반 작업에서는 허용될 수 있지만 정밀 삽입(Precision Insertion)에서는 허용되지 않을 수 있다. 따라서 유사한 방향의 오프셋을 가진 고장이 반복되면 캘리브레이션 또는 좌표계 변환 문제를 강하게 의심할 수 있다.

파지 계획(Grasp Planning)은 파지 실행(Grasp Execution)과 독립적으로 평가해야 한다. 플래너(Planner)는 수학적으로 도달 가능한 파지를 생성할 수 있지만 접촉점(Contact Point), 접근 방향(Approach Direction), 마찰, 무게 중심(Center of Mass), 객체 형상이 불리한 경우 물리적으로 불안정할 수 있다. 후보 파지 점수(Candidate Grasp Score)는 실제 성공 결과와 비교해야 한다. 높은 순위의 후보가 반복적으로 실패한다면 파지 품질 모델(Grasp Quality Model)이 실제 운용 환경에서 중요한 물리적 특성을 충분히 표현하지 못하고 있음을 의미할 수 있다.

동작 계획 고장(Motion Planning Failure)은 매니퓰레이터(Manipulator)가 원하는 파지 또는 배치 자세에 안전하게 도달할 수 없을 때 발생한다. 관절 한계(Joint Limit), 특이점(Singularity), 자기 충돌(Self-Collision), 환경 장애물(Environmental Obstacle), 부족한 여유 공간(Insufficient Clearance), 잘못된 접근 방향(Invalid Approach Direction)은 실행 가능한 궤적을 제거할 수 있다. 플래너가 연산상 성공하더라도 장애물과 지나치게 가깝거나 작은 모델 오차에 민감한 동작을 생성할 수 있다. 분석에서는 후보 궤적(Candidate Trajectory), 충돌 검사(Collision Check), 관절 상태(Joint State), 제약 조건(Constraint), 계획 결과(Planning Outcome)를 보존해야 한다.

실행 오류(Execution Error)는 물리적 로봇이 계획된 궤적을 정확하게 추종하지 못할 때 발생한다. 서보 추종 오차(Servo Tracking Error), 백래시(Backlash), 관절 컴플라이언스(Joint Compliance), 적재하중에 의한 변형(Payload-Induced Deflection), 액추에이터 포화(Actuator Saturation), 통신 지연(Communication Delay), 진동, 제어기 튜닝(Controller Tuning)은 엔드 이펙터가 목표 경로에서 벗어나게 만들 수 있다. 명령된 관절 궤적과 측정된 관절 궤적을 엔드 이펙터 자세 및 제어기 오차(Controller Error)와 비교하면 고장이 계획 단계에서 발생했는지 실제 실행 과정에서 발생했는지를 판단할 수 있다.

힘 제어 조작(Force-Controlled Manipulation)은 또 다른 유형의 고장을 발생시킨다. 삽입(Insertion), 조립(Assembly), 표면 추종(Surface Following), 구속 운동(Constrained Motion) 중 과도한 힘은 정렬 불량(Misalignment), 예상하지 못한 접촉(Unexpected Contact), 부적절한 컴플라이언스 파라미터(Compliance Parameter), 잘못된 환경 모델(Environment Model)을 나타낼 수 있다. 반대로 힘이 부족하면 완전한 체결(Seating)이나 안정적인 접촉이 이루어지지 않을 수 있다. 비정상적인 상호작용 동역학(Interaction Dynamics)을 정확하게 재구성하려면 힘과 토크 이력을 위치, 속도, 접촉 상태, 작업 단계(Task Phase)와 시간 동기화해야 한다.

삽입 고장(Insertion Failure)은 매우 작은 정렬 오차도 끼임(Jamming)이나 쐐기 현상(Wedging)을 발생시킬 수 있으므로 특별한 주의가 필요하다. 페그 인 홀(Peg-in-Hole), 커넥터 결합(Connector Mating), 부품 조립(Component Assembly), 도구 결합(Tool Engagement)은 위치 정확도(Position Accuracy), 자세 정확도(Orientation Accuracy), 컴플라이언스(Compliance), 접촉 형상(Contact Geometry), 힘 임계값(Force Threshold)에 의존한다. 접촉 상태를 진단하지 않고 삽입을 반복하면 부품이나 도구가 손상될 수 있으므로 복구 과정에서는 수정 가능한 정렬 오류와 물리적으로 호환되지 않거나 손상된 부품을 구분해야 한다.

해제 및 배치 고장(Release and Placement Failure)은 운반이 성공적으로 완료된 이후에도 발생할 수 있다. 그리퍼 마찰(Gripper Friction), 흡착 유지(Suction Persistence), 자기력(Magnetic Force), 접착(Adhesion), 기계적 간섭(Mechanical Interference)으로 인해 객체가 엔드 이펙터에서 분리되지 않을 수 있다. 반대로 너무 이른 해제(Premature Release)는 부정확한 배치나 낙하를 발생시킬 수 있다. 분석에서는 그리퍼 열림 명령만으로 성공적인 해제가 이루어졌다고 가정하지 말고 해제 명령(Release Command), 액추에이터 응답(Actuator Response), 접촉 상태, 객체 지지 상태(Object Support Condition), 엔드 이펙터 움직임, 해제 후 객체 자세(Post-Release Object Pose)를 확인해야 한다.

객체 특성(Object Property)은 명시적인 진단 변수(Diagnostic Variable)로 취급해야 한다. 질량(Mass), 크기(Dimensions), 무게 중심(Center of Gravity), 표면 마찰(Surface Friction), 강성(Rigidity), 변형성(Deformability), 취성(Fragility), 반사도(Reflectivity), 포장 변동(Packaging Variation)은 조작 성능에 상당한 영향을 미칠 수 있다. 하나의 제품 변형(Product Variant)에서 검증된 파지 전략이 시각적으로 유사한 다른 제품에서는 실패할 수 있다. 객체 유형과 관련 물리 특성을 기록하면 파지 및 취급 안정성에 직접 영향을 미치는 조건에 따라 고장을 그룹화할 수 있다.

고장 탐지(Failure Detection)는 작업 완료 이후에만 수행하는 것이 아니라 조작 과정 중에 이루어져야 한다. 파지 검증(Grasp Verification)은 핑거 위치, 모터 전류, 힘, 촉각 센싱(Tactile Sensing), 진공 압력(Vacuum Pressure), 비전(Vision), 객체 추적(Object Tracking)을 결합할 수 있다. 예상하지 못한 변화는 완전한 낙하가 발생하기 전에 미끄러짐(Slip)이나 파지 손실을 나타낼 수 있다. 조기 탐지(Early Detection)를 통해 로봇은 가속도를 낮추고, 안전 범위 내에서 파지력을 증가시키거나, 객체를 재배치하고, 안전한 위치에 내려놓거나, 손상이 발생하기 전에 작업자 지원을 요청할 수 있다.

근본 원인 분석(Root Cause Analysis, RCA)은 외부에 나타난 고장과 이를 시작한 메커니즘(Initiating Mechanism)을 구분해야 한다. 객체 낙하가 그리퍼 고장으로 기록될 수 있지만 실제 인과 사슬(Causal Chain)은 자세 추정 오류, 중심에서 벗어난 파지(Off-Center Grasping), 부족한 접촉 면적(Contact Area), 점진적인 미끄러짐(Progressive Slip), 가속 중 최종적인 파지 해제로 시작될 수 있다. 인식, 계획, 로봇 상태, 힘, 그리퍼, 제어기 로그를 시간 동기화하면 이러한 인과 시퀀스를 재구성하고 최종 증상만을 대상으로 잘못된 시정 조치를 수행하는 것을 방지할 수 있다.

시정 조치(Corrective Action)는 검증된 고장 클래스(Failure Class)에 대응해야 한다. 인식 오류는 센싱 또는 자세 추정 개선이 필요할 수 있고, 캘리브레이션 문제는 재캘리브레이션(Recalibration)이 필요하며, 불안정한 파지는 다른 접촉 전략(Contact Strategy)을 요구할 수 있다. 실행 오류는 제어기 또는 기계 시스템의 변경이 필요할 수 있으며, 힘 관련 고장은 컴플라이언스 튜닝(Compliance Tuning)이나 접촉 상태 로직(Contact-State Logic)의 개선이 필요할 수 있다. 일부 고장은 알고리즘 복잡성을 증가시키는 것보다 지그(Fixture), 그리퍼, 객체 또는 작업장(Workstation)을 재설계하는 것이 더 효과적일 수 있다.

검증(Validation)에서는 실제 객체의 변동과 운용 조건을 고려하여 대표적인 파지 실패, 낙하, 충돌, 삽입, 해제 시나리오를 재현해야 한다. 성능은 파지 성공률(Grasp Success Rate), 배치 정확도(Placement Accuracy), 낙하율(Drop Rate), 삽입 성공률(Insertion Success), 접촉력(Contact Force), 사이클 시간(Cycle Time), 복구 성공률(Recovery Success), 개입 빈도(Intervention Frequency)를 이용해 측정해야 한다. 조작 신뢰성(Manipulation Reliability)은 자세, 마찰, 객체 특성, 센싱, 기계적 동작의 통계적 변동에 영향을 받기 때문에 반복 시험(Repeated Trial)이 필요하다.

현장에서 발생한 조작 고장(Field Manipulation Failure)은 최종적으로 구조화된 엔지니어링 지식(Structured Engineering Knowledge)으로 전환되어야 한다. 각 사고에는 객체 정보(Object Information), 인식 출력(Perception Output), 파지 후보(Grasp Candidate), 궤적, 로봇 상태, 힘 이력(Force History), 그리퍼 상태, 고장 시그니처(Failure Signature), 복구 결과(Recovery Result), 검증된 근본 원인(Verified Root Cause)을 보존할 수 있다. 이러한 기록을 집계하면 제품, 로봇, 도구, 사이트 전반에서 반복되는 취약점을 식별할 수 있다. 이를 통해 현장 운용(Field Operation), 고장 분석(Failure Analysis), 조작 시스템 설계(Manipulation Design), 검증, 후속 배포(Deployment)를 연결하는 지속적인 개선 루프(Improvement Loop)를 구축할 수 있다.

## 10.07. Fleet Downtime Analysis MTBF MTTR Dashboard [w/Code]

![](images/image7.png){width="7.268055555555556in" height="7.268055555555556in"}

플릿 다운타임 분석(Fleet Downtime Analysis)은 개별 로봇의 운용 중단을 운용 신뢰성(Operational Reliability), 유지보수성(Maintainability), 생산 영향(Production Impact)에 대한 측정 가능한 정보로 변환한다. 플릿에는 작업량, 사용 연수, 구성, 운용 환경이 서로 다른 로봇이 포함될 수 있으므로 단순히 고장 횟수만 집계하는 것으로는 충분하지 않다. 다운타임 분석에서는 고장 이벤트(Failure Event), 운용 시간(Operating Hours), 수리 활동(Repair Activity), 임무 기록(Mission Record), 유지보수 이력(Maintenance History), 플릿 가용성(Fleet Availability)을 결합하여 신뢰성 손실이 어디에서 발생하는지를 파악해야 한다.

성능 지표(Performance Indicator)를 계산하기 전에 다운타임(Downtime)을 일관되게 정의해야 한다. 로봇은 하드웨어 고장(Hardware Failure), 소프트웨어 고장(Software Failure), 충전(Charging), 계획 유지보수(Planned Maintenance), 안전 점검(Safety Inspection), 작업자 개입(Operator Intervention), 인프라 문제(Infrastructure Problem), 예비 부품 대기(Waiting for Spare Parts)로 인해 사용 불가능할 수 있다. 계획 다운타임(Planned Downtime)과 비계획 다운타임(Unplanned Downtime)은 서로 다른 운용 조건을 나타내므로 일반적으로 분리해야 한다. 또한 로봇, 사이트, 유지보수 팀 사이에서 측정 기준이 달라지는 것을 방지하려면 명확한 시작 및 종료 규칙(Start and End Rule)이 필요하다.

평균 고장 간격(Mean Time Between Failures, MTBF)은 수리 가능한 고장 사이의 평균 운용 시간을 측정하며 기본적인 신뢰성(Reliability) 수준을 나타낸다. 관측 기간 동안 누적된 운용 시간을 관련 고장 횟수로 나누어 계산할 수 있다. 이때 어떤 사건을 유효한 고장(Qualifying Failure)으로 판단할 것인지에 대한 정의를 일관되게 유지해야 한다. 경미한 경고(Minor Warning), 자동 복구(Automatic Recovery), 작업자 개입, 유지보수가 필요한 고장을 명확한 분류 정책(Classification Policy) 없이 함께 계산해서는 안 된다.

평균 수리 시간(Mean Time To Repair, MTTR)은 고장이 발생한 이후 시스템을 얼마나 신속하게 복구할 수 있는지를 나타낸다. 수리 시간(Repair Time)에는 진단(Diagnosis), 기술자 대응(Technician Response), 물리적 수리(Physical Repair), 소프트웨어 복구(Software Recovery), 부품 교체(Component Replacement), 캘리브레이션(Calibration), 검증(Verification), 서비스 복귀(Return to Service)가 포함될 수 있다. 좁은 의미의 기술적 수리 시간은 생산 현장에서 실제로 경험하는 전체 운용 중단 시간과 크게 다를 수 있으므로 조직은 MTTR에 어떤 구간을 포함할 것인지 명확하게 정의해야 한다.

가용성(Availability)은 장비가 요구된 기능을 수행할 수 있는 시간의 비율을 측정하여 신뢰성과 유지보수성을 연결한다. 수리 가능한 시스템(Repairable System)의 고유 가용성(Inherent Availability)은 일반적으로 MTBF와 MTTR의 관계를 통해 표현할 수 있지만 플릿 운용에서는 더 넓은 해석이 필요하다. 기술자 대기, 교체 부품 대기, 네트워크 복구(Network Recovery), 인프라 접근, 운용 승인(Operational Approval)은 물리적인 수리 자체가 짧더라도 실제 비가용 시간(Unavailability)을 크게 증가시킬 수 있다.

로봇마다 누적되는 운용 노출량(Operational Exposure)이 다르므로 플릿 지표(Fleet Metric)는 정규화(Normalization)해야 한다. 하나의 로봇은 지속적으로 운용될 수 있지만 다른 로봇은 하루에 몇 시간만 운용될 수 있다. 따라서 고장률(Failure Rate)은 운용 시간, 임무(Mission), 이동 거리(Kilometer), 조작 사이클(Manipulation Cycle) 또는 응용 분야에 적합한 다른 작업량 지표를 기준으로 표현할 수 있다. 노출량 정규화(Exposure Normalization)는 작업량이 많은 로봇이 단순히 더 많은 업무를 수행했다는 이유만으로 신뢰성이 낮은 것처럼 보이는 것을 방지한다.

고장 분류(Failure Classification)는 다운타임 지표에 엔지니어링 의미를 부여한다. 이벤트는 하드웨어, 소프트웨어, 인공지능 인식(AI Perception), 내비게이션(Navigation), 조작(Manipulation), 통신(Communication), 인프라(Infrastructure), 배터리(Battery), 안전(Safety), 작업자 또는 운용 원인(Human or Operational Cause)에 따라 그룹화할 수 있다. 각 범주는 고장 횟수, 누적 다운타임(Accumulated Downtime), MTBF, MTTR, 재발률(Recurrence Rate), 생산 영향을 기준으로 분석할 수 있다. 발생 횟수가 적은 고장이라도 한 번 발생할 때 매우 긴 복구 시간이 필요하다면 더 높은 우선순위를 가질 수 있다.

다운타임 대시보드(Downtime Dashboard)는 플릿 전체 평균만 표시하는 것이 아니라 여러 수준에서 분석할 수 있어야 한다. 엔지니어는 개별 로봇, 로봇 모델(Robot Model), 하드웨어 리비전(Hardware Revision), 소프트웨어 릴리스(Software Release), 사이트(Site), 작업 교대조(Shift), 임무 유형(Mission Type), 고장 범주를 비교해야 할 수 있다. 플릿 관리자는 가용성과 생산 영향을 필요로 하고, 유지보수 팀은 반복적으로 고장 나는 구성요소와 수리 시간을 필요로 한다. 동일한 기본 이벤트 데이터(Underlying Event Data)가 이러한 서로 다른 운용 관점을 지원해야 한다.

추세 분석(Trend Analysis)은 단일 MTBF 또는 MTTR 값보다 더 많은 정보를 제공한다. 주간 또는 월간 추세를 통해 시정 조치(Corrective Action) 이후 신뢰성이 개선되고 있는지 또는 장비 노후화에 따라 악화되고 있는지를 확인할 수 있다. 소프트웨어 배포(Software Deployment) 이후 갑작스럽게 고장이 증가하면 회귀 문제(Regression)를 나타낼 수 있으며, 수리 빈도가 점진적으로 증가하면 부품 마모(Component Wear)를 의미할 수 있다. 이동 구간(Rolling Window)을 이용하면 오래된 과거 데이터가 현재 플릿 동작을 과도하게 지배하지 않으면서 이러한 변화를 탐지할 수 있다.

다운타임 지속시간(Downtime Duration)은 의미 있는 단계로 분해해야 한다. 탐지 시간(Detection Time)은 고장이 발생한 이후 인식되기까지의 시간을 측정하고, 대응 시간(Response Time)은 지원 작업이 시작될 때까지의 시간을 측정하며, 진단 시간(Diagnosis Time)은 결함을 분리하는 데 필요한 시간을 나타낸다. 수리 시간은 시정 작업(Corrective Work)을 포함하고, 검증 시간(Validation Time)은 서비스 복귀 이전의 확인 과정을 포함한다. 이를 통해 긴 MTTR을 하나의 유지보수 문제로 처리하지 않고 실제 지연을 발생시키는 특정 단계를 식별할 수 있다.

파레토 분석(Pareto Analysis)은 전체 다운타임의 상당 부분을 발생시키는 상대적으로 적은 수의 고장 클래스를 식별하여 신뢰성 개선(Reliability Improvement)의 우선순위를 결정하는 데 도움을 준다. 총 손실 시간(Total Lost Hours), 발생 빈도(Occurrence Frequency), 생산 영향에 따라 이벤트를 정렬하면 서로 다른 우선순위가 나타날 수 있다. 빈번한 소프트웨어 복구는 이벤트 횟수에서 가장 큰 비중을 차지할 수 있지만 드물게 발생하는 구동계 고장(Drivetrain Failure)이 생산 손실 시간에서는 가장 큰 비중을 차지할 수 있다. 따라서 대시보드는 여러 분석 관점을 제공해야 한다.

반복 고장(Repeated Failure)은 불완전한 시정 조치를 의미할 수 있으므로 특별한 주의가 필요하다. 로봇이 빠르게 서비스에 복귀하더라도 동일한 결함이 몇 시간마다 반복된다면 MTTR은 양호하게 나타나면서 실제 운용에는 심각한 장애를 발생시킬 수 있다. 따라서 재발률, 반복 고장까지의 시간(Time to Repeated Failure), 반복 개입(Repeated Intervention)을 MTBF 및 MTTR과 함께 분석해야 한다. 사고를 기존 근본 원인 분석(Root Cause Analysis, RCA) 기록과 연결하면 시정 조치가 실제로 효과가 있었는지를 판단할 수 있다.

플릿 다운타임은 로봇 자체 외부의 의존 시스템(Dependency System)에도 영향을 받는다. 무선 네트워크(Wireless Network), 플릿 서버(Fleet Server), 엘리베이터(Elevator), 자동문(Automatic Door), 충전 인프라(Charging Infrastructure), 생산 시스템 인터페이스(Production Interface)의 고장은 여러 로봇을 동시에 정지시킬 수 있다. 영향을 받은 각 로봇을 독립적인 고장으로 처리하면 신뢰성 통계가 왜곡된다. 공통 원인 이벤트(Common-Cause Event)를 식별하여 공유 인프라 고장과 연결함으로써 최초 원인을 중복 계산하지 않으면서 플릿 수준 영향을 측정해야 한다.

생산 영향(Production Impact)은 모든 로봇의 비가용 상태가 동일한 비즈니스 손실을 발생시키는 것은 아니므로 기술적 다운타임과 별도로 측정해야 한다. 여분의 로봇(Redundant Robot)이 존재하는 경우 한 대가 고장 나더라도 운용이 중단되지 않을 수 있지만 핵심 작업장(Critical Workstation)을 담당하는 로봇의 고장은 전체 공정을 정지시킬 수 있다. 손실된 임무(Lost Mission), 지연된 주문(Delayed Order), 처리량 감소(Reduced Throughput), 유휴 작업장(Idle Workstation), 개입 인력(Intervention Labor), 복구 비용(Recovery Cost)은 신뢰성 개선의 우선순위를 결정하는 추가적인 기준을 제공한다.

데이터 품질(Data Quality)은 신뢰성 대시보드(Reliability Dashboard)의 신뢰도에 직접적인 영향을 미친다. 누락된 타임스탬프(Missing Timestamp), 일관되지 않은 고장 코드(Failure Code), 수동으로 입력된 설명, 중복 사고(Duplicated Incident), 잘못된 서비스 복귀 시간(Return-to-Service Time)은 MTBF와 MTTR을 크게 왜곡할 수 있다. 따라서 자동 이벤트 수집(Automated Event Capture)은 통제된 고장 분류 체계(Failure Taxonomy), 검증 규칙(Validation Rule), 동기화된 시계(Synchronized Clock), 추적 가능한 유지보수 기록(Traceable Maintenance Record)과 결합해야 한다. 감사(Audit)와 이후 재분류(Reclassification)를 위해 원시 이벤트(Raw Event)도 보존해야 한다.

운용 이력이 제한된 로봇이나 구성을 비교할 때는 통계적 해석(Statistical Interpretation)이 필요하다. 새롭게 배포된 로봇은 누적 운용 시간이 적고 아직 고장이 발생하지 않았다는 이유만으로 매우 우수한 MTBF를 나타낼 수 있다. 필요한 경우 신뢰성 비교에는 신뢰구간(Confidence Interval), 표본 크기(Sample Size), 노출 시간(Exposure Time), 관측 기간(Observation Period)을 함께 고려해야 한다. 충분하지 않은 증거에서 계산된 단일 추정값(Point Estimate)만으로 시스템의 순위를 결정하는 것은 피해야 한다.

대시보드는 궁극적으로 신뢰성 지표(Reliability Metric)를 엔지니어링 조치(Engineering Action)와 연결해야 한다. 특정 고장 범주를 선택하면 영향을 받은 로봇, 이벤트 타임라인(Event Timeline), 로그(Log), 유지보수 기록, 근본 원인 분석 결과, 소프트웨어 또는 하드웨어 버전, 시정 조치까지 추적할 수 있어야 한다. 변경 사항을 배포한 이후에는 후속 MTBF, MTTR, 재발률, 가용성 추세를 통해 해당 조치가 개별 사고 티켓(Incident Ticket)을 단순히 종료한 것이 아니라 측정 가능한 개선 효과를 실제로 발생시켰는지를 판단할 수 있다.

성숙한 플릿 다운타임 프로세스(Fleet Downtime Process)는 폐쇄형 신뢰성 개선 루프(Closed Reliability Improvement Loop)를 형성한다. 운용 이벤트는 구조화된 다운타임 기록을 생성하고, 대시보드는 주요 손실 요인을 드러내며, 근본 원인 분석(RCA)은 고장 메커니즘을 식별하고, 엔지니어링 팀은 시정 조치를 구현하며, 플릿 모니터링(Fleet Monitoring)은 그 결과를 검증한다. 시간이 지남에 따라 MTBF는 증가하고 MTTR과 재발률은 감소하며 가용성은 향상되어야 한다. 이를 통해 현장 고장 이력(Field Failure History)을 유지보수, 설계, 배포, 플릿 최적화(Fleet Optimization)를 위한 측정 가능한 엔지니어링 증거로 전환할 수 있다.

## 10.08. Predictive Failure Detection ML Model [w/Code]

![](images/image8.png){width="7.268055555555556in" height="7.268055555555556in"}

예측 고장 탐지(Predictive Failure Detection)는 머신러닝(Machine Learning)을 사용하여 로봇 고장이 운용에 심각한 영향을 미치기 전에 고장 발생 확률이 증가하고 있음을 나타내는 패턴을 식별한다. 기존 경보(Conventional Alarm)가 임계값을 이미 초과한 이후 대응하는 것과 달리 예측 모델(Predictive Model)은 텔레메트리(Telemetry), 로그(Log), 센서 측정값(Sensor Measurement), 운용 조건(Operating Condition), 과거 고장 이력(Historical Failure)을 결합하여 분석한다. 목표는 점검, 유지보수, 안전한 복구(Graceful Recovery), 임무 재할당(Mission Reassignment)을 수행할 수 있는 충분한 사전 경고 시간(Warning Time)을 확보하는 것이다.

예측 고장 데이터셋(Predictive Failure Dataset)은 단순히 개별 고장 기록만 포함하는 것이 아니라 시간에 따른 로봇 상태를 표현해야 한다. 유용한 입력에는 모터 전류, 온도, 진동, 배터리 전압, 관절 오차(Joint Error), CPU 및 GPU 사용률, 메모리 사용량, 네트워크 지연시간(Network Latency), 위치추정 신뢰도(Localization Confidence), 인식 신뢰도(Perception Confidence), 제어기 오류(Controller Error), 안전 이벤트(Safety Event), 임무 상태(Mission State), 소프트웨어 경고(Software Warning)가 포함된다. 유지보수 기록(Maintenance Record)과 확인된 고장 타임스탬프(Failure Timestamp)는 성능 저하 패턴을 실제 결과와 연결하는 핵심 레이블(Label)을 제공한다.

많은 고장이 점진적으로 진행되기 때문에 시간 윈도 구성(Time-Window Construction)은 매우 중요하다. 고장 메커니즘에 따라 측정값을 수초, 수분, 수시간 또는 그 이상의 슬라이딩 윈도(Sliding Window)로 그룹화할 수 있다. 각 윈도는 원시 시퀀스(Raw Sequence) 또는 평균(Mean), 분산(Variance), 최솟값(Minimum), 최댓값(Maximum), 기울기(Slope), 주파수 성분(Frequency Component), 이벤트 횟수(Event Count), 변화율(Rate of Change)과 같은 통계적 특징으로 최근 동작을 표현할 수 있다. 예측 지평(Prediction Horizon)은 실제 운용에서 유용한 사전 경고 시간을 제공하도록 설정해야 한다.

레이블 설계(Label Design)는 머신러닝 모델이 실제로 무엇을 학습하는지를 결정한다. 이진 분류(Binary Classification)는 정의된 미래 시간 범위 내에 고장이 발생할지를 분류할 수 있으며, 다중 클래스 모델(Multiclass Model)은 모터, 배터리, 내비게이션, 통신, 소프트웨어 고장과 같은 고장 범주를 예측할 수 있다. 다른 접근법으로는 잔여 유효 수명(Remaining Useful Life, RUL)이나 연속 위험 점수(Continuous Risk Score)를 추정할 수 있다. 부정확한 고장 시점이나 모호한 원인은 모델 품질을 크게 저하시킬 수 있으므로 레이블은 검증된 사고 및 유지보수 기록에서 생성해야 한다.

클래스 불균형(Class Imbalance)은 정상적인 로봇 운용 데이터가 실제 고장 데이터보다 훨씬 많기 때문에 발생하는 핵심 문제이다. 모델은 대부분의 경우 정상 상태만 예측해도 겉으로는 높은 정확도(Accuracy)를 달성할 수 있다. 따라서 평가에서는 정밀도(Precision), 재현율(Recall), F1 점수(F1 Score), 오경보율(False-Alarm Rate), 정밀도-재현율 특성(Precision-Recall Behavior), 탐지 선행 시간(Detection Lead Time)을 중요하게 고려해야 한다. 샘플링 전략(Sampling Strategy), 클래스 가중치(Class Weighting), 특수 손실 함수(Specialized Loss Function), 신중하게 설계된 이상 탐지(Anomaly Detection)를 이용하여 심각한 불균형 문제를 완화할 수 있다.

특징 엔지니어링(Feature Engineering)은 운용 텔레메트리를 성능 저하를 나타내는 지표로 변환할 수 있다. 모터 전류 분산의 증가는 기계적 저항(Mechanical Resistance)을 나타낼 수 있고, 온도 상승 추세는 냉각 또는 마찰 문제를 의미할 수 있으며, 반복적인 플래너 복구(Planner Recovery)는 내비게이션 고장에 앞서 발생할 수 있다. 또한 통신 지연시간의 증가는 네트워크 불안정(Network Instability)을 나타낼 수 있다. 물리적으로 의미 있는 특징은 개별 측정값만으로 식별하기 어려운 미세한 성능 저하 신호(Degradation Signal)를 드러낼 수 있으므로 도메인 지식(Domain Knowledge)이 중요하다.

지도학습(Supervised Learning)은 충분한 레이블 고장 이력(Labeled Failure History)이 존재할 때 적합하다. 로지스틱 회귀(Logistic Regression), 의사결정나무(Decision Tree), 랜덤 포레스트(Random Forest), 그래디언트 부스팅 트리(Gradient-Boosted Tree), 서포트 벡터 머신(Support Vector Machine), 신경망(Neural Network)은 운용 특징과 미래 고장 사이의 관계를 학습할 수 있다. 단순한 모델은 의사결정을 해석하기 쉽다는 장점이 있으며 복잡한 모델은 비선형 상호작용(Nonlinear Interaction)을 포착할 수 있다. 모델 복잡도(Model Complexity)는 현실적인 검증 조건에서 측정 가능한 성능 향상이 있을 때 정당화되어야 한다.

비지도학습(Unsupervised Learning)과 준지도학습(Semi-Supervised Learning)은 고장 레이블이 부족한 경우 유용하다. 모델은 정상 동작(Normal Behavior)의 표현을 학습하고 이와 다른 상태를 이상(Anomaly)으로 탐지할 수 있다. 통계적 방법(Statistical Method), 클러스터링(Clustering), 격리 기반 모델(Isolation-Based Model), 오토인코더(Autoencoder), 기타 표현 학습(Representation Learning) 기법을 통해 이전에 확인되지 않은 성능 저하 패턴을 탐지할 수 있다. 그러나 이상 상태가 자동으로 고장을 의미하는 것은 아니므로 시정 조치를 실행하기 전에 탐지된 편차를 운용 결과 및 엔지니어링 증거와 연계하여 확인해야 한다.

시퀀스 모델(Sequential Model)은 정적 특징(Static Feature)이 포착하기 어려운 시간적 의존성(Temporal Dependency)을 학습할 수 있다. 순환 신경망(Recurrent Neural Network), 시간 합성곱 신경망(Temporal Convolutional Network), 트랜스포머(Transformer) 및 관련 아키텍처는 텔레메트리와 이벤트 시퀀스를 분석하여 점진적으로 발전하는 성능 저하를 식별할 수 있다. 이벤트의 순서와 지속시간이 중요한 경우 이러한 모델의 장점이 커진다. 그러나 복잡한 시퀀스 모델은 실제 고장 전조(Failure Precursor) 대신 사이트별 일정, 로봇 식별 정보, 운용 패턴을 학습할 수 있으므로 신중한 검증이 필요하다.

학습 및 평가 데이터셋(Training and Evaluation Dataset)은 정보 누출(Information Leakage)을 방지하도록 분리해야 한다. 동일한 고장 이벤트에서 생성된 인접 시간 윈도를 무작위로 분할하면 거의 동일한 샘플이 학습 세트와 시험 세트에 동시에 포함되어 비현실적으로 높은 성능이 나타날 수 있다. 고장 에피소드(Failure Episode), 로봇, 시간 구간(Time Period), 사이트 단위의 분리는 일반화 성능(Generalization)을 더 강하게 검증할 수 있다. 가능하다면 최종 평가는 모델 학습에 직접 사용되지 않은 로봇과 운용 조건을 포함해야 한다.

예측 성능(Prediction Performance)은 머신러닝 지표뿐 아니라 운용 관점에서도 평가해야 한다. 모터 정지 5초 전에 생성된 경고는 통계적으로 정확하더라도 유지보수 준비에 수시간이 필요하다면 운용상 의미가 없을 수 있다. 반대로 수일 전에 생성되는 예측은 지나치게 높은 불확실성을 발생시킬 수 있다. 따라서 탐지 선행 시간, 운용 시간당 오경보(False Alarm), 놓친 중요 고장(Missed Critical Failure), 개입 비용(Intervention Cost), 방지된 다운타임(Avoided Downtime)을 기존 분류 지표와 함께 평가해야 한다.

예측 결과가 유지보수 또는 플릿 운용(Fleet Operation)에 영향을 미치는 경우 설명 가능성(Explainability)이 중요하다. 엔지니어는 어떤 신호가 높은 위험 예측(High-Risk Prediction)에 기여했으며 해당 신호가 물리적으로 타당한지를 이해할 필요가 있다. 특징 중요도(Feature Importance), 지역적 설명(Local Explanation), 추세 시각화(Trend Visualization), 과거 고장 시그니처(Historical Failure Signature)와의 비교는 진단을 지원할 수 있다. 설명 가능성을 인과관계의 증명으로 간주해서는 안 되지만 실제 성능 저하와 관련 없는 운용 조건에서 발생한 상관관계를 구분하는 데 도움을 줄 수 있다.

예측 모델은 로봇과 운용 환경 사이의 차이를 고려해야 한다. 하드웨어 리비전(Hardware Revision), 적재하중(Payload), 임무 유형(Mission Type), 바닥 조건(Floor Condition), 주변 온도(Ambient Temperature), 소프트웨어 버전, 사용 강도(Utilization Intensity)는 정상 텔레메트리 분포를 변화시킬 수 있다. 따라서 하나의 플릿 공통 임계값(Fleet-Wide Threshold)이나 모델이 모든 사이트에서 동일한 성능을 보장하지는 않는다. 운용 데이터에서 체계적인 차이가 확인된다면 문맥 변수(Context Variable), 로봇별 기준선(Robot-Specific Baseline), 도메인 적응(Domain Adaptation), 개별 모델을 고려할 수 있다.

배포 아키텍처(Deployment Architecture)는 예측 기능을 기존 모니터링 및 유지보수 프로세스와 통합해야 한다. 엣지 추론(Edge Inference)은 낮은 지연시간으로 탐지를 수행하고 네트워크 중단 중에도 계속 동작할 수 있으며, 중앙 집중형 플릿 분석(Centralized Fleet Analysis)은 여러 로봇의 장기간 이력 데이터를 결합할 수 있다. 예측 결과에는 타임스탬프, 위험 점수(Risk Score), 의심되는 고장 클래스(Suspected Failure Class), 관련 증거(Relevant Evidence), 권장 점검 대상(Recommended Inspection Target)이 포함되어야 한다. 경보는 통제되지 않은 또 다른 경고 스트림을 만드는 대신 심각도(Severity)에 따라 전달되어야 한다.

로봇의 동작은 시간에 따라 변화하므로 배포 이후 모델 드리프트(Model Drift)를 모니터링해야 한다. 새로운 소프트웨어, 교체된 부품, 서로 다른 적재하중, 변경된 경로, 센서 노화(Sensor Aging), 환경 변화는 특징과 고장 사이의 관계를 변화시킬 수 있다. 입력 분포(Input Distribution), 예측 발생률(Prediction Rate), 오경보, 미탐 고장(Missed Failure), 보정 상태(Calibration)를 지속적으로 추적해야 한다. 중요한 드리프트가 발생하면 검증되지 않은 자동 모델 교체 대신 조사, 데이터셋 업데이트, 재보정(Recalibration), 통제된 재학습(Controlled Retraining)을 수행해야 한다.

예측 경보(Predictive Alert)는 근본 원인 분석(Root Cause Analysis, RCA) 및 유지보수 결과와 직접 연결되어야 한다. 경고 이후 점검이 수행되면 발견된 상태를 해당 예측 및 후속 조치와 함께 기록해야 한다. 정확한 예측(True Prediction)은 관련 고장 시그니처를 강화하며, 오경보는 모델의 취약점을 드러낸다. 사전 경고 없이 발생한 고장은 다음 개발 주기에서 특징, 레이블, 모델 구조(Model Structure), 탐지 임계값(Detection Threshold)을 개선하기 위한 특히 중요한 샘플이 된다.

성숙한 예측 고장 프로세스(Predictive Failure Process)는 플릿 텔레메트리, 고장 로그(Failure Log), 머신러닝 모델, 유지보수, 근본 원인 분석(RCA), 신뢰성 대시보드(Reliability Dashboard)를 연결하는 폐쇄 루프(Closed Loop)를 형성한다. 과거 고장은 예측 모델을 학습시키고, 배포된 모델은 새롭게 발생하는 위험을 식별하며, 유지보수 조치는 새로운 증거를 생성하고, 검증된 결과는 다시 데이터셋으로 반환된다. 최종 목표는 단순히 예측 정확도를 높이는 것이 아니라 더 빠른 사전 개입(Early Intervention), 예상하지 못한 고장의 감소, 다운타임 감소, 평균 고장 간격(Mean Time Between Failures, MTBF) 향상, 그리고 더욱 신뢰할 수 있는 산업용 로봇 플릿을 구현하는 것이다.

## 10.09. Failure Analysis Feedback to Development Loop

![](images/image9.png){width="7.268055555555556in" height="7.268055555555556in"}

고장 분석(Failure Analysis)은 현장 사고(Field Incident)가 설계, 소프트웨어, 인공지능 모델(AI Model), 검증(Validation), 운용의 체계적인 변경으로 전환될 때 가장 큰 엔지니어링 가치를 창출한다. 로봇을 복구한 후 고장 티켓(Failure Ticket)을 종료하는 것은 즉각적인 운용 중단을 해결하지만 반드시 제품 개선으로 이어지는 것은 아니다. 개발 피드백 루프(Development Feedback Loop)는 검증된 고장 증거가 수집되고, 우선순위가 결정되며, 담당자가 지정되고, 수정 및 검증된 후 배포되고, 재발 위험(Recurrence Risk)이 측정 가능하게 감소할 때까지 모니터링되도록 한다.

피드백 루프는 구조화된 사고 수집(Structured Incident Capture)에서 시작된다. 각각의 고장 기록에는 로봇, 사이트(Site), 임무(Mission), 타임스탬프(Timestamp), 운용 상태(Operating State), 소프트웨어 및 하드웨어 버전, 환경 조건(Environmental Condition), 증상(Symptom), 로그(Log), 텔레메트리(Telemetry), 복구 조치(Recovery Action), 생산 영향(Production Impact)이 보존되어야 한다. 원시 증거(Raw Evidence)는 개발팀이 불완전한 설명이나 개별 작업자의 기억에 의존하지 않고 이벤트를 재현할 수 있도록 해당 사고와 추적 가능하게 연결되어야 한다.

트리아지(Triage)는 운용 사고를 엔지니어링 작업(Engineering Work)으로 전환한다. 고장은 안전 영향(Safety Consequence), 생산 손실(Production Loss), 재발성(Recurrence), 영향을 받는 플릿 규모(Fleet Size), 고객 영향(Customer Impact), 탐지 가능성(Detectability), 복구 난이도(Recovery Difficulty)를 기준으로 우선순위를 결정할 수 있다. 드물게 발생하는 안전 중요 이벤트(Safety-Critical Event)는 즉각적인 조사가 필요할 수 있으며, 빈번하지만 심각도가 낮은 운용 중단은 체계적인 개선 대상으로 그룹화할 수 있다. 우선순위는 단순한 고장 빈도가 아니라 기술적 심각도와 누적 운용 비용(Accumulated Operational Cost)을 함께 반영해야 한다.

근본 원인 분석(Root Cause Analysis, RCA)은 현장 증상(Field Symptom)과 개발 변경(Development Change)을 연결하는 역할을 한다. 분석에서는 최초 발생 메커니즘(Initiating Mechanism), 기여 조건(Contributing Condition), 전파 경로(Propagation Path), 탐지 동작(Detection Behavior), 복구 응답(Recovery Response), 최종 결과(Final Consequence)를 식별해야 한다. 예를 들어 내비게이션 타임아웃(Navigation Timeout)이 발생했다고 해서 이를 자동으로 플래너 결함(Planner Defect)으로 판단해서는 안 된다. 증거를 통해 위치추정 성능 저하(Localization Degradation), 네트워크 지연(Network Delay), 지도 불일치(Map Inconsistency), 교통 예약 로직(Traffic Reservation Logic)이 이벤트를 시작한 원인으로 확인될 수 있다.

근본 원인이 충분한 증거로 뒷받침되면 해당 사고를 명시적인 엔지니어링 요구사항(Engineering Requirement)으로 변환해야 한다. "내비게이션 강건성(Navigation Robustness)을 개선한다"와 같은 모호한 조치는 검증하기 어렵다. 보다 명확한 요구사항은 운용 조건, 예상 시스템 동작(Expected System Behavior), 측정 가능한 한계(Measurable Limit), 복구 응답, 승인 기준(Acceptance Criterion)을 정의한다. 현장 증거를 시험 가능한 요구사항(Testable Requirement)으로 변환하면 학습된 교훈(Lessons Learned)이 단순한 서술형 보고서로만 남는 것을 방지할 수 있다.

시정 조치(Corrective Action)는 여러 개발 영역(Development Domain)에 영향을 줄 수 있다. 소프트웨어 결함은 코드 변경(Code Change)이 필요할 수 있고, 인공지능 고장(AI Failure)은 데이터셋 또는 모델 업데이트가 필요할 수 있으며, 하드웨어 고장은 부품 또는 기계 설계 변경(Mechanical Redesign)이 필요할 수 있다. 운용 고장은 설정(Configuration)이나 절차 변경(Procedure Change)을 요구할 수 있다. 여러 영역에 걸친 사고(Cross-Domain Incident)는 서로 다른 팀이 최초 발생 메커니즘을 해결하지 않은 채 각각 증상만 수정하는 것을 방지하기 위해 공통 담당자(Common Owner)와 인과관계 기록(Causal Record)을 유지해야 한다.

현장 고장(Field Failure)은 가능한 경우 재현 가능한 시험 사례(Reproducible Test Case)로 변환해야 한다. 관련 로그, 센서 기록(Sensor Recording), 지도(Map), 객체 구성(Object Configuration), 로봇 상태(Robot State), 교통 조건(Traffic Condition), 환경 파라미터(Environmental Parameter)를 회귀 시험 시나리오(Regression Scenario)로 변환할 수 있다. 과거에 현장 고장을 발생시킨 결함은 이후 릴리스(Release)가 반드시 통과해야 하는 영구적인 시험(Permanent Test)이 되는 것이 이상적이다. 이를 통해 비용이 많이 소요된 현장 운용 경험을 재사용 가능한 검증 자산(Validation Asset)으로 전환할 수 있다.

시뮬레이션(Simulation)과 리플레이(Replay)는 실제 장비 시험 전에 많은 고장을 효율적으로 재현할 수 있는 방법을 제공한다. 기록된 센서 스트림(Sensor Stream)은 인식 및 내비게이션 소프트웨어를 통해 다시 실행할 수 있으며, 시뮬레이션은 장애물, 교통 충돌(Traffic Conflict), 조작 조건(Manipulation Condition), 통신 장애(Communication Disturbance)를 재구성할 수 있다. 최초 발생 조건을 누락한 단순화된 시뮬레이션은 결함이 해결되었다는 잘못된 판단을 만들 수 있으므로 재현 정확도(Reproduction Accuracy)를 반드시 검증해야 한다.

소프트웨어 변경은 배포 전에 계층화된 검증(Layered Validation)을 통과해야 한다. 단위 시험(Unit Test)은 개별 로직을 검증하고, 통합 시험(Integration Test)은 구성요소 사이의 상호작용을 평가하며, 로그 리플레이(Log Replay)는 과거 사고를 확인하고, 시뮬레이션은 보다 광범위한 시나리오를 평가한다. 하드웨어 인더 루프(Hardware-in-the-Loop, HIL) 또는 실제 로봇 시험(Physical Robot Testing)은 실제 시스템 동작을 최종적으로 확인한다. 안전 중요 고장이나 영향도가 높은 고장은 하나의 환경에서 성공적으로 재현되었다는 사실만으로 관련 고장 모드(Failure Mode)가 제거되었다고 보장할 수 없으므로 더욱 강력한 검증 증거가 필요하다.

인공지능 관련 시정 조치(AI-Related Corrective Action)에는 추가적인 데이터 거버넌스(Data Governance)가 필요하다. 고장 샘플(Failure Sample)은 검토, 레이블링(Labeling), 버전 관리(Versioning)를 거쳐 필요한 경우 통제된 학습 데이터셋(Training Dataset)이나 회귀 데이터셋(Regression Dataset)에 포함되어야 한다. 모델 재학습(Model Retraining)은 목표 고장 사례에서 개선을 입증하는 동시에 다른 영역에서 허용할 수 없는 성능 저하가 발생하지 않았음을 보여야 한다. 데이터셋 버전, 모델 버전, 전처리(Preprocessing), 임계값(Threshold), 평가 결과(Evaluation Result)는 개선 과정의 추적성을 확보하기 위해 원래 사고와 연결되어야 한다.

릴리스 관리(Release Management)는 검증된 엔지니어링 변경을 다시 플릿 운용(Fleet Operation)과 연결한다. 시정 변경(Corrective Change)은 소프트웨어, 펌웨어(Firmware), 모델, 설정 또는 하드웨어 버전과 연결되어야 하며 통제된 릴리스 프로세스(Controlled Release Process)를 통해 배포되어야 한다. 카나리 배포(Canary Deployment) 또는 제한된 사이트 롤아웃(Limited-Site Rollout)은 플릿 전체에 적용하기 전에 위험을 줄일 수 있다. 모니터링에서는 성공적인 설치 자체를 문제 해결로 간주하지 않고 배포 전후의 관련 고장 시그니처(Failure Signature)를 비교해야 한다.

배포 후 검증(Post-Deployment Verification)은 시정 조치 사이클(Corrective-Action Cycle)을 완성한다. 엔지니어는 충분한 관측 기간(Observation Period) 동안 재발률(Recurrence Rate), 평균 고장 간격(Mean Time Between Failures, MTBF), 평균 수리 시간(Mean Time To Repair, MTTR), 개입 빈도(Intervention Frequency), 안전 이벤트(Safety Event), 관련 성능 지표(Performance Indicator)를 모니터링해야 한다. 운용 증거가 예상된 개선을 뒷받침할 때에만 고장이 효과적으로 해결되었다고 판단할 수 있다. 재발이 계속되면 별도의 무관한 사고 기록을 새로 만드는 대신 근본 원인 분석이나 시정 조치를 다시 검토해야 한다.

피드백 루프는 아차 사고(Near Miss)와 성공적인 복구(Successful Recovery)도 포함해야 한다. 로봇이 위치추정 성능 저하를 탐지하고 생산을 중단하지 않은 상태에서 안전하게 복구했다면 공식적인 고장으로 이어지지 않았더라도 시스템의 취약점을 보여줄 수 있다. 반복적인 복구 조치, 경고의 집중 발생(Warning Burst), 신뢰도 저하(Confidence Degradation), 작업자 개입은 새롭게 나타나는 문제에 대한 조기 증거(Early Evidence)를 제공할 수 있다. 이러한 신호를 포함하면 심각한 현장 고장이 누적되기 전에 개발 단계에서 대응할 수 있다.

지식 관리(Knowledge Management)는 프로젝트, 팀, 제품 세대(Product Generation) 사이에서 학습된 교훈이 사라지는 것을 방지한다. 확인된 고장 시그니처, 근본 원인, 영향을 받은 구성(Affected Configuration), 시정 조치, 시험 사례, 검증 증거(Validation Evidence)는 검색 가능한 엔지니어링 지식 베이스(Engineering Knowledge Base)에 저장해야 한다. 새로운 사고를 과거 사례와 비교하면 반복적인 조사를 줄이고 서로 다른 로봇 플랫폼에서 이전에 발생했던 고장 메커니즘을 엔지니어가 빠르게 인식할 수 있다.

지표(Metric)는 피드백 프로세스 자체의 효과도 평가해야 한다. 유용한 측정 항목에는 사고 발생부터 트리아지까지의 시간(Time from Incident to Triage), 근본 원인 확인까지의 시간(Time to Confirmed Root Cause), 시정 조치 리드 타임(Corrective-Action Lead Time), 회귀 시험 커버리지(Regression-Test Coverage), 릴리스 이후 재발(Recurrence After Release), 유출 결함(Escaped Defect), 주요 사고가 영구 시험으로 전환된 비율이 포함된다. 이러한 지표는 조직이 단순히 고장을 빠르게 처리하는 것인지 아니면 실제로 제품 신뢰성(Product Reliability)을 향상시키고 있는지를 보여준다.

자동화(Automation)는 모니터링, 이슈 추적(Issue Tracking), 로그, 시험 시스템(Test System), 배포 기록(Deployment Record)을 연결하여 피드백 루프를 단축할 수 있다. 탐지된 고장 시그니처를 기반으로 관련 증거를 자동 수집하고, 영향을 받는 버전을 식별하며, 유사한 과거 사고를 연결하고, 구조화된 조사 패키지(Investigation Package)를 생성할 수 있다. 그러나 사고 사이의 통계적 유사성(Statistical Similarity)이 동일한 근본 원인을 증명하는 것은 아니므로 자동화는 인과관계를 자동 결정하는 대신 엔지니어링 판단(Engineering Judgment)을 지원해야 한다.

피드백 프로세스는 개별 제품을 넘어 아키텍처(Architecture)와 플랫폼 의사결정(Platform Decision)까지 확장되어야 한다. 반복적인 통신 고장은 미들웨어(Middleware) 또는 네트워크 이중화(Network Redundancy)의 재설계를 요구할 수 있고, 반복적인 인식 취약점(Perception Weakness)은 센서 아키텍처(Sensor Architecture)의 변경으로 이어질 수 있으며, 반복되는 유지보수 문제는 기계적 모듈성(Mechanical Modularity)에 영향을 줄 수 있다. 여러 제품 세대에서 유사한 고장이 반복된다면 적절한 시정 조치는 또 하나의 국부적 패치(Local Patch)가 아니라 플랫폼 수준 설계 규칙(Platform-Level Design Rule)이 될 수 있다.

성숙한 고장 분석 피드백 루프(Failure-Analysis Feedback Loop)는 현장 운용을 지속적인 엔지니어링 증거(Engineering Evidence)의 원천으로 전환한다. 사고는 구조화된 데이터를 생성하고, 근본 원인 분석은 고장 메커니즘을 식별하며, 개발팀은 시정 변경을 구현하고, 검증 과정은 고장을 영구적인 시험으로 변환하며, 통제된 배포는 개선 사항을 다시 플릿에 적용하고, 모니터링은 그 결과를 검증한다. 운용 증거를 통해 신뢰성(Reliability), 안전성(Safety), 유지보수성(Maintainability), 시스템 성능(System Performance)이 실제로 향상되었음이 확인될 때 비로소 피드백 루프가 완성된다.

## 10.10. Field Failure Hall of Fame Lessons Learned

![](images/image10.png){width="7.268055555555556in" height="7.268055555555556in"}

현장 고장 명예의 전당(Field Failure Hall of Fame)은 중요한 엔지니어링 교훈을 제공한 대표적인 고장 사례를 구조화하여 수집한 것이다. 목적은 실수를 미화하거나 책임을 특정하는 것이 아니라 사고가 종료된 이후 사라질 수 있는 어려운 현장 운용 지식을 보존하는 데 있다. 각 사례에서는 무엇이 발생했는지, 정상적인 보호 체계가 왜 실패했는지, 시스템이 어떻게 복구되었는지, 어떤 증거를 통해 원인이 밝혀졌는지, 그리고 어떠한 영구적인 개선 사항이 도입되었는지를 설명해야 한다.

가장 가치 있는 사례가 반드시 수리 비용이 가장 높은 고장인 것은 아니다. 겉으로는 사소해 보이는 간헐적 결함(Intermittent Fault)이 전체 로봇 플릿에 영향을 미치는 진단(Diagnostics), 아키텍처(Architecture), 시험(Testing), 운용 절차(Operational Procedure)의 취약점을 드러낼 수 있다. 사례 선정에서는 안전 중요도(Safety Significance), 재발성(Recurrence), 진단 난이도(Diagnostic Difficulty), 다운타임(Downtime), 생산 영향(Production Impact), 예상하지 못한 상호작용(Unexpected Interaction), 향후 로봇 플랫폼과 배포 환경에 대한 교훈의 일반 적용 가능성(General Applicability)을 고려해야 한다.

간헐적인 전기 연결(Intermittent Electrical Connection)은 소프트웨어나 센서 문제와 유사한 증상을 만들 수 있기 때문에 대표적인 현장 고장 유형이다. 느슨한 커넥터(Loose Connector)는 정지 상태의 시험에서는 정상적으로 동작하지만 진동, 가속, 기계적 충격이 발생할 때 순간적으로 연결이 끊어질 수 있다. 로그에는 무작위로 발생하는 것처럼 보이는 센서 손실과 이후의 자동 복구(Automatic Recovery)가 기록될 수 있다. 여기에서 얻을 수 있는 교훈은 사라지는 센서 신호를 모두 소프트웨어 결함으로 판단하는 대신 커넥터 고정(Connector Retention), 진동 시험(Vibration Testing), 전기 진단(Electrical Diagnostics), 타임스탬프 기반 통신 모니터링(Timestamped Communication Monitoring)을 함께 적용해야 한다는 것이다.

시간 동기화 고장(Time Synchronization Failure)은 인프라 문제가 정상적으로 동작하는 개별 구성요소 전체로 어떻게 전파될 수 있는지를 보여준다. 카메라, 라이다(LiDAR), 관성 측정 장치(Inertial Measurement Unit, IMU), 제어기(Controller), 컴퓨팅 노드(Compute Node)는 각각 정상적으로 동작하더라도 서로 일치하지 않는 타임스탬프가 센서 융합(Sensor Fusion)이나 상태 추정(State Estimation)을 손상시킬 수 있다. 그 결과는 인식 또는 위치추정 불안정성과 유사하게 나타날 수 있다. 따라서 신뢰성 높은 로봇에는 명시적인 클록 모니터링(Clock Monitoring), 동기화 진단(Synchronization Diagnostics), 타임스탬프 검증(Timestamp Validation), 의도적으로 시간 오류를 주입하는 시험이 필요하다.

캘리브레이션 드리프트(Calibration Drift)는 또 다른 기만적인 고장 패턴을 제공한다. 카메라, 라이다, 관절 인코더(Joint Encoder), 조작 도구(Manipulation Tool)는 전기적으로 정상 상태를 유지하면서도 진동, 충격, 마모, 온도 변화, 유지보수 작업으로 인해 기하학적 관계(Geometric Relationship)가 점진적으로 변할 수 있다. 이 경우 일반적인 하드웨어 고장을 발생시키지 않으면서 인식 및 제어 오류가 증가할 수 있다. 따라서 캘리브레이션 유효성(Calibration Validity)은 단순한 설치 절차로만 취급하는 것이 아니라 지속적으로 감시해야 하는 운용 조건(Operational Condition)으로 관리해야 한다.

지도 및 설정 불일치(Map and Configuration Mismatch)는 소프트웨어 업데이트, 사이트 변경, 유지보수 이후 빈번하게 나타날 수 있다. 로봇이 유효하지만 잘못된 리비전(Revision)의 지도를 불러오거나 다른 하드웨어 구성을 위한 파라미터(Parameter)를 사용할 수 있다. 각각의 구성요소는 정상 상태를 보고하지만 통합된 시스템은 잘못 동작할 수 있다. 강력한 설정 식별(Configuration Identity), 호환성 검사(Compatibility Check), 배포 매니페스트(Deployment Manifest), 버전 추적성(Version Traceability), 시작 단계 검증(Startup Validation)은 이러한 종류의 고장에 대한 핵심 방어 수단이다.

메모리 누수(Memory Leak)와 자원 고갈(Resource Exhaustion)은 짧은 실험실 시험에서는 발견되지 않을 수 있는 고장을 보여준다. 내비게이션 또는 인식 프로세스가 수시간 동안 정상적으로 동작하면서 메모리, 파일 디스크립터(File Descriptor), GPU 자원, 통신 버퍼(Communication Buffer)를 서서히 소모할 수 있다. 수일 동안 운용된 이후에는 지연시간이 증가하거나 프로세스가 예상하지 못하게 종료될 수 있다. 따라서 단기간의 기능적 정확성(Functional Correctness)이 운용 안정성(Operational Stability)을 보장하지 않으므로 장시간 내구 시험(Long-Duration Endurance Testing)과 자원 추세 모니터링(Resource Trend Monitoring)이 필요하다.

네트워크 성능 저하(Network Degradation)는 통신을 단순히 연결 또는 단절의 이진 상태가 아니라 변화하는 운용 조건으로 취급해야 하는 이유를 보여준다. 패킷 손실(Packet Loss), 지터(Jitter), 혼잡(Congestion), 로밍 지연(Roaming Delay), 일시적인 액세스 포인트(Access Point) 문제는 완전한 연결 단절 이전부터 분산 로봇 기능을 불안정하게 만들 수 있다. 시스템은 성능이 저하된 통신 상태에서의 동작(Degraded Communication Behavior), 로컬 폴백 기능(Local Fallback Capability), 타임아웃 정책(Timeout Policy), 복구 절차(Recovery Procedure), 네트워크 증상과 애플리케이션 고장을 구분하는 텔레메트리를 정의해야 한다.

내비게이션 교착상태(Navigation Deadlock)는 개별 로봇 지능과 플릿 수준 조정(Fleet-Level Coordination)의 차이를 보여준다. 두 대의 로봇이 각각 로컬에서 유효한 충돌 회피 규칙(Collision-Avoidance Rule)을 따르더라도 좁은 통로나 공유 교차로에서 서로를 무기한 차단할 수 있다. 단순히 로컬 장애물 회피(Local Obstacle Avoidance)를 강화하는 것만으로는 이러한 문제를 반드시 해결할 수 없다. 교통 예약(Traffic Reservation), 우선순위 규칙(Priority Rule), 교착상태 탐지(Deadlock Detection), 경로 재설정(Rerouting), 플릿 수준 복구 정책(Fleet-Level Recovery Policy)을 적대적 다중 로봇 시나리오(Adversarial Multi-Robot Scenario)에서 검증해야 한다.

휠 슬립(Wheel Slip)과 변화하는 바닥 조건은 환경이 항상 일정하게 유지된다고 가정하는 것이 얼마나 위험한지를 보여준다. 먼지, 물, 오일, 경사로, 노면 전환(Surface Transition), 마모된 타이어, 변화하는 적재하중은 접지력(Traction)을 변화시키고 오도메트리(Odometry)와 제어에 사용되는 이동 가정을 무효화할 수 있다. 강건한 이동 로봇(Robust Mobile Robot)은 휠 오도메트리를 절대적인 이동 정보로 간주하는 대신 슬립 탐지(Slip Detection), 센서 융합, 적응형 제어 한계(Adaptive Control Limit), 환경 인식(Environmental Awareness), 복구 로직(Recovery Logic)을 결합해야 한다.

인식 도메인 시프트(Perception Domain Shift)는 개발 환경에서 우수한 성능을 보인 모델이 서로 다른 조명, 날씨, 배경, 객체 외형, 카메라 오염(Camera Contamination), 사이트 기하 구조(Site Geometry)를 만날 때 나타난다. 높은 벤치마크 정확도(Benchmark Accuracy)는 학습 분포(Training Distribution)를 벗어난 현장에서의 신뢰성 높은 성능을 보장할 수 없다. 고장 샘플은 데이터셋 관리(Dataset Management), 회귀 평가(Regression Evaluation), 신뢰도 모니터링(Confidence Monitoring), 통제된 모델 개선(Controlled Model Improvement)으로 다시 전달되어야 하며, 이를 통해 배포 경험이 검증된 운용 영역(Validated Operating Domain)을 점진적으로 확장하도록 해야 한다.

조작 고장(Manipulation Failure)은 시뮬레이션이나 정상 조건 시험에서 충분히 표현되지 않은 작은 물리적 변화에서 발생하는 경우가 많다. 포장 변형(Packaging Deformation), 객체 공차(Object Tolerance), 표면 마찰(Surface Friction), 그리퍼 마모(Gripper Wear), 적재하중 변화, 부정확한 자세 추정(Pose Estimation)은 안정적으로 동작하던 픽앤플레이스(Pick-and-Place) 시퀀스를 반복적인 미스(Miss)나 낙하(Drop)로 변화시킬 수 있다. 따라서 신뢰성 높은 조작을 위해서는 힘 및 접촉 피드백(Force and Contact Feedback), 파지 검증(Grasp Verification), 복구 전략(Recovery Strategy), 공차 인식 계획(Tolerance-Aware Planning), 이상적인 객체뿐만 아니라 현실적인 변동 조건을 포함하는 시험이 필요하다.

배터리 및 충전 고장(Battery and Charging Failure)은 에너지 관리(Energy Management)가 자율성(Autonomy)의 일부임을 보여준다. 오염된 충전 접점(Charging Contact), 커넥터 정렬 불량(Connector Misalignment), 배터리 노화(Battery Aging), 온도 제한(Temperature Limit), 부정확한 충전 상태 추정(State-of-Charge Estimation)은 내비게이션과 임무 소프트웨어가 정상적으로 동작하더라도 로봇을 운용 불가능하게 만들 수 있다. 충전 성공 여부를 명시적으로 검증하고, 에너지 여유량(Energy Margin)에 성능 저하를 반영하며, 플릿 스케줄링(Fleet Scheduling)에서는 계획 충전과 비정상적인 에너지 관련 다운타임을 구분해야 한다.

자동 복구(Automatic Recovery) 자체가 숨겨진 고장 원인이 될 수도 있다. 프로세스 재시작, 제어기 리셋(Controller Reset), 임무 재실행은 빠르게 운용을 복구할 수 있지만 반복적인 복구는 해결되지 않은 결함을 수주 동안 감출 수 있다. 하루에 20번 자동 복구되는 로봇을 반드시 정상 상태라고 볼 수는 없다. 복구 빈도(Recovery Frequency), 반복 경고(Repeated Warning), 리셋 원인(Reset Cause), 복구 사이의 시간(Time Between Recoveries)을 신뢰성 지표(Reliability Indicator)로 모니터링하고 심각한 고장이 발생하기 전에 조사를 시작해야 한다.

소프트웨어 및 모델 업데이트(Software and Model Update)는 또 다른 중요한 현장 교훈을 제공한다. 하나의 변경이 특정 결함을 수정하면서 다른 영역의 타이밍, 자원 사용량(Resource Usage), 인터페이스(Interface), 임계값(Threshold), 동작을 변경할 수 있다. 단위 시험(Unit Test)의 성공만으로 안전한 플릿 배포를 보장할 수 없다. 버전 관리된 산출물(Version-Controlled Artifact), 호환성 검사, 회귀 시험(Regression Testing), 단계적 롤아웃(Staged Rollout), 카나리 배포(Canary Deployment), 롤백 기능(Rollback Capability), 릴리스 후 모니터링(Post-Release Monitoring)은 정상적인 개선 과정에서 새롭게 유입되는 고장을 방어하는 수단을 제공한다.

사람의 개입(Human Intervention) 역시 중요한 고장 증거이다. 작업자는 공식적인 사고 기록을 생성하지 않은 상태에서 객체 위치를 조정하거나, 경로를 정리하거나, 임무를 재시작하거나, 센서를 조정하거나, 로봇을 수동으로 이동하여 취약한 로봇 동작을 보완하는 경우가 많다. 따라서 실제보다 플릿의 신뢰성이 높아 보일 수 있다. 개입 원인(Intervention Reason)과 개입 빈도(Intervention Frequency)를 기록해야 하며, 반복적인 사람의 지원은 기존 고장 로그에서 발견되지 않을 수 있는 자동화 공백(Automation Gap)을 식별하는 중요한 근거가 된다.

현장 고장 명예의 전당은 기술적 증거뿐만 아니라 해당 증거가 시정 조치(Corrective Action)로 전환된 판단 과정도 보존해야 한다. 각 사례에는 간결한 타임라인(Timeline), 관찰된 증상, 영향을 받은 구성(Affected Configuration), 관련 로그와 텔레메트리, 근본 원인(Root Cause), 기여 요인(Contributing Factor), 복구 방법(Recovery Method), 시정 변경(Corrective Change), 회귀 시험, 배포 후 결과(Post-Deployment Result)를 포함하는 것이 유용하다. 목적은 개발 과정과 분리된 극적인 사고 이야기를 보관하는 것이 아니라 재사용 가능한 엔지니어링 지식(Reusable Engineering Knowledge)을 구축하는 것이다.

현장 고장에서 얻을 수 있는 가장 중요한 교훈은 신뢰성(Reliability)이 개별적으로 신뢰할 수 있는 구성요소만으로 만들어지는 것이 아니라 전체 시스템에서 형성된다는 것이다. 하드웨어, 소프트웨어, 인공지능(AI), 타이밍(Timing), 네트워킹(Networking), 설정(Configuration), 인프라(Infrastructure), 유지보수(Maintenance), 환경(Environment), 사람의 운용(Human Operation)은 지속적으로 상호작용한다. 성숙한 조직은 기억할 가치가 있는 고장을 요구사항(Requirement), 설계 규칙(Design Rule), 진단 체계(Diagnostics), 영구 시험(Permanent Test), 모니터링 지표(Monitoring Indicator), 교육 자료(Training Material)로 전환하여 각각의 중요한 고장이 미래의 로봇 시스템을 더욱 강건하게 만들도록 한다.
