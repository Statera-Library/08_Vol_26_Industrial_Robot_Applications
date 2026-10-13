**Volume 26. Industrial Robot Applications**

# Chapter 01. Warehouse AMR Applications

## 01.01. Warehouse Automation Market and AMR Role

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

창고 자동화(Warehouse Automation)는 개별적인 자재 취급 장비 중심의 구조에서 재고 관리(Inventory Management), 운송(Transportation), 보관(Storage), 피킹(Picking), 포장(Packing), 출하(Shipping)를 연결하는 통합 운영 아키텍처(Integrated Operational Architecture)로 발전해 왔다. 자율이동로봇(Autonomous Mobile Robot, AMR)은 고정된 유도 경로(Fixed Guide Path)를 필요로 하지 않으면서 유연한 운송 기능을 제공하기 때문에 이러한 변화의 중요한 구성 요소가 되었다. 본 장의 구성에서 AMR은 이후 다루는 상품-작업자 시스템(Goods-to-Person System), 팔레트 운송(Pallet Transport), 플릿 통합(Fleet Integration), 교통 관리(Traffic Management), 충전(Charging), 안전(Safety) 기술의 기반 역할을 한다.

전자상거래(E-commerce)의 성장, 짧아진 배송 요구 시간, 재고관리단위(SKU) 다양성 증가, 주문량 변동은 창고 운영의 경제성을 변화시켰다. 수동 카트(Manual Cart), 지게차(Forklift), 컨베이어(Conveyor), 고정형 보관 시스템(Fixed Storage System)을 중심으로 설계된 기존 시설은 수요 패턴이 빠르게 변화할 경우 효과적으로 대응하기 어렵다. 따라서 자동화(Automation)는 최대 처리량(Throughput)뿐만 아니라 확장성(Scalability), 운영 유연성(Operational Flexibility), 신속한 구축(Rapid Deployment), 대규모 인프라 변경 없이 작업 흐름을 재구성할 수 있는 능력을 중요하게 고려한다.

창고 자동화(Warehouse Automation)는 물리 장비(Physical Equipment), 제어 소프트웨어(Control Software), 정보 시스템(Information System), 최적화 서비스(Optimization Service)의 계층 구조로 이해할 수 있다. 기업 수준에서는 창고관리시스템(Warehouse Management System, WMS)이 재고와 주문을 조정하고, 창고제어시스템(Warehouse Control System, WCS)과 창고실행시스템(Warehouse Execution System, WES)이 비즈니스 요구사항을 실제 운영 작업으로 변환한다. 물리 계층에서는 컨베이어, 자동보관시스템(Automated Storage System), 로봇 매니퓰레이터(Robotic Manipulator), 지게차, AMR이 자재 이동을 수행한다. AMR은 소프트웨어에서 생성된 운송 임무(Transport Mission)를 자율적인 물리 행동으로 변환하여 이러한 계층들을 연결한다.

AMR은 위치추정(Localization), 매핑(Mapping), 경로 계획(Path Planning), 장애물 감지(Obstacle Detection), 모션 제어(Motion Control)를 기반으로 이동한다는 점에서 기존의 고정 경로 자동화(Fixed-Path Automation)와 근본적으로 다르다. 자기 테이프(Magnetic Tape), 유도선(Wire), 영구적으로 정의된 트랙을 따라 이동하는 대신 AMR은 지도화된 환경(Mapped Environment)에서 자율적으로 주행하며 주변 조건이 변경되면 이동 궤적(Trajectory)을 조정할 수 있다. 이러한 특성은 사람, 팔레트, 카트, 지게차, 임시 보관 구역, 다른 로봇에 의해 사용 가능한 이동 공간이 지속적으로 변화하는 창고에 특히 적합하다.

AMR의 비즈니스 가치(Business Value)는 단순한 이동성(Mobility)보다 유연성(Flexibility)에서 발생한다. 컨베이어는 예측 가능한 대량 운송을 제공하지만 일반적으로 상당한 물리적 인프라가 필요하며 설치 후 이동하기 어렵다. 반면 AMR 플릿(AMR Fleet)은 로봇 추가, 지도 수정, 작업 할당 정책(Task Allocation Policy) 변경을 통해 단계적으로 확장할 수 있다. 이를 통해 창고 운영자는 전체 물류 인프라를 다시 구축하지 않고도 성장 단계에서 처리 능력을 증가시키거나 자재 흐름(Material Flow)을 재설계하고 기존 브라운필드 시설(Brownfield Facility)에 자동화를 도입할 수 있다.

AMR은 다양한 형태의 창고 운송 패턴(Warehouse Transportation Pattern)을 지원한다. 상품-작업자(Goods-to-Person, GTP) 운영에서는 로봇이 선반(Shelf), 랙(Rack), 토트(Tote), 컨테이너(Container)를 고정된 작업자 또는 로봇 피킹 스테이션(Robotic Picking Station)으로 운반한다. 다른 시스템에서는 개별 토트를 작업 셀(Work Cell) 사이에서 이동시키거나, 입고(Receiving), 보관(Storage), 생산(Production), 출하(Shipping) 영역 사이에서 팔레트를 운송하거나, 물류 경로를 따라 카트를 견인한다. 이러한 구조는 시장 환경에서 출발하여 상품-작업자 시스템 설계와 자율 팔레트 운송으로 발전하는 창고 AMR의 응용 흐름을 보여준다.

상품-작업자 자동화(Goods-to-Person Automation)는 작업자와 재고 사이의 전통적인 관계를 변화시킨다. 수동 창고(Manual Warehouse)에서는 작업자가 보관 위치 사이를 이동하는 데 상당한 시간을 소비하지만, AMR 기반 시스템은 재고를 지정된 피킹 스테이션(Picking Station)으로 이동시킬 수 있다. 목표는 단순히 작업자의 보행을 로봇 이동으로 대체하는 것이 아니다. 전체 시스템은 주문 배포(Order Release), 재고 가용성(Inventory Availability), 로봇 할당(Robot Assignment), 스테이션 처리 능력(Station Capacity), 보충(Replenishment), 혼잡(Congestion), 후속 포장 작업을 동기화하여 특정 공정의 개선이 다른 공정의 병목(Bottleneck)을 발생시키지 않도록 해야 한다.

팔레트 운송 AMR(Pallet-Transport AMR)은 또 다른 중요한 운영 계층을 담당한다. 입고 도크(Receiving Dock), 예비 보관 구역(Reserve Storage), 생산 버퍼(Production Buffer), 스테이징 영역(Staging Area), 출하 도크(Shipping Dock)에서는 반복적인 팔레트 이동이 필요하며, 전통적으로 이러한 작업은 사람이 운전하는 지게차에 의존해 왔다. 자율 팔레트 차량(Autonomous Pallet Vehicle)은 위치(Position), 임무 상태(Mission State), 적재 상태(Load Status), 예외 상황(Exception)을 감독 소프트웨어(Supervisory Software)에 보고하면서 이러한 작업을 지속적으로 수행할 수 있다. 효과적인 운영을 위해서는 신뢰성 높은 적재 감지(Load Detection), 도킹 정확도(Docking Accuracy), 내비게이션(Navigation), 교통 조정(Traffic Coordination), 인간 운전 장비와의 안전한 상호작용이 필요하다.

소프트웨어 통합(Software Integration)은 개별 AMR이 유용한 창고 자산(Warehouse Asset)이 될 것인지 단순히 독립된 이동 기계에 머무를 것인지를 결정한다. 창고관리시스템(WMS), 창고제어시스템(WCS), 플릿 관리자(Fleet Manager), 로봇 제어기(Robot Controller)는 주문, 우선순위, 위치, 자원 상태(Resource State), 작업 완료 이벤트(Completion Event)를 상호 교환해야 한다. 따라서 WMS/WCS 통합은 동적 슬롯팅(Dynamic Slotting), 경로 최적화(Route Optimization)와 함께 핵심적인 창고 AMR 기술이며, 로봇 배치는 보다 큰 소프트웨어 기반 물류 시스템(Software-Controlled Logistics System)의 일부로 이해해야 한다.

로봇 수가 증가할수록 플릿 관리(Fleet Management)의 중요성도 증가한다. 단일 AMR은 충돌 없는 로컬 경로(Local Path)를 계획할 수 있지만, 수백 대의 로봇이 독립적으로 움직이는 환경에서는 전역 조정(Global Coordination)이 부족할 경우 혼잡(Congestion), 자원 충돌(Resource Conflict), 교착상태(Deadlock)가 발생할 수 있다. 따라서 플릿 소프트웨어(Fleet Software)는 작업 할당(Task Allocation), 교통 제어(Traffic Control), 경로 예약(Route Reservation), 우선순위 관리(Priority Management), 혼잡 회피(Congestion Avoidance), 복구(Recovery)를 수행한다. 창고는 물리적 구조뿐만 아니라 스케줄링 정책(Scheduling Policy)에 의해 용량이 결정되는 공유 운송 네트워크(Shared Transportation Network)로 취급해야 한다.

동적 경로 최적화(Dynamic Route Optimization)는 운영 조건에 따라 로봇의 이동을 지속적으로 조정함으로써 이러한 개념을 확장한다. 교차로가 혼잡하거나, 엘리베이터가 사용 중이거나, 충전소가 붐비거나, 높은 우선순위의 임무가 시스템에 진입하는 상황에서는 기하학적으로 가장 짧은 경로(Shortest Geometric Route)가 반드시 가장 빠르거나 생산적인 경로는 아니다. 효과적인 최적화는 이동 시간(Travel Time), 대기열 길이(Queue Length), 로봇 가용성(Robot Availability), 임무 우선순위(Mission Priority), 배터리 상태(Battery State), 예상 교통량(Predicted Traffic)을 함께 고려하여 개별 로봇이 아니라 전체 플릿 수준의 처리량을 향상시킨다.

에너지 관리(Energy Management) 역시 시스템 수준의 핵심 요구사항이다. 배터리 기반 AMR은 생산적인 운영과 충전 요구사항 사이의 균형을 유지해야 하며, 충전이 제대로 조정되지 않으면 수요가 높은 시간대에 사용 가능한 플릿 용량(Fleet Capacity)이 감소할 수 있다. 충전 전략(Charging Strategy)은 충전 상태(State of Charge), 예상 작업량(Expected Workload), 임무 우선순위, 충전기 가용성(Charger Availability), 배터리 건전성(Battery Health), 예상 유휴 시간(Predicted Idle Period)을 고려할 수 있다. 따라서 충전소 관리(Charging Station Management)와 에너지 최적화(Energy Optimization)는 교통 관리와 함께 실용적인 AMR 플릿 운영의 핵심 요소가 된다.

실제 창고는 본질적으로 불확실한 환경이므로 예외 처리(Exception Handling)는 정상적인 내비게이션(Nominal Navigation)만큼 중요하다. 차단된 통로(Blocked Aisle), 잘못 배치된 팔레트, 손상된 적재물, 위치추정 실패(Localization Failure), 사용할 수 없는 작업 스테이션, 통신 중단(Communication Interruption), 접근할 수 없는 충전소는 정상적인 임무 완료를 방해할 수 있다. 따라서 산업용 AMR 소프트웨어(Industrial AMR Software)는 명시적인 복구 상태(Recovery State), 타임아웃 정책(Timeout Policy), 재계획 메커니즘(Replanning Mechanism), 운영자 에스컬레이션(Operator Escalation), 이벤트 로깅(Event Logging), 안전한 폴백 동작(Safe Fallback Behavior)을 갖추어야 한다. 운영 강건성(Operational Robustness)은 이러한 반복적인 장애에서 시스템이 얼마나 효과적으로 복구하는지에 의해 평가된다.

안전(Safety)은 모든 최적화 목표를 제한하는 핵심 경계 조건이다. 로봇 속도를 높이거나 분리 거리를 줄이면 처리량을 향상시킬 수 있지만, 창고 로봇은 작업자, 지게차, 카트, 기계, 시설 인프라와 공간을 공유한다. 따라서 안전 아키텍처(Safety Architecture)는 센싱(Sensing), 속도 제어(Speed Control), 보호 영역(Protective Field), 비상 정지(Emergency Stop), 고장 처리(Fault Handling), 운영 절차(Operational Procedure)를 통합적으로 조정해야 한다. ISO 3691-4와 같은 산업 안전 요구사항에 대한 대응은 선택적 기능이 아니라 실제 AMR 배치의 핵심 요소로 이해해야 한다.

창고 AMR의 경제성 평가(Economic Evaluation)는 로봇 구매 가격만이 아니라 전체 시스템 성능(Total System Performance)을 기준으로 수행해야 한다. 주요 평가 요소에는 노동력 활용(Labor Utilization), 처리량, 이동 거리(Travel Distance), 주문 사이클 시간(Order Cycle Time), 오류 감소(Error Reduction), 시설 변경 비용(Facility Modification Cost), 유지보수(Maintenance), 소프트웨어 통합, 충전 인프라, 플릿 감독(Fleet Supervision), 예상 가동률(Expected Utilization)이 포함된다. 특히 AMR은 제한된 규모의 플릿에서 시작하여 운영 효과와 수요가 명확해짐에 따라 단계적으로 확대할 수 있기 때문에 점진적인 자동화(Incremental Automation)에 적합하다.

AMR은 또한 창고 내 이동에 대한 디지털 표현(Digital Representation)을 생성한다. 각각의 임무에서는 타임스탬프(Timestamp), 이동 궤적(Trajectory), 대기 시간(Waiting Period), 교통 이벤트(Traffic Event), 배터리 상태, 고장(Fault), 작업 완료 기록(Completion Record)과 같은 데이터가 생성될 수 있다. 이러한 운영 데이터를 주문 및 재고 정보와 결합하면 혼잡 구역(Congestion Zone), 비효율적인 레이아웃(Inefficient Layout), 반복적인 예외 상황, 활용도가 낮은 자원을 파악할 수 있다. 따라서 로봇 플릿은 운송 시스템인 동시에 지속적인 창고 최적화(Continuous Warehouse Optimization)를 지원하는 분산 데이터 생성 플랫폼(Distributed Data-Generation Platform)이 된다.

보다 광범위한 로봇 소프트웨어 아키텍처(Robotics Software Architecture) 역시 이러한 시스템 관점을 강화한다. AMR용 ROS 2(ROS 2 for AMR), 플릿 API(Fleet API), 클라우드 플릿 서비스(Cloud Fleet Service), 산업용 내비게이션(Industrial Navigation), 다중 로봇 플릿 지능(Multi-Robot Fleet Intelligence)은 각각 미들웨어(Middleware), 통신(Communication), 내비게이션, 플릿 조정(Fleet Coordination) 계층에 분산된 기능이다. 따라서 실제 창고 AMR 애플리케이션은 하나의 로봇 알고리즘이 아니라 여러 소프트웨어 계층과 서비스를 통합하는 시스템으로 구축된다.

대규모 배치 환경에서 창고 자동화는 사이버-물리 오케스트레이션 문제(Cyber-Physical Orchestration Problem)로 발전한다. 수백 대의 로봇은 지속적으로 변화하는 주문에 대응하면서 보관 장비, 작업 스테이션, 자동문, 엘리베이터, 컨베이어, 매니퓰레이터, 작업자와 상호작용해야 한다. 중앙집중식 최적화(Centralized Optimization)는 전역적인 조정을 제공할 수 있으며, 개별 로봇은 인지(Perception), 장애물 회피(Obstacle Avoidance), 안전을 위한 로컬 자율성(Local Autonomy)을 유지한다. 따라서 성공적인 아키텍처는 기업 소프트웨어(Enterprise Software), 플릿 서비스(Fleet Service), 엣지 컴퓨팅(Edge Computing), 온보드 로봇 제어(Onboard Robot Control) 사이의 역할을 명확하게 분배해야 한다.

AMR의 전략적인 역할은 궁극적으로 창고 운송을 상대적으로 경직된 물리적 프로세스에서 프로그래밍 가능한 물류 역량(Programmable Logistics Capability)으로 전환하는 것이다. 비즈니스 요구사항이 변화함에 따라 임무(Mission), 우선순위(Priority), 경로(Route), 플릿 규모(Fleet Size), 운영 정책(Operating Policy)을 소프트웨어를 통해 변경할 수 있다. 이러한 소프트웨어 정의 유연성(Software-Defined Flexibility)은 AMR이 단순한 노동력 대체 수단을 넘어 중요한 이유이며, 디지털 창고의 의사결정이 실제 물리적 자재 흐름(Material Flow)에 직접 영향을 미칠 수 있도록 하는 이동형 실행 계층(Mobile Execution Layer)을 제공한다.

성숙한 창고 AMR 배치(Mature Warehouse AMR Deployment)는 자율 차량들의 단순한 집합이 아니라 하나의 통합 시스템(Integrated System)으로 이해해야 한다. 상품-작업자 운송(Goods-to-Person Transport), 팔레트 이동(Pallet Movement), 동적 경로 설정(Dynamic Routing), WMS/WCS 통합, 다중 로봇 교통 제어(Multi-Robot Traffic Control), 에너지 관리, 예외 복구(Exception Recovery), 안전이 하나의 조정된 아키텍처(Coordinated Architecture)로 작동해야 한다. 이러한 요소들은 창고 AMR 시스템이 소규모 자동화에서 수백 대 규모의 대형 플릿 운영(Large-Scale Fleet Operation)으로 확장되기 위해 필요한 핵심 기술적 기반을 형성한다.

## 01.02. Goods to Person GTP AMR System Design [w/Code]

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

상품-작업자(Goods-to-Person, GTP) 자동화는 작업자가 보관 통로를 이동하여 상품을 찾는 대신 재고를 작업자에게 이동시키는 방식으로 창고 피킹(Warehouse Picking)을 변화시킨다. 자율이동로봇(Autonomous Mobile Robot, AMR)은 선반(Shelf), 랙(Rack), 토트(Tote) 또는 기타 적재 운반체(Load Carrier)를 회수하여 지정된 피킹 스테이션(Picking Station)으로 운반한다. 시스템은 모바일 로보틱스(Mobile Robotics), 재고 관리(Inventory Management), 작업 스케줄링(Task Scheduling), 워크스테이션 제어(Workstation Control), 자재 흐름 최적화(Material-Flow Optimization)를 하나의 조정된 주문 이행 아키텍처(Fulfillment Architecture)로 통합한다.

GTP AMR 시스템은 일반적으로 보관 위치(Storage Location), 이동식 재고 운반체(Movable Inventory Carrier), AMR, 피킹 스테이션, 충전소(Charging Station), 플릿 관리 소프트웨어(Fleet-Management Software), 창고 정보 시스템(Warehouse Information System) 인터페이스로 구성된다. 각 구성 요소는 연속적인 주문 이행 사이클(Order-Fulfillment Cycle)에 참여한다. 창고관리시스템(Warehouse Management System, WMS)은 필요한 재고를 식별하고, 실행 계층(Execution Layer)과 플릿 계층(Fleet Layer)은 어떤 로봇이 해당 재고를 회수하고 운송 임무(Transport Mission)를 어떻게 수행할 것인지 결정한다.

운영 프로세스는 고객 주문(Customer Order) 또는 생산 주문(Production Order)이 피킹 작업(Picking Task)으로 변환되면서 시작된다. 필요한 재고관리단위(Stock Keeping Unit, SKU)는 실제 보관 위치 및 관련 선반 또는 토트와 매핑된다. 이후 시스템은 보관 위치와 적절한 피킹 스테이션을 연결하는 운송 임무를 생성한다. 각각의 로봇 임무를 독립적으로 처리하는 대신 스케줄러(Scheduler)는 주문 우선순위(Order Priority), 재고 위치(Inventory Location), 스테이션 작업량(Station Workload), 로봇 가용성(Robot Availability), 전체 창고 교통량(Warehouse Traffic)을 함께 고려해야 한다.

재고 운반체(Inventory Carrier)는 제품과 이동 로봇이 상호작용하는 방식을 결정하기 때문에 GTP 설계의 핵심 요소이다. 하나의 운반체에는 여러 개의 선반과 재고관리단위(SKU)가 포함될 수 있으며, 특정 제품군을 위한 토트 형태로 구성될 수도 있다. AMR과 운반체 사이의 기계적 인터페이스(Mechanical Interface)는 예상되는 가속(Acceleration), 회전(Turning), 바닥 불규칙성(Floor Irregularity), 적재 조건(Payload Condition)에서도 안정성을 유지하면서 신뢰성 있는 결합(Engagement), 운송, 위치 결정(Positioning), 분리(Release)를 지원해야 한다.

선반 기반 GTP 시스템(Shelf-Based GTP System)은 일반적으로 호환되는 보관 랙 아래로 이동할 수 있는 로봇을 사용한다. 지정된 랙에 도착하면 리프팅 메커니즘(Lifting Mechanism)이 적재물과 결합하고 운송이 가능하도록 충분한 높이까지 들어 올린다. 이후 AMR은 랙을 피킹 스테이션으로 운반하고 작업자가 접근할 수 있도록 정확하게 위치시킨 다음 필요한 피킹 작업이 완료될 때까지 대기한다. 작업이 완료되면 랙을 지정된 보관 위치로 반환한다. 이 전체 과정에서는 정확한 도킹(Accurate Docking)과 적재 감지(Load Detection)가 필수적이다.

토트 기반 GTP 아키텍처(Tote-Based GTP Architecture)는 다른 형태의 자재 흐름 모델(Material-Flow Model)을 사용한다. 전체 선반을 이동시키는 대신 로봇 또는 관련 자동화 설비가 필요한 제품이 포함된 컨테이너(Container)를 운송한다. 토트 이동은 개별 작업을 위해 이동해야 하는 재고의 양을 줄일 수 있으며 컨베이어(Conveyor), 로봇 피킹 셀(Robotic Picking Cell), 자동 보관 시스템(Automated Storage System), 분류 장비(Sorting Equipment)와 효과적으로 통합될 수 있다. 적절한 아키텍처는 SKU 특성, 주문 프로파일(Order Profile), 보관 밀도(Storage Density), 처리량 요구사항(Throughput Requirement), 시설 제약조건(Facility Constraint)에 따라 결정된다.

피킹 스테이션(Picking Station)은 단순한 로봇 목적지가 아니라 시스템의 핵심 자원(Critical System Resource)이다. 스테이션 설계는 작업자 생산성(Worker Productivity), 대기열 형성(Queue Formation), 로봇 활용률(Robot Utilization), 전체 주문 처리량(Order Throughput)에 영향을 준다. 스테이션에는 디스플레이(Display), 바코드 스캐너(Barcode Scanner), 픽투라이트(Pick-to-Light) 장치, 중량 센서(Weight Sensor), 확인 버튼(Confirmation Button), 안전 장치(Safety Device), 주문 관리 소프트웨어(Order-Management Software) 인터페이스가 포함될 수 있다. 작업자에게 제공되는 정보는 품목(Item), 수량(Quantity), 원본 위치(Source Location), 목적지 주문 컨테이너(Destination Order Container)를 명확하게 식별해야 한다.

스테이션 제어 워크플로(Station-Control Workflow)는 작업자의 행동과 로봇 임무를 동기화해야 한다. AMR이 도착하면 시스템은 재고 운반체를 확인하고 해당 피킹 지시(Picking Instruction)를 활성화한다. 작업자가 완료를 확인하면 재고 기록(Inventory Record)이 갱신되고 로봇은 다음 상태 전이(State Transition)를 수행한다. 품목이 없거나 손상되었거나 잘못 식별되었거나 예상 수량보다 부족한 경우에는 예외 처리 워크플로(Exception Workflow)를 통해 잘못된 재고 갱신을 방지하고 적절한 복구 동작(Recovery Action)을 결정해야 한다.

로봇 작업 할당(Robot Task Allocation)은 GTP 성능에 큰 영향을 미친다. 기본적인 스케줄러는 각 요청에 가장 가까운 가용 AMR을 할당할 수 있지만 시스템 규모가 커지면 이러한 전략은 비효율적일 수 있다. 보다 발전된 할당 방식은 예상 이동 시간(Estimated Travel Time), 로봇 배터리 상태(Robot Battery State), 현재 교통 상황(Current Traffic), 피킹 스테이션의 대기열 길이(Queue Length), 임무 우선순위(Mission Priority), 적재 호환성(Load Compatibility), 향후 작업 가능성(Future Task Opportunity)을 고려한다. 목표는 불필요한 이동을 최소화하면서 로봇과 워크스테이션의 활용률을 균형 있게 유지하는 것이다.

보관 위치 할당(Storage Assignment)과 동적 슬롯팅(Dynamic Slotting)은 로봇 스케줄링(Robot Scheduling)과 밀접하게 연결되어 있다. 자주 요청되는 재고는 처리량이 높은 피킹 스테이션 가까이에 배치할 수 있으며, 이동 빈도가 낮은 제품은 더 먼 보관 구역에 배치할 수 있다. 그러나 최적의 배치는 수요 변화에 따라 달라진다. 따라서 GTP 시스템은 주문 이력(Order History)과 현재 수요(Current Demand)를 활용하여 보관 구조를 지속적으로 재구성함으로써 함께 주문되는 빈도가 높은 제품과 수요가 높은 운반체의 운송 거리를 줄일 수 있다.

경로 계획(Path Planning)은 개별 로봇 수준과 플릿 수준(Fleet Level) 모두에서 수행되어야 한다. 각 AMR은 보관 위치와 피킹 위치 사이에서 안전한 경로를 확보해야 하지만, 여러 로봇이 동일한 교차로나 스테이션으로 집중되면 개별적으로 최적화된 경로가 오히려 혼잡(Congestion)을 발생시킬 수 있다. 플릿 교통 관리(Fleet Traffic Management)는 경로 구간(Path Segment)을 예약하고, 교차로 접근을 제어하며, 방향성 통로(Directional Lane)를 할당하고, 로봇 우선순위를 조정하거나 차량을 혼잡 구역 주변으로 우회시켜 예측 가능한 시스템 처리량을 유지할 수 있다.

창고 레이아웃(Warehouse Layout)은 이러한 경로 결정에 직접적인 영향을 미친다. 보관 통로(Storage Aisle), 교차 통로(Cross Aisle), 워크스테이션 접근 구역(Workstation Approach), 충전 구역(Charging Area), 유지보수 구역(Maintenance Zone), 비상 경로(Emergency Route)는 공유 운송 네트워크(Shared Transportation Network)의 일부로 설계되어야 한다. 좁은 통로는 보관 밀도를 높일 수 있지만 로봇의 추월이나 교행 기회를 감소시키며, 지나치게 넓은 공간은 보관 효율을 낮춘다. 따라서 효과적인 GTP 설계는 보관 용량(Storage Capacity), 로봇 접근성(Robot Accessibility), 교통 용량(Traffic Capacity), 작업자 접근성(Human Access), 안전 요구사항(Safety Requirement) 사이의 균형을 유지해야 한다.

대기열 관리(Queue Management)는 특히 피킹 스테이션 주변에서 중요하다. 하나의 스테이션으로 지나치게 많은 AMR을 보내면 로봇 혼잡이 발생하고 중요한 바닥 공간을 점유하지만, 너무 적은 로봇을 보내면 작업자가 재고 도착을 기다리게 된다. 스케줄링 소프트웨어(Scheduling Software)는 스테이션 서비스 시간(Station Service Time)을 예측하고 이에 따라 로봇 임무를 배포해야 한다. 버퍼 위치(Buffer Position)를 이용하여 제어된 대기 공간을 제공할 수 있지만, 과도한 버퍼링(Buffering)은 근본적인 조정 문제를 해결하기보다 스케줄링 비효율성을 감추는 결과를 가져올 수 있다.

배터리 관리(Battery Management) 역시 임무 스케줄링과 통합되어야 한다. 에너지가 부족한 로봇에는 임무 완료 전에 운행이 중단될 위험이 있는 작업을 할당해서는 안 된다. 반대로 불필요한 충전은 플릿 가용성(Fleet Availability)을 감소시킨다. 기회 충전(Opportunity Charging)은 자연스럽게 발생하는 유휴 시간을 활용할 수 있으며, 예측 충전(Predictive Charging)은 향후 작업량을 추정하여 수요가 증가하기 전에 충분한 수의 로봇을 준비할 수 있다. 따라서 충전 결정(Charging Decision)은 독립적인 하위 시스템으로 처리하기보다 작업 할당과 연계하여 조정해야 한다.

WMS와 WCS 통합(WMS and WCS Integration)은 비즈니스 주문과 실제 로봇 활동을 연결하는 정보 브리지(Information Bridge)를 제공한다. WMS는 재고와 주문 이행 로직(Fulfillment Logic)을 관리하며, 창고제어시스템(Warehouse Control System, WCS), 창고실행시스템(Warehouse Execution System, WES), 또는 플릿 관리자(Fleet Manager)는 장비 수준의 실행을 조정한다. 인터페이스는 일반적으로 임무 요청(Mission Request), 재고 식별자(Inventory Identifier), 출발 및 목적지 위치(Source and Destination Location), 우선순위, 장비 상태(Equipment State), 완료 이벤트(Completion Event), 예외 정보를 교환하여 물리적 운영과 디지털 기록이 지속적으로 동기화되도록 한다.

신뢰성 높은 시스템 설계(Reliable System Design)를 위해서는 모든 운송 임무에 대한 명확한 상태 관리(State Management)가 필요하다. 하나의 임무는 생성(Created), 할당(Assigned), 보관 위치로 이동(Navigating to Storage), 적재물 획득(Acquiring Load), 운송(Transporting), 대기(Queued), 도킹(Docked), 피킹(Picking), 복귀(Returning), 완료(Completed), 실패(Failed) 등의 상태를 거칠 수 있다. 상태 전이는 모두 기록되어야 하며 이를 통해 감독 소프트웨어(Supervisory Software)는 모든 주문과 로봇의 정확한 상태를 파악할 수 있다. 이는 특히 활성 임무 수행 중 통신 장애나 장비 중단이 발생하는 경우 중요하다.

예외 처리(Exception Handling)는 일반적인 경로 차단뿐만 아니라 다양한 비정상 상황을 처리해야 한다. 로봇이 랙을 정상적으로 획득하지 못하거나, 예상하지 못한 장애물을 만나거나, 위치추정 신뢰도(Localization Confidence)가 감소하거나, 이미 사용 중인 스테이션에 도착하거나, 불안정한 적재물(Unstable Load)을 감지하거나, 통신이 끊어질 수 있다. 복구 로직(Recovery Logic)은 임무를 재시도(Retry), 재계획(Replan), 재할당(Reassign), 안전 일시정지(Safe Pause) 또는 운영자에게 에스컬레이션할 것인지 결정해야 한다. 자동 복구(Automated Recovery)는 대규모 AMR 플릿을 관리하는 운영자의 부담을 감소시킨다.

안전 요구사항(Safety Requirement)은 기계적 아키텍처와 소프트웨어 아키텍처 모두에 영향을 미친다. AMR은 창고 작업자 주변에서 운행하므로 장애물을 감지하고, 속도를 제어하며, 보호 영역(Protective Zone)을 유지하고, 위험 조건이 감지되면 안전 상태(Safe State)로 전환해야 한다. 특히 피킹 스테이션은 작은 운영 공간에서 로봇과 사람이 상호작용하기 때문에 추가적인 주의가 필요하다. 내비게이션 효율성(Navigation Efficiency)이 안전 기능(Safety Function)보다 우선되어서는 안 되며, 플릿 수준의 스케줄링 역시 작업자의 로봇 노출을 증가시키는 교통 패턴을 의도적으로 생성하지 않아야 한다.

성능 평가(Performance Evaluation)는 로봇의 최대 속도가 아니라 전체 GTP 시스템을 대상으로 수행해야 한다. 중요한 측정 지표에는 시간당 처리 주문 수(Orders Processed per Hour), 스테이션별 피킹 수(Picks per Station), 로봇 활용률, 스테이션 활용률(Station Utilization), 평균 임무 시간(Average Mission Time), 대기열 시간(Queue Duration), 이동 거리, 혼잡 발생 빈도(Congestion Frequency), 충전 시간(Charging Time), 예외 발생률(Exception Rate), 주문 사이클 시간(Order Cycle Time)이 포함된다. 실제 시스템 병목이 워크스테이션 용량, 재고 가용성 또는 교통 혼잡에 있다면 로봇의 최대 속도를 높이더라도 전체 성능 향상은 제한적일 수 있다.

배치 규모가 증가하면 확장성(Scalability)이 핵심적인 설계 요소가 된다. 초기에는 로봇을 추가하면 운송 능력이 증가하지만 일정 수준을 넘어서면 추가 차량이 혼잡을 증가시키고 한계 생산성(Marginal Productivity)을 감소시킬 수 있다. 따라서 용량 계획(Capacity Planning)은 플릿 규모, 보관 레이아웃, 스테이션 수, 경로 용량(Path Capacity), 충전 인프라(Charging Infrastructure), 주문 프로파일 사이의 관계를 평가해야 한다. 시뮬레이션(Simulation)과 디지털 트윈 분석(Digital-Twin Analysis)을 활용하면 비용이 많이 드는 물리적 변경을 수행하기 전에 이러한 상호작용을 평가할 수 있다.

잘 설계된 GTP AMR 시스템은 궁극적으로 조정된 사이버-물리 주문 이행 플랫폼(Coordinated Cyber-Physical Fulfillment Platform)으로 동작한다. WMS의 의사결정은 재고 요구사항(Inventory Requirement)을 생성하고, 스케줄링 소프트웨어는 이를 임무로 변환하며, 플릿 서비스(Fleet Service)는 공유 자원을 조정하고, 자율 로봇은 실제 물리적 이동을 수행한다. 작업자는 피킹 스테이션과 예외 처리 워크플로를 통해 시스템에 계속 통합된다. 이러한 아키텍처는 불필요한 작업자 이동을 조정된 재고 이동(Orchestrated Inventory Movement)으로 대체하면서 변화하는 창고 수요에 대응할 수 있는 유연성을 유지한다.

따라서 GTP 자동화의 효과는 특정 로봇 하나의 성능보다 재고(Inventory), 스케줄링(Scheduling), 내비게이션(Navigation), 교통 관리(Traffic Management), 워크스테이션 설계(Workstation Design), 충전(Charging), 안전(Safety), 예외 복구(Exception Recovery)를 얼마나 효과적으로 통합하는가에 의해 결정된다. 이러한 시스템 관점(System Perspective)은 자율 팔레트 운송(Autonomous Pallet Transportation), 동적 슬롯팅(Dynamic Slotting), WMS/WCS 통합, 다중 AMR 교통 관리(Multi-AMR Traffic Management), 대규모 플릿 운영(Large-Scale Fleet Operation)으로 이어지는 후속 창고 AMR 응용 기술의 기반을 제공한다.

## 01.03. Autonomous Pallet Transport AMR Architecture [w/Code]

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

자율 팔레트 운송(Autonomous Pallet Transport)은 AMR 기술을 경량 토트(Tote)와 선반 이동에서 창고 및 공장 내부의 중량 단위 적재물(Heavy Unit Load) 운송으로 확장한다. 팔레트 AMR(Pallet AMR)은 모든 운송 작업에 사람이 운전하는 지게차를 사용하지 않고도 입고 도크(Receiving Dock), 보관 구역(Storage Zone), 생산 버퍼(Production Buffer), 스테이징 영역(Staging Area), 출하 위치(Shipping Location)를 연결한다. 이러한 아키텍처는 자율 내비게이션(Autonomous Navigation), 신뢰성 높은 팔레트 취급(Pallet Handling), 정밀 도킹(Precise Docking), 적재물 모니터링(Load Monitoring), 플릿 조정(Fleet Coordination), 산업 안전(Industrial Safety)을 통합해야 한다.

일반적인 팔레트 AMR 아키텍처(Pallet AMR Architecture)는 모바일 베이스(Mobile Base), 구동 시스템(Drive System), 조향 메커니즘(Steering Mechanism), 배터리 및 전력 전자장치(Power Electronics), 팔레트 취급 메커니즘(Pallet-Handling Mechanism), 안전 센서(Safety Sensor), 내비게이션 센서(Navigation Sensor), 온보드 컴퓨터(Onboard Computer), 안전 제어기(Safety Controller), 통신 인터페이스(Communication Interface)로 구성된다. 이러한 물리적 구성 요소는 위치추정(Localization), 인지(Perception), 계획(Planning), 모션 제어(Motion Control), 적재물 취급(Load Handling), 임무 실행(Mission Execution), 진단(Diagnostics), 플릿 및 창고 시스템과의 통신을 담당하는 계층형 소프트웨어(Layered Software)를 통해 통합된다.

기계적 아키텍처(Mechanical Architecture)는 팔레트 취급 방식에 따라 크게 달라진다. 일부 AMR은 호환되는 팔레트 또는 운반체 아래로 진입한 뒤 통합 리프팅 플랫폼(Integrated Lifting Platform)을 사용하여 들어 올리며, 다른 시스템은 자율 지게차(Autonomous Forklift)와 유사한 포크 메커니즘(Fork Mechanism)을 사용한다. 또 다른 설계에서는 롤러 컨베이어(Roller Conveyor), 이송 스테이션(Transfer Station), 고정식 팔레트 스탠드(Fixed Pallet Stand)와 연동한다. 각각의 구성은 차량 크기, 회전 반경(Turning Radius), 하중 중심(Load Center), 리프팅 높이(Lifting Height), 도킹 허용오차(Docking Tolerance), 적재 안정성(Payload Stability)에 서로 다른 요구사항을 발생시킨다.

적재 용량(Payload Capacity)은 시스템의 거의 모든 부분에 영향을 준다. 무거운 적재물을 운반하는 차량은 관성(Inertia)이 증가하고 더 긴 제동 거리(Braking Distance)가 필요하며 회전 과정에서 더 큰 횡방향 힘(Lateral Force)을 받을 수 있다. 따라서 제어기(Controller)는 무부하 상태와 최대 적재 상태의 AMR이 동일한 동적 거동(Dynamic Behavior)을 갖는다고 가정해서는 안 된다. 가속(Acceleration), 감속(Deceleration), 조향 속도(Steering Rate), 최대 속도(Maximum Velocity), 비상 정지 특성(Emergency Stopping Characteristic)은 감지되거나 추정된 적재 조건에 따라 조정되어야 한다.

적재 감지(Load Detection)는 이러한 적응형 동작(Adaptive Behavior)에 필요한 정보를 제공한다. 존재 감지 센서(Presence Sensor)는 팔레트가 정상적으로 획득되었는지 판단할 수 있으며, 중량 센서(Weight Sensor), 리프트 위치 센서(Lift-Position Sensor), 포크 센서(Fork Sensor), 모터 전류 측정(Motor-Current Measurement)을 통해 적재물에 관한 추가 정보를 확보할 수 있다. 시스템은 운송을 시작하기 전에 적재물이 정상적으로 획득되었는지 확인하고, 불완전한 결합(Incomplete Engagement), 과적(Overload), 예상하지 못한 적재물 이동(Unexpected Load Movement), 목적지에서의 팔레트 분리 실패 등을 감지해야 한다.

정밀 도킹(Precise Docking)은 자율 팔레트 운송에서 가장 까다로운 기능 가운데 하나이다. 일반적인 창고 내비게이션에서는 허용될 수 있는 위치 오차도 포크가 팔레트 개구부(Pallet Opening)에 진입하거나 차량이 컨베이어 인터페이스(Conveyor Interface)와 정렬되어야 하는 상황에서는 허용되지 않을 수 있다. 따라서 도킹 과정에서는 라이다(LiDAR), 카메라(Camera), 기준 마커(Fiducial Marker), 반사판(Reflector), 기하학적 특징(Geometric Feature) 또는 기타 기준 정보를 이용하여 목표 주변의 상대 위치(Relative Position)와 자세(Orientation)를 추정하는 로컬 정밀 제어 단계(Local Precision-Control Phase)를 사용하는 경우가 많다.

내비게이션 아키텍처(Navigation Architecture)는 일반적으로 전역 계획(Global Planning)과 로컬 모션 제어(Local Motion Control)를 분리한다. 전역 경로 계획기(Global Planner)는 창고 지도와 교통 제약조건(Traffic Constraint)을 이용하여 출발 구역과 목적지 구역 사이의 경로를 선택한다. 로컬 경로 계획기(Local Planner)는 주변 장애물에 대응하면서 실행 가능한 단기 모션 명령(Motion Command)을 생성한다. 모션 제어기(Motion Controller)는 차량 운동학(Vehicle Kinematics), 적재물에 따른 제한조건, 안전 제약조건(Safety Constraint), 도킹 요구사항을 만족하면서 이러한 명령을 조향 및 바퀴 구동 명령으로 변환한다.

위치추정(Localization)은 긴 창고 이동 경로뿐만 아니라 저속 정밀 작업 중에도 신뢰성을 유지해야 한다. 라이다 기반 위치추정(LiDAR-Based Localization)은 주변 환경의 기하학적 구조를 저장된 지도와 정합할 수 있으며, 휠 인코더(Wheel Encoder)와 관성 센서(Inertial Sensor)는 연속적인 움직임 추정(Motion Estimation)을 제공한다. 카메라 또는 랜드마크(Landmark)는 복잡한 환경에서 이러한 측정을 보완할 수 있다. 센서 융합(Sensor Fusion)은 단일 센서 방식에 대한 의존도를 줄이고 선반, 팔레트, 임시 물체로 인해 주변 환경이 변화하는 경우에도 보다 안정적인 자세 추정(Pose Estimation)을 제공한다.

팔레트 운송은 적재물로 인해 차량의 실질적인 외형 크기(Footprint)가 변화할 수 있으므로 추가적인 경로 계획 제약조건을 발생시킨다. 팔레트가 모바일 베이스(Mobile Base) 바깥쪽으로 돌출되면 벽, 랙, 기둥, 다른 차량과의 가용 간격(Clearance)이 감소할 수 있다. 따라서 경로 계획 소프트웨어(Path-Planning Software)는 로봇 섀시(Robot Chassis)만이 아니라 적재물을 포함한 전체 외형을 표현해야 한다. 회전 동작에서도 팔레트 돌출부(Pallet Overhang)와 스윕 볼륨(Swept Volume)을 고려하여 코너 구간에서 충돌이 발생하지 않도록 해야 한다.

임무 실행(Mission Execution)은 내비게이션과 자재 취급(Material Handling)을 상태 기반 워크플로(State-Driven Workflow)로 조정한다. 하나의 운송 요청은 할당(Assignment), 픽업 위치로 이동(Travel to Pickup), 도킹(Docking), 팔레트 획득(Pallet Acquisition), 적재 확인(Load Verification), 출발(Departure), 적재 운송(Loaded Transport), 목적지 접근(Destination Approach), 하역(Unloading), 분리 확인(Release Verification), 완료(Completion)의 과정을 거칠 수 있다. 명시적인 임무 상태(Mission State)를 사용하면 비정상 상황 발생 시 어떤 작업이 수행되고 있었는지를 감독 소프트웨어(Supervisory Software)가 정확하게 파악할 수 있어 고장 감지와 복구가 쉬워진다.

창고 통합(Warehouse Integration)은 WMS, WCS, WES, 제조 시스템(Manufacturing System) 또는 운영자 인터페이스(Operator Interface)가 팔레트 이동을 요청하면서 시작된다. 요청에는 일반적으로 출발 위치(Source), 목적지(Destination), 팔레트 또는 적재물 식별자(Load Identifier), 우선순위(Priority), 관련 취급 제약조건(Handling Constraint)이 포함된다. 플릿 소프트웨어(Fleet Software)는 요청을 로봇 임무로 변환하고 적절한 AMR을 선택하며 실행 과정을 모니터링하고 완료 또는 실패를 보고함으로써 디지털 재고 기록과 실제 팔레트 이동을 동기화한다.

플릿 할당(Fleet Allocation)은 단순히 픽업 위치까지의 거리만을 고려해서는 안 된다. 선택된 차량은 충분한 적재 용량, 호환 가능한 취급 장비(Compatible Handling Equipment), 충분한 배터리 에너지, 필요한 경로와 목적지에 대한 접근성을 갖추어야 한다. 작업 할당 알고리즘(Assignment Algorithm)은 교통 상황, 임무 마감시간(Mission Deadline), 충전 일정(Charging Schedule), 예상되는 향후 작업까지 추가로 고려할 수 있다. 이러한 요소는 서로 다른 종류의 AMR이 동일한 시설을 공유할수록 더욱 중요해진다.

팔레트 AMR은 많은 토트 운반 로봇보다 크고 기동성이 낮기 때문에 교통 관리(Traffic Management)가 매우 중요하다. 여러 대의 적재 차량이 동시에 접근하면 교차로(Intersection), 좁은 통로(Narrow Aisle), 스테이징 영역, 도크 접근 구역(Dock Approach)이 병목(Bottleneck)이 될 수 있다. 플릿 소프트웨어는 도로 구간(Road Segment)을 예약하고, 교차로 진입을 제어하며, 일방통행(One-Way Traffic)을 적용하고, 대기 구역(Waiting Zone)을 설정하며, 임무 우선순위를 조정하여 차량 사이의 안전거리를 유지하면서 교착상태(Gridlock)를 방지할 수 있다.

사람이 운전하는 지게차(Human-Operated Forklift)는 또 다른 수준의 불확실성을 발생시킨다. 중앙에서 조정되는 AMR과 달리 지게차는 예상하지 못한 순간에 이동 경로로 진입하거나, 통로에서 정지하거나, 후진하거나, 적재 구역을 일시적으로 차단할 수 있다. 팔레트 AMR은 이러한 차량을 감지하고 감속(Speed Reduction), 정지(Stopping), 재계획(Replanning)을 통해 안전하게 대응해야 한다. 플릿 수준에서는 운영 데이터를 이용하여 반복적으로 차단되는 구역을 식별하고 이를 경로 정책(Routing Policy)이나 시설 재설계(Facility Redesign)에 반영할 수 있다.

안전 아키텍처(Safety Architecture)는 일반적인 자율주행 소프트웨어가 실패하더라도 사람을 보호할 수 있을 정도로 독립적으로 구성되어야 한다. 안전 등급 스캐너(Safety-Rated Scanner), 비상 정지 회로(Emergency-Stop Circuit), 보호 영역(Protective Field), 속도 모니터링(Speed Monitoring), 제동 기능(Braking Function), 안전 제어기(Safety Controller)를 통해 작업자와 장비 주변에서 안전한 동작을 강제할 수 있다. 완전히 적재된 AMR은 안전하게 정지하기 위해 더 긴 거리가 필요할 수 있으므로 보호 영역은 차량 속도, 이동 방향, 회전 상태, 적재 상태에 따라 변경될 수 있다.

고장 처리(Failure Handling)는 복구 가능한 운영 예외(Recoverable Operational Exception)와 사람의 개입이 필요한 상태를 구분해야 한다. 일시적인 경로 차단은 대기 또는 재계획을 통해 해결할 수 있지만, 잘못 정렬된 팔레트(Misaligned Pallet), 불안정한 적재물(Unstable Load), 리프팅 메커니즘 고장(Lifting Mechanism Failure), 위치추정 손실(Localization Loss), 안전 제어기 고장(Safety-Controller Fault)은 차량을 제어된 안전 상태(Controlled Safe State)로 전환해야 할 수 있다. 명확한 고장 코드(Fault Code)와 복구 절차(Recovery Procedure)는 평균 복구 시간(Mean Time to Recovery)을 단축하고 운영자가 안전하지 않은 임시 해결책을 사용하는 것을 방지한다.

팔레트 운송 임무는 여러 외부 자원과 상호작용하는 경우가 많기 때문에 통신 신뢰성(Communication Reliability)이 중요하다. AMR은 이송 구역에 진입하기 전에 자동문(Automatic Door), 컨베이어, 리프트(Lift), 생산 셀(Production Cell), 스테이징 제어기(Staging Controller)로부터 허가를 받아야 할 수 있다. 인터페이스에는 응답 확인(Acknowledgment), 타임아웃(Timeout), 재시도(Retry), 상태 검증(State Validation), 멱등 명령(Idempotent Command)이 포함되어야 하며, 이를 통해 일시적인 네트워크 장애가 중복된 팔레트 이동이나 일관되지 않은 장비 상태를 발생시키지 않도록 해야 한다.

배터리 및 충전 전략(Battery and Charging Strategy)은 중량 적재 운송에서 증가하는 에너지 요구량을 반영해야 한다. 에너지 소비량(Energy Consumption)은 적재 중량, 이동 거리, 가속 프로파일(Acceleration Profile), 바닥 경사(Floor Slope), 대기 시간에 따라 달라진다. 플릿 소프트웨어는 현재 에너지로 임무를 완료하고 이후 충전소까지 이동할 수 있는지 추정할 수 있다. 예측 충전(Predictive Charging)은 수요가 낮은 시간대에 충전을 수행하면서 예상되는 팔레트 운송 피크 시간에 충분한 수의 차량을 가용 상태로 유지하도록 계획할 수 있다.

운영 텔레메트리(Operational Telemetry)는 지속적인 개선(Continuous Improvement)의 기반을 제공한다. AMR은 임무 시간(Mission Duration), 이동 거리, 적재 상태, 도킹 시도 횟수(Docking Attempt), 대기 시간, 배터리 소비량, 장애물 이벤트(Obstacle Event), 위치추정 품질(Localization Quality), 안전 정지(Safety Stop), 고장 이력(Fault History)을 기록할 수 있다. 이러한 기록을 창고 주문과 교통 정보에 연계하면 반복적인 병목, 비효율적인 경로, 문제가 발생하는 이송 스테이션, 장비 신뢰성 문제를 식별할 수 있다.

따라서 성능(Performance)은 차량 수준과 시스템 수준 모두에서 평가해야 한다. 차량 수준 측정 항목에는 도킹 정확도(Docking Accuracy), 정지 거리(Stopping Distance), 내비게이션 신뢰성(Navigation Reliability), 적재물 취급 성공률(Load-Handling Success Rate), 에너지 소비량이 포함된다. 시스템 수준 측정 항목에는 시간당 팔레트 이동 수(Pallet Moves per Hour), 임무 사이클 시간(Mission Cycle Time), 플릿 활용률(Fleet Utilization), 대기열 시간(Queue Duration), 혼잡 발생 빈도(Congestion Frequency), 예외 발생률(Exception Rate), 충전 가용성(Charging Availability), 수동 개입 없이 완료된 운송 요청 비율 등이 포함된다.

시뮬레이션(Simulation)과 디지털 트윈(Digital Twin) 환경은 팔레트 AMR이 생산 장비 및 작업자 주변에서 실제 운행되기 전에 배치 위험(Deployment Risk)을 줄일 수 있다. 엔지니어는 다양한 수요 시나리오에서 레이아웃(Layout), 회전 여유 공간(Turning Clearance), 교통 규칙(Traffic Rule), 플릿 규모(Fleet Size), 스테이션 처리 능력(Station Capacity), 임무 스케줄(Mission Schedule)을 평가할 수 있다. 하드웨어 인 더 루프 테스트(Hardware-in-the-Loop Testing)는 제어기와 인터페이스를 추가로 검증할 수 있으며, 단계적 현장 시운전(Staged Field Commissioning)을 통해 위치추정, 도킹, 적재물 취급, 안전 동작, 복구 절차를 최종 확인할 수 있다.

강건한 자율 팔레트 운송 아키텍처(Robust Autonomous Pallet Transport Architecture)는 궁극적으로 기계적 적재물 취급(Mechanical Load Handling), 인지, 위치추정, 내비게이션, 모션 제어, 안전, 플릿 관리, 창고 소프트웨어를 하나의 조정된 시스템으로 통합한다. AMR은 단순히 자율 지게차를 대체하는 장비가 아니라 더 넓은 창고 운영의 일부로 임무를 동적으로 할당하고 모니터링할 수 있는 소프트웨어 제어형 자재 흐름 자원(Software-Controlled Material-Flow Resource)이 된다.

이러한 아키텍처는 이후의 창고 자동화 기능을 위한 기술적 기반도 제공한다. 팔레트 이동이 디지털 방식으로 관리되는 임무(Digitally Managed Mission)로 표현되면 동적 슬롯팅(Dynamic Slotting)을 통해 재고의 최적 보관 위치를 결정할 수 있고, 경로 최적화(Route Optimization)를 통해 이동 거리와 혼잡을 줄일 수 있다. 또한 WMS/WCS 통합을 통해 비즈니스 프로세스와 물리적 프로세스를 조정하고, 다중 AMR 교통 관리(Multi-AMR Traffic Management)를 통해 개별 차량 중심의 자율 운송을 대규모 산업용 플릿(Large Industrial Fleet)으로 확장할 수 있다.

## 01.04. Dynamic Slotting and Route Optimization [w/Code]

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

동적 슬롯팅(Dynamic Slotting)과 경로 최적화(Route Optimization)는 재고가 어디에 보관되는지와 로봇이 해당 재고에 접근하기 위해 어떻게 이동하는지를 함께 조정하여 창고 AMR의 성능을 향상시킨다. 기존 슬롯팅(Traditional Slotting)은 제품을 비교적 고정된 위치에 배치하지만 수요(Demand), 주문 구성(Order Composition), 재고 수준(Inventory Level), 워크스테이션 작업량(Workstation Workload)은 지속적으로 변화한다. 동적 시스템(Dynamic System)은 운영 데이터를 활용하여 재고를 재배치하고 로봇 경로를 조정함으로써 전체 이동 거리, 혼잡(Congestion), 주문 이행 시간(Fulfillment Time)을 줄인다.

슬롯팅(Slotting)은 각각의 재고관리단위(Stock Keeping Unit, SKU), 토트(Tote), 팔레트(Pallet), 선반(Shelf), 이동식 재고 운반체(Mobile Inventory Carrier)에 할당할 물리적 보관 위치(Physical Storage Location)를 결정한다. 이러한 배치의 품질은 운송 작업량에 직접적인 영향을 준다. 자주 요청되는 재고가 피킹 또는 출하 구역에서 멀리 보관되면 장거리 임무가 반복적으로 발생하기 때문이다. 동적 슬롯팅은 보관 위치를 영구적인 속성이 아닌 최적화 변수(Optimization Variable)로 취급하여 운영 조건이 변화함에 따라 배치 결정을 변경할 수 있도록 한다.

수요 빈도(Demand Frequency)는 슬롯팅에서 가장 중요한 입력 정보 중 하나이다. 회전율이 높은 제품(Fast-Moving Product)은 처리량이 높은 피킹 스테이션(High-Throughput Picking Station) 가까이에 배치할 수 있으며, 회전율이 낮은 재고(Slow-Moving Inventory)는 상대적으로 먼 보관 구역을 사용할 수 있다. 그러나 주문 패턴에 제품 사이의 강한 연관성이 존재한다면 단순한 빈도 기반 분류(Frequency-Based Classification)만으로는 충분하지 않다. 개별 수요 빈도가 크게 다르더라도 함께 주문되는 제품은 서로 연계하여 배치하는 것이 유리할 수 있다.

주문 연관성 분석(Order Affinity Analysis)은 과거 및 현재의 주문 데이터를 분석하여 이러한 관계를 식별한다. 여러 SKU가 동일한 주문에서 반복적으로 함께 등장한다면 이들을 로봇의 전체 이동 거리를 줄일 수 있는 위치에 보관함으로써 주문 이행 효율(Fulfillment Efficiency)을 향상시킬 수 있다. 선반 기반 상품-작업자 시스템(Shelf-Based Goods-to-Person System)에서는 연관성을 기반으로 하나의 이동식 랙(Mobile Rack)에 배치할 제품을 결정할 수 있다. 토트 또는 팔레트 시스템에서는 보관 구역(Storage Zone), 보충 위치(Replenishment Position), 운송 임무 순서(Transport Mission Sequencing)에 이를 적용할 수 있다.

동적 슬롯팅은 제품의 물리적 제약조건(Physical Product Constraint)도 고려해야 한다. 중량(Weight), 크기(Dimension), 적층 가능성(Stackability), 취급 요구사항(Handling Requirement), 온도 조건(Temperature Condition), 위험물 규칙(Hazardous-Material Rule), 보관 장비와의 호환성(Compatibility)은 사용 가능한 위치를 제한할 수 있다. 이동 거리가 수학적으로 짧더라도 해당 위치가 적재물을 안전하게 수용할 수 없다면 의미가 없다. 따라서 최적화는 창고의 기하학적 구조와 자재 취급 요구사항이 정의하는 실행 가능 영역(Feasible Set) 안에서 수행되어야 한다.

보관 밀도(Storage Density)는 또 다른 상충관계(Tradeoff)를 발생시킨다. 수요가 높은 제품을 피킹 스테이션 주변에 집중시키면 명목상의 이동 거리(Nominal Travel Distance)는 줄어들지만 좁은 영역에 로봇 교통이 집중될 수 있다. 이로 인한 혼잡은 실제 임무 시간을 증가시키고 전체 처리량을 감소시킬 수 있다. 따라서 효과적인 슬롯팅은 거리뿐만 아니라 교통 용량(Traffic Capacity)도 고려해야 하며, 필요한 경우 사용 빈도가 높은 재고를 여러 접근 가능한 구역에 분산하여 특정 통로가 지속적인 병목(Bottleneck)이 되는 것을 방지해야 한다.

경로 최적화(Route Optimization)는 출발 위치와 목적지 위치가 결정된 이후 시작된다. 창고 지도(Warehouse Map)는 교차로(Intersection), 스테이션(Station), 보관 위치(Storage Position), 충전기(Charger), 이송 지점(Transfer Point)을 노드(Node)로 표현하고 이동 가능한 경로를 에지(Edge)로 표현하는 그래프(Graph)로 구성할 수 있다. 기본적인 경로 설정은 기하학적 거리를 최소화하지만 실제 운영에서는 예상 이동 시간(Expected Travel Time), 혼잡, 방향 제한(Direction Restriction), 안전 구역(Safety Zone), 일시적인 경로 차단(Temporary Blockage)에 따라 동적으로 비용을 부여할 수 있다.

다중 AMR 창고(Multi-AMR Warehouse)에서는 최단 경로(Shortest Path)가 항상 가장 빠른 경로는 아니다. 많은 로봇이 점유한 짧은 통로는 교통량이 적은 조금 더 긴 우회 경로보다 더 긴 지연을 발생시킬 수 있다. 따라서 동적 경로 설정(Dynamic Routing)은 현재 또는 예측된 상태에 따라 에지 비용(Edge Cost)을 갱신한다. 플릿 소프트웨어(Fleet Software)는 혼잡이 심각해지기 전에 차량을 다른 경로로 전환하여 사용 가능한 운송 네트워크의 용량을 보다 균등하게 활용하고 동일한 최단 경로로 로봇이 반복적으로 집중되는 것을 방지할 수 있다.

실시간 교통 정보(Real-Time Traffic Information)는 로봇 위치, 속도, 임무 대기열(Mission Queue), 예약된 경로 구간(Reserved Path Segment), 대기 이벤트(Waiting Event)에서 얻을 수 있다. 이러한 정보를 이용하면 플릿 관리자(Fleet Manager)는 교차로와 좁은 통로 주변의 혼잡을 추정할 수 있다. 교통량이 미리 정의되거나 학습된 임계값(Threshold)을 초과하면 해당 구역의 경로 비용을 증가시킬 수 있다. 새로운 임무는 대체 경로(Alternative Path)를 사용하도록 유도되고 이미 혼잡 구역에 진입한 로봇은 점진적으로 빠져나갈 수 있다.

경로 예약(Route Reservation)은 보다 결정론적인 조정 메커니즘(Deterministic Coordination Mechanism)을 제공한다. AMR은 제한된 경로 구간에 진입하기 전에 교통 관리자(Traffic Manager)에게 사용 권한을 요청할 수 있다. 해당 구간은 일시적으로 예약되어 서로 충돌할 수 있는 이동이 동시에 진입하지 못하도록 한다. 예약은 교차로, 좁은 통로, 도킹 접근 구간(Docking Approach), 기타 중요 자원(Critical Resource)에 적용할 수 있다. 핵심 과제는 안전을 위해 충분한 공간을 예약하면서도 네트워크 용량을 불필요하게 감소시키지 않는 것이다.

여러 공유 자원(Shared Resource)의 예약이 동시에 이루어지는 경우에는 교착상태 방지(Deadlock Prevention)를 고려해야 한다. 두 로봇이 각각 하나의 자원을 점유한 상태에서 상대방이 보유한 다른 자원을 기다리면 순환 대기(Circular Waiting)가 발생할 수 있다. 플릿 관리자는 예약 순서(Reservation Ordering)를 강제하거나, 제한 구역 진입을 제어하거나, 탈출 위치(Escape Location)를 유지하거나, 로봇이 진입 전에 전체 중요 구간(Critical Section)을 확보하도록 요구함으로써 이러한 상황을 방지할 수 있다.

임무 우선순위(Mission Priority)는 경로 설정에 또 다른 차원을 추가한다. 긴급한 생산 보충 작업(Production Replenishment Task)은 우선순위가 낮은 재고 재배치 임무(Inventory Relocation Mission)보다 빠른 접근이 필요할 수 있다. 경로 계획기(Route Planner)는 교차로 접근, 대기열 순서(Queue Ordering), 경로 비용 계산(Path Cost Calculation)에 우선순위를 반영할 수 있다. 그러나 높은 우선순위의 임무만 지속적으로 선호하면 낮은 우선순위의 작업이 기아 상태(Starvation)에 빠질 수 있으므로 작업이 무기한 연기되지 않도록 공정성 메커니즘(Fairness Mechanism)이 필요하다.

슬롯팅과 경로 설정은 각각의 최적화 결과가 서로의 문제 조건을 변화시키므로 독립적으로 최적화해서는 안 된다. 인기 재고를 특정 스테이션 가까이 이동하면 교통 분포(Traffic Distribution)가 변화하고, 혼잡한 경로는 원래 매력적이었던 보관 위치를 비효율적인 위치로 만들 수 있다. 통합 최적화(Integrated Optimization)는 보관 위치와 운송 비용(Transportation Cost)을 함께 평가한다. 이를 통해 재고와 스테이션 사이의 정적인 거리만 최소화하는 대신 시스템 수준의 주문 이행 비용(System-Level Fulfillment Cost)을 최소화하는 구성을 찾는다.

재슬롯팅(Re-Slotting) 자체에도 비용이 발생한다. 재고를 실제로 이동시켜야 하기 때문이다. 지나치게 빈번한 최적화는 충분한 미래 이익을 제공하지 못하면서 로봇 용량을 소비하는 재배치 임무(Relocation Mission)를 증가시킬 수 있다. 따라서 실용적인 시스템은 위치 변경으로 예상되는 이익과 재배치 거리(Relocation Distance), 작업자 또는 로봇의 작업량, 운영 중단 위험(Disruption Risk), 새로운 수요 패턴의 예상 지속시간을 비교해야 한다. 충분한 운영상의 이익이 예상되는 변경만 실행하는 것이 바람직하다.

예측 슬롯팅(Predictive Slotting)은 현재 주문에만 반응하는 대신 미래 수요를 예측함으로써 이러한 접근법을 확장한다. 과거 주문 패턴(Historical Order Pattern), 계절적 특성(Seasonal Behavior), 프로모션(Promotion), 생산 일정(Production Schedule), 시간대별 효과(Time-of-Day Effect)를 활용하여 어떤 재고의 중요도가 곧 증가할 것인지 예측할 수 있다. 로봇은 수요가 낮은 시간에 선택된 적재물을 미리 재배치하여 예상 작업량이 발생하기 전에 창고를 준비하고 피크 운영 시간(Peak Operation) 동안의 운송 부담을 줄일 수 있다.

경로 예측(Route Prediction) 역시 반응형 혼잡 회피(Reactive Congestion Avoidance)를 넘어설 수 있다. 현재 로봇의 임무 정보를 이용하면 몇 분 후 차량이 이동할 가능성이 높은 위치를 예측할 수 있다. 플릿 관리자는 앞으로 발생할 교차로 수요(Intersection Demand)를 추정하고 대기열이 형성되기 전에 경로를 조정할 수 있다. 이러한 예측 교통 관리(Predictive Traffic Management)는 혼잡이 직접 관찰될 때까지 기다릴 경우 지나치게 많은 로봇이 동일한 구역으로 진입할 수 있는 대규모 플릿(Large Fleet)에서 특히 유용하다.

배터리 상태(Battery State) 역시 최적화 과정에 포함되어야 한다. 이동 시간이 유사한 두 경로도 거리, 가속 빈도(Acceleration Frequency), 적재 중량(Payload), 바닥 상태(Floor Condition), 교통으로 인한 정지 횟수에 따라 서로 다른 에너지 비용(Energy Cost)을 가질 수 있다. 잔여 에너지가 적은 로봇은 임무를 완료하고 충전소까지 도달할 수 있도록 충분한 전력을 보존하는 경로가 필요할 수 있다. 반대로 에너지 여유가 큰 로봇은 전체 플릿의 혼잡을 감소시키기 위해 더 긴 우회 경로를 선택할 수 있다.

예외 상황(Exception Condition)이 발생하면 경로 비용과 보관 위치의 가용성(Storage Availability)을 즉시 변경해야 한다. 차단된 통로(Blocked Aisle), 사용할 수 없는 워크스테이션(Unavailable Workstation), 고장 난 충전기(Failed Charger), 유지보수 구역(Maintenance Zone), 안전 사고(Safety Incident)는 창고의 일부 영역을 정상 운영에서 일시적으로 제외할 수 있다. 지도와 자원 모델(Resource Model)은 이러한 변화를 반영하여 새로운 임무가 사용할 수 없는 영역을 회피하도록 해야 한다. 진행 중인 임무에는 재계획(Replanning)이 필요할 수 있으며 슬롯팅 로직은 일시적으로 접근할 수 없는 영역으로 재고를 이동시키지 않아야 한다.

최적화 알고리즘(Optimization Algorithm)은 실제적인 계산 제약조건(Computational Limit) 내에서 동작해야 한다. 대규모 창고에는 수천 개의 보관 위치와 수백 대의 로봇이 존재할 수 있으므로 모든 재고 배치와 경로를 동시에 최적화하면 조합 최적화 문제(Combinatorial Problem)가 발생한다. 계층형 전략(Hierarchical Strategy)을 사용하면 장기 슬롯팅(Long-Term Slotting), 중기 작업 계획(Medium-Term Task Planning), 실시간 경로 설정(Real-Time Routing)을 분리할 수 있다. 이후 휴리스틱(Heuristic), 그래프 탐색(Graph Search), 수학적 최적화(Mathematical Optimization), 시뮬레이션(Simulation), 학습 기반 방법(Learning-Based Method)을 각각 적절한 의사결정 시간 범위에 적용할 수 있다.

시뮬레이션과 디지털 트윈(Digital Twin)은 최적화 정책을 실제 창고에 적용하기 전에 평가하는 데 유용하다. 과거 주문 스트림(Historical Order Stream)을 다양한 슬롯팅 전략, 경로 비용, 플릿 규모, 교통 규칙에 적용하여 재생할 수 있다. 엔지니어는 처리량(Throughput), 이동 거리, 대기열 시간(Queue Time), 혼잡, 에너지 소비량(Energy Consumption), 재배치 작업량(Relocation Effort)을 비교할 수 있다. 이를 통해 국소적으로는 유리해 보이는 최적화 정책이 실제 배치 후 예상하지 못한 시스템 수준의 동작을 발생시키는 위험을 줄일 수 있다.

운영 지표(Operational Metric)는 겉으로 보이는 최적화 효과와 실제 효과를 구분할 수 있어야 한다. 평균 경로 거리(Average Route Distance)가 감소하더라도 혼잡이나 대기 시간이 증가하면 주문 이행 성능은 향상되지 않을 수 있다. 유용한 측정 지표에는 임무 사이클 시간(Mission Cycle Time), 적재 및 무적재 이동 거리(Loaded and Unloaded Travel Distance), 교차로 지연(Intersection Delay), 스테이션 대기 시간(Station Waiting Time), 로봇 활용률(Robot Utilization), 시간당 완료 주문 수(Orders Completed per Hour), 재배치 비용(Relocation Cost), 에너지 소비량, 교착상태 발생 빈도(Deadlock Frequency)가 포함된다. 최적화 목표는 단일 내비게이션 지표가 아니라 창고의 비즈니스 성과를 반영해야 한다.

지속적인 피드백(Continuous Feedback)을 활용하면 창고 조건이 변화하더라도 최적화 시스템을 지속적으로 개선할 수 있다. 임무 로그(Mission Log)는 실제 이동 시간, 반복적인 병목, 도킹 지연(Docking Delay), 일시적인 장애물, 계획 경로와 실제 실행 경로 사이의 차이를 보여준다. 주문 데이터는 SKU 수요와 연관성의 변화를 보여준다. 이러한 데이터 소스를 결합하면 슬롯팅 점수(Slotting Score), 그래프 비용(Graph Cost), 교통 정책(Traffic Policy), 수요 예측(Demand Forecast)을 주기적으로 재조정하여 최적화가 실제 운영 조건에 지속적으로 부합하도록 할 수 있다.

동적 슬롯팅과 경로 최적화는 궁극적으로 창고 레이아웃(Warehouse Layout)과 로봇 이동(Robot Movement)을 공동으로 관리되는 소프트웨어 자원(Software Resource)으로 전환한다. 재고 배치는 미래의 운송 수요를 결정하고 경로 설정은 해당 수요를 얼마나 효율적으로 처리할 수 있는지를 결정한다. 수요 예측(Demand Prediction), 보관 위치 할당(Storage Assignment), 작업 스케줄링(Task Scheduling), 교통 인식(Traffic Awareness), 적응형 경로 계획(Adaptive Path Planning)을 연결함으로써 AMR 플릿은 창고의 물리적 구조를 지속적으로 변경하지 않고도 변화하는 작업량에 대응할 수 있다.

이러한 기능은 보다 심층적인 창고 시스템 통합(Warehouse-System Integration)으로 발전하기 위한 중요한 연결 계층을 제공한다. 재고 위치와 로봇 경로를 동적으로 제어할 수 있게 되면 WMS와 WCS 인터페이스를 통해 실시간 비즈니스 우선순위(Real-Time Business Priority)를 제공하고, 플릿 관리(Fleet Management)를 통해 수백 개의 동시 임무를 조정하며, 충전(Charging)을 자원 최적화(Resource Optimization)에 포함할 수 있다. 또한 예외 처리(Exception Handling)를 통해 계획을 자동으로 변경할 수 있으므로 동적 최적화(Dynamic Optimization)는 확장 가능한 창고 AMR 운영을 위한 핵심 조정 계층(Coordination Layer)이 된다.

## 01.05. WMS WCS Integration with AMR Fleet [w/Code]

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

창고관리시스템(Warehouse Management System, WMS)과 창고제어시스템(Warehouse Control System, WCS)의 통합은 비즈니스 수준의 주문 이행 의사결정(Business-Level Fulfillment Decision)과 실제 AMR 실행(Physical AMR Execution)을 연결하는 소프트웨어 연결 구조를 제공한다. WMS는 어떤 재고를 이동해야 하는지 결정하고, WCS, 창고실행시스템(Warehouse Execution System, WES) 또는 플릿 관리자(Fleet Manager)는 이동을 언제 어떤 방식으로 수행할지 결정한다. 성공적인 아키텍처는 재고 정확성(Inventory Accuracy), 운영 우선순위(Operational Priority), 장비 상태(Equipment State)를 유지하면서 창고 주문을 로봇 임무(Robot Mission)로 변환한다.

WMS는 일반적으로 재고 기록(Inventory Record), 보관 위치(Storage Location), 주문 상태(Order Status), 할당 규칙(Allocation Rule), 보충 요구사항(Replenishment Requirement), 출하 우선순위(Shipping Priority)를 관리한다. WMS는 개별 모터 명령보다는 주문(Order), 재고관리단위(Stock Keeping Unit, SKU), 팔레트(Pallet), 토트(Tote), 위치(Location)와 같은 비즈니스 객체(Business Object)를 중심으로 동작한다. 자재 이동이 필요한 경우 WMS는 논리적 운송 요구사항(Logical Transport Requirement)을 생성하고, 하위 실행 계층(Lower Execution Layer)은 이를 AMR 및 기타 자동화 장비가 수행하는 물리적 작업으로 변환한다.

WCS는 물리적 장비에 보다 가까운 조정 계층(Coordination Layer)을 제공한다. WCS는 컨베이어(Conveyor), 분류기(Sorter), 자동 보관 시스템(Automated Storage System), 워크스테이션(Workstation), 자동문(Door), 리프트(Lift), 로봇 운송 자원(Robotic Transport Resource)을 관리하면서 운영 상태를 모니터링할 수 있다. AMR 환경에서는 WCS가 직접 플릿 임무(Fleet Mission)를 생성하거나 전용 플릿 관리자에게 운송 요청(Transport Request)을 전달할 수 있다. 이러한 분리를 통해 창고 로직(Warehouse Logic)은 개별 로봇의 내비게이션 및 제어 구현과 독립적으로 유지될 수 있다.

WES는 WMS의 계획과 WCS의 실행 사이에서 추가적인 오케스트레이션 계층(Orchestration Layer)을 제공할 수 있다. WES는 단순히 운송 요청을 전달하는 대신 주문, 인력(Labor), 워크스테이션 처리 능력(Workstation Capacity), 재고 가용성(Inventory Availability), 자동화 자원(Automation Resource)을 지속적으로 균형 조정할 수 있다. 고도로 자동화된 창고에서는 WMS, WES, WCS, 플릿 관리(Fleet Management) 기능의 구분이 구현 방식에 따라 달라질 수 있으므로 제품 명칭보다 의사결정 권한과 시스템 상태(System State)의 소유권을 명확하게 정의하는 것이 중요하다.

AMR 플릿 관리자(AMR Fleet Manager)는 운송 요구사항을 실행 가능한 로봇 임무(Executable Robot Mission)로 변환한다. 요청에는 출발 위치(Source Location), 목적지(Destination), 적재물 식별자(Load Identifier), 임무 유형(Mission Type), 우선순위(Priority), 시간 제약조건(Time Constraint), 취급 요구사항(Handling Requirement)이 포함될 수 있다. 플릿 관리자는 작업을 할당하기 전에 가용 로봇, 배터리 상태(Battery State), 적재 호환성(Payload Compatibility), 현재 교통 상황(Current Traffic), 자원 예약(Resource Reservation)을 평가한다. 이후 개별 AMR은 내비게이션과 자재 취급 작업(Material-Handling Action)을 수행하면서 진행 상태를 플릿 계층에 보고한다.

강건한 통합 아키텍처(Robust Integration Architecture)를 위해서는 일관된 위치 모델(Location Model)이 필요하다. WMS는 목적지를 비즈니스상의 보관 위치로 표현할 수 있지만 플릿 시스템은 이동 가능한 좌표(Navigable Coordinate), 도킹 자세(Docking Pose), 스테이션 식별자(Station Identifier)를 필요로 한다. 따라서 매핑 계층(Mapping Layer)은 논리적 창고 위치(Logical Warehouse Location)를 실제 로봇 목적지(Physical Robot Destination)와 연결한다. 랙, 스테이션 또는 시설 레이아웃이 변경될 경우 모든 시스템에서 해당 정보를 동기화하여 유효한 WMS 위치가 잘못된 로봇 임무를 생성하지 않도록 해야 한다.

적재물 식별 정보(Load Identity)는 전체 운송 과정에서 일관되게 유지되어야 한다. 팔레트, 토트, 랙, 카트(Cart), 컨테이너(Container)는 바코드(Barcode), RFID 식별자(RFID Identifier), 시스템 생성 ID(System-Generated ID)를 사용하여 표현할 수 있다. 픽업 전에 시스템은 예상된 적재물이 출발 위치에 존재하는지 확인할 수 있으며, 배송 이후에는 확인 절차를 통해 권위 있는 재고 상태(Authoritative Inventory State)를 갱신할 수 있다. 이를 통해 임무 실패 또는 작업자의 수동 개입(Manual Intervention)이 발생하더라도 실제 자재와 디지털 기록(Digital Record)이 서로 분리되는 것을 방지할 수 있다.

임무 수명주기 관리(Mission Lifecycle Management)는 신뢰성 높은 상태 동기화(State Synchronization)의 기반을 제공한다. 하나의 운송 요청은 생성(Created), 수락(Accepted), 할당(Assigned), 실행 중(Executing), 도착(Arrived), 완료(Completed), 취소(Canceled), 실패(Failed) 상태를 거칠 수 있다. 보다 세부적인 내부 로봇 상태(Internal Robot State)는 플릿 시스템 내부에 유지하고 비즈니스와 관련된 상태 전이(Business-Relevant Transition)만 상위 시스템에 보고할 수 있다. 명확하게 정의된 상태 의미(State Semantics)는 서로 다른 시스템이 동일한 임무를 다르게 해석하는 것을 방지하고 통신 중단 이후의 복구를 단순화한다.

시스템 사이의 인터페이스(Interface)는 지연시간(Latency), 신뢰성(Reliability), 레거시 시스템 요구사항(Legacy-System Requirement)에 따라 REST API, 메시지 브로커(Message Broker), 산업용 미들웨어(Industrial Middleware), 데이터베이스 통합(Database Integration), 표준화 프로토콜(Standardized Protocol)을 사용할 수 있다. 즉각적인 응답이 필요한 경우 동기식 요청(Synchronous Request)이 유용하며, 임무 진행 상황과 장비 상태 갱신에는 비동기 이벤트(Asynchronous Event)가 효과적이다. 현대적인 아키텍처는 명령에 명시적인 응답 확인(Acknowledgment)을 제공하면서 운영 이벤트는 느슨하게 결합(Loosely Coupled)될 수 있도록 두 가지 패턴을 함께 사용하는 경우가 많다.

메시지 설계(Message Design)는 추적성(Traceability)과 안전한 재시도 동작(Safe Retry Behavior)을 지원해야 한다. 각각의 요청에는 WMS, WCS, 플릿 관리자, 로봇 로그(Robot Log) 전체에서 추적할 수 있는 고유 식별자(Unique Identifier)가 포함되어야 한다. 명령은 타임아웃 이후 다시 전송하더라도 중복된 운송 임무가 생성되지 않도록 가능하면 멱등성(Idempotency)을 갖추어야 한다. 타임스탬프(Timestamp), 소스 시스템 식별자(Source-System Identifier), 시퀀스 정보(Sequence Information), 상관관계 ID(Correlation ID)는 지연되거나 중복되거나 일관성이 없는 창고 운영을 조사할 때 이벤트를 재구성하는 데 도움이 된다.

네트워크 통신이 항상 지속적으로 사용 가능하다고 가정할 수 없기 때문에 타임아웃 및 재시도 정책(Timeout and Retry Policy)이 필수적이다. WMS가 운송 요청을 전송한 후 응답을 받지 못했다고 해서 새로운 임무를 무조건 생성하면 중복 이동(Duplicate Movement)이 발생할 수 있다. 통합 계층(Integration Layer)은 재시도하기 전에 기존 요청이 이미 수락되었는지를 확인해야 한다. 영속적 대기열(Persistent Queue)과 지속성 있는 임무 기록(Durable Mission Record)을 사용하면 일시적인 통신 장애나 서비스 중단 이후에도 처리를 계속할 수 있다.

이벤트 기반 통합(Event-Driven Integration)을 사용하면 상위 시스템이 모든 로봇을 지속적으로 폴링(Polling)하지 않고도 물리적 상태 변화에 대응할 수 있다. 플릿 관리자는 임무가 수락되거나, 로봇이 스테이션에 도착하거나, 적재물을 획득하거나, 배송을 완료하거나, 고장이 발생하거나, 자원을 사용할 수 없게 되었을 때 이벤트를 발행할 수 있다. WCS 또는 WES 로직은 필요한 이벤트를 구독(Subscribe)하고 후속 작업을 실행함으로써 검증된 물리적 상태에 따라 자재 흐름이 진행되는 반응형 아키텍처(Responsive Architecture)를 구성할 수 있다.

AMR이 공유 장비(Shared Equipment)와 상호작용할 때는 자원 조정(Resource Coordination)이 필요하다. 자동문, 엘리베이터(Elevator), 컨베이어, 로봇 셀(Robotic Cell), 팔레트 이송 스테이션(Pallet Transfer Station)에 접근하는 로봇은 도착하기 전에 해당 자원을 예약해야 할 수 있다. WCS는 이러한 자원을 조정하고 이송 경로가 준비되었을 때 사용 권한을 제공할 수 있다. 핸드셰이크 시퀀스(Handshake Sequence)는 로봇과 장비의 상태를 모두 확인하여 AMR이 정확하게 위치하기 전에 컨베이어가 팔레트를 방출하는 상황을 방지해야 한다.

WMS의 주문 우선순위(Order Priority)는 플릿 스케줄링 동작(Fleet Scheduling Behavior)으로 신중하게 변환되어야 한다. 긴급 고객 주문(Expedited Customer Order), 생산 부족(Production Shortage), 긴급 보충 작업(Urgent Replenishment Task)은 우선적인 처리가 필요할 수 있으며 일반적인 재배치 작업(Relocation Task)은 대기할 수 있다. 플릿 관리자는 이러한 우선순위를 작업 할당과 교통 의사결정에 반영할 수 있지만 우선순위 정책(Priority Policy)은 낮은 우선순위 작업이 무기한 연기되지 않도록 해야 하며 안전 및 자원 제약조건과도 호환되어야 한다.

동적 슬롯팅(Dynamic Slotting)은 WMS 데이터와 AMR 실행 사이의 관계를 더욱 강화한다. 수요 패턴(Demand Pattern)과 재고 정책(Inventory Policy)을 통해 적절한 보관 위치를 식별할 수 있으며 플릿 시스템은 재배치 작업을 수행하는 데 필요한 운송 비용(Transportation Cost)을 추정할 수 있다. 재고 관리 관점에서는 최적으로 보이는 보관 결정도 과도한 로봇 교통을 발생시킬 수 있다. 따라서 시스템 통합을 통해 비즈니스 수준의 재고 최적화(Inventory Optimization)에 실제 운송 용량(Transportation Capacity)과 혼잡 정보를 반영할 수 있다.

예외 처리(Exception Handling)는 모든 소프트웨어 계층 사이에서 책임이 조정되어야 한다. AMR이 목적지에 도달하지 못하거나 적재물 획득에 실패하거나 안전하지 않은 상태를 감지하면 플릿 관리자는 임무를 조용히 종료하는 대신 구조화된 예외 정보(Structured Exception)를 보고해야 한다. WCS 또는 WES는 대체 스테이션(Alternative Station)이나 경로를 선택할 수 있으며, WMS는 실제 물리적 상태가 확인된 이후에만 재고 또는 주문 상태를 변경해야 한다. 이를 통해 디지털 상태(Digital State)와 물리적 상태(Physical State)가 서로 불일치하는 것을 방지할 수 있다.

수동 개입(Manual Intervention) 역시 명시적으로 표현되어야 한다. 운영자는 지게차를 이용하여 팔레트를 이동하거나, 스테이션에서 토트를 제거하거나, 차단된 통로를 정리하거나, 고장 난 로봇을 복구할 수 있다. 이러한 작업이 정보 시스템 외부에서 수행되면 재고와 임무 기록이 잘못될 수 있다. 따라서 운영자 인터페이스(Operator Interface)는 제어된 확인(Controlled Acknowledgment), 적재물 재할당(Load Reassignment), 임무 취소(Mission Cancellation), 재고 조정(Inventory Reconciliation)을 지원하여 사람에 의한 복구 작업이 통합 소프트웨어 아키텍처에 반영되도록 해야 한다.

플릿 상태(Fleet Status)는 창고 계획에 중요한 피드백을 제공할 수 있다. 로봇 가용성(Robot Availability), 대기열 길이(Queue Length), 혼잡 수준(Congestion Level), 충전 수요(Charging Demand), 스테이션 대기 시간(Station Waiting Time), 예상 임무 완료 시간(Estimated Mission Completion Time)을 WES 또는 WMS 로직에 제공할 수 있다. 이를 통해 주문 배포(Order Release)와 보충 의사결정(Replenishment Decision)이 실제 운송 용량을 반영할 수 있으며, AMR 플릿과 관련 스테이션이 효율적으로 처리할 수 있는 수준을 초과하는 작업이 특정 구역에 투입되는 것을 방지할 수 있다.

수백 대의 AMR이 빈번하게 상태 갱신(Status Update)과 임무 이벤트(Mission Event)를 생성하는 환경에서는 확장성(Scalability)이 중요하다. 모든 저수준 텔레메트리(Low-Level Telemetry)를 WMS로 전송하면 불필요한 부하와 강한 결합(Tight Coupling)이 발생한다. 계층형 아키텍처(Layered Architecture)는 로봇 데이터를 집계하고 각 소비자(Consumer)에게 필요한 정보만 제공해야 한다. 고주파 위치추정 데이터와 센서 데이터는 플릿 계층에 유지하고, 임무 상태, 처리 용량(Capacity), 예외, 비즈니스 이벤트(Business Event)는 창고 애플리케이션으로 전달하는 것이 적절하다.

창고 API는 실제 물리 장비의 동작에 직접적인 영향을 줄 수 있기 때문에 보안(Security) 역시 필수적인 통합 요구사항이다. 인증(Authentication), 권한 부여(Authorization), 암호화 통신(Encrypted Communication), 네트워크 분할(Network Segmentation), 자격 증명 관리(Credential Management), 감사 로깅(Audit Logging)을 통해 임무 인터페이스를 보호해야 한다. 시스템은 로봇 작업을 생성, 취소 또는 수정할 수 있는 서비스를 제한해야 한다. 사이버-물리 환경(Cyber-Physical Environment)의 보안 장애는 정보 기밀성뿐만 아니라 재고 무결성(Inventory Integrity), 생산 연속성(Production Continuity), 물리적 안전에도 영향을 줄 수 있다.

모니터링(Monitoring)은 애플리케이션, 통합, 운영 정보를 함께 제공해야 한다. 엔지니어는 API 지연시간(API Latency), 메시지 대기열(Message Queue), 실패한 트랜잭션(Failed Transaction), 임무 상태, 로봇 가용성, 장비 고장(Equipment Fault), 재고 동기화(Inventory Synchronization)를 확인할 수 있어야 한다. 분산 로깅(Distributed Logging)과 상관관계 식별자(Correlation Identifier)를 사용하면 하나의 창고 주문이 WMS에서 생성되어 WCS의 오케스트레이션을 거치고 플릿에서 실행된 후 최종 배송 확인에 도달하는 전체 과정을 추적할 수 있으므로 문제 해결 시간을 크게 단축할 수 있다.

통합 테스트(Integration Testing)는 성공적인 운송 시나리오만을 대상으로 해서는 안 된다. 중복 메시지(Duplicate Message), 응답 지연(Delayed Response), 네트워크 단절(Network Loss), 로봇 고장(Robot Failure), 사용할 수 없는 목적지(Unavailable Destination), 잘못된 적재물 식별(Incorrect Load Identity), 취소된 주문(Canceled Order), 수동 개입, 서비스 재시작(Service Restart)을 테스트해야 한다. 시뮬레이션(Simulation)과 하드웨어 인 더 루프(Hardware-in-the-Loop) 환경을 활용하면 실제 배치 전에 이러한 조건을 재현할 수 있다. 목표는 개별 구성 요소가 서로 다른 시점에 실패하거나 복구되더라도 전체 시스템 상태가 일관성을 유지하는지 검증하는 것이다.

성숙한 WMS-WCS-AMR 아키텍처(Mature WMS-WCS-AMR Architecture)는 비즈니스 계획(Business Planning), 실행 조정(Execution Coordination), 플릿 최적화(Fleet Optimization), 온보드 자율성(Onboard Autonomy) 사이에 명확한 경계를 설정한다. WMS는 재고와 주문 이행 의도(Fulfillment Intent)를 관리하고, WCS 또는 WES는 운영 자원을 조정하며, 플릿 관리자는 운송 수요를 최적화된 임무로 변환하고, 각각의 AMR은 물리적 이동을 안전하게 수행한다. 잘 정의된 인터페이스를 사용하면 모든 창고 애플리케이션을 특정 로봇 플랫폼에 강하게 결합하지 않고도 각 계층을 독립적으로 발전시킬 수 있다.

이러한 통합은 AMR 플릿을 단순한 자율주행 차량들의 집합에서 창고 전체의 실행 자원(Warehouse-Wide Execution Resource)으로 전환한다. 주문, 재고, 스테이션, 공유 장비, 교통, 충전, 예외 상황은 동기화된 디지털 상태(Synchronized Digital State)와 이벤트 기반 워크플로(Event-Driven Workflow)를 통해 서로 연결된다. 결과적으로 이러한 아키텍처는 다중 AMR 교통 관리(Multi-AMR Traffic Management), 자동 충전 조정(Automated Charging Coordination), 예외 복구(Exception Recovery), 안전 감독(Safety Supervision), 그리고 궁극적으로 수백 대의 로봇이 하나의 조정된 시스템으로 동작하는 대규모 창고 플릿(Large-Scale Warehouse Fleet)을 위한 기반을 제공한다.

## 01.06. Multi AMR Traffic Management and Deadlock [w/Code]

![](images/image6.png){width="7.268055555555556in" height="7.268055555555556in"}

다중 AMR 교통 관리(Multi-AMR Traffic Management)는 창고의 통로, 교차로, 스테이션, 충전 구역, 이송 구역을 공유하는 여러 자율 로봇의 이동을 조정한다. 각각의 AMR이 주변 장애물을 독립적으로 회피할 수 있더라도 로컬 충돌 회피(Local Collision Avoidance)만으로 효율적인 플릿 운영(Fleet Operation)을 보장할 수는 없다. 상위 수준의 조정이 없으면 개별적으로는 합리적인 이동이 혼잡(Congestion), 긴 대기열(Queue), 자원 충돌(Resource Conflict), 교착상태(Deadlock)를 발생시켜 전체 창고 처리량(Warehouse Throughput)을 감소시킬 수 있다.

창고 운송 네트워크(Warehouse Transportation Network)는 교차로, 스테이션, 대기 위치(Waiting Position), 도킹 구역(Docking Area), 기타 주요 위치를 노드(Node)로 표현하고 이동 가능한 경로를 에지(Edge)로 표현하는 그래프(Graph)로 구성할 수 있다. 교통 관리(Traffic Management)는 특정 노드나 에지를 로봇이 언제 점유할 수 있는지 제어함으로써 이러한 공유 그래프에서 동작한다. 목표는 단순히 물리적 충돌을 방지하는 것이 아니라 전체 플릿에서 예측 가능하고 효율적인 이동을 유지하는 것이다.

로봇 위치(Robot Position), 계획된 경로(Planned Route), 속도(Velocity), 임무 우선순위(Mission Priority), 적재 상태(Payload State), 목적지 대기열(Destination Queue)은 조정에 필요한 기본 정보를 제공한다. 플릿 관리자(Fleet Manager)는 이러한 상태를 결합하여 미래의 자원 수요(Resource Demand)를 추정한다. 두 로봇이 물리적으로 서로 접근한 이후에만 대응하는 대신 교통 시스템은 여러 경로 구간 이전부터 충돌 가능성을 식별하고, 해당 충돌이 즉각적인 내비게이션 문제가 되기 전에 일정이나 경로를 변경할 수 있다.

경로 예약(Path Reservation)은 공유 자원을 제어하기 위한 일반적인 메커니즘이다. AMR은 통로, 교차로 또는 제한 구역(Constrained Zone)에 진입하기 전에 필요한 경로 구간에 대한 접근 권한을 요청한다. 교통 관리자(Traffic Manager)는 충돌할 가능성이 있는 이동이 모두 해소된 경우에만 예약을 승인한다. 로봇이 해당 자원을 벗어나면 예약은 해제된다. 이러한 메커니즘은 물리적 이동을 제어된 자원 획득(Resource Acquisition)과 해제(Release)의 연속 과정으로 변환한다.

예약 세분성(Reservation Granularity)은 시스템 성능에 큰 영향을 준다. 매우 작은 영역만 예약하면 인프라 활용률(Infrastructure Utilization)을 높일 수 있지만 빈번한 조정이 필요하며 구역 경계에서 충돌 가능성이 증가할 수 있다. 반대로 긴 경로를 예약하면 예측 가능한 이동을 제공하지만 다른 로봇의 이동을 불필요하게 차단할 수 있다. 따라서 실제 시스템에서는 통로 구조(Aisle Geometry), 정지 거리(Stopping Distance), 교행 가능성(Passing Opportunity), 교차로, 운영 위험(Operational Risk)을 반영하여 창고를 적절한 교통 구간(Traffic Segment)으로 나눈다.

교차로(Intersection)는 여러 경로가 동일한 물리적 공간을 놓고 경쟁하기 때문에 특히 중요하다. 교통 제어기(Traffic Controller)는 교차로를 배타적 자원(Exclusive Resource)으로 취급하고 도착 시간(Arrival Time), 임무 우선순위, 대기 시간(Waiting Duration), 예상되는 하류 구간 가용성(Downstream Availability)에 따라 접근 권한을 부여할 수 있다. 로봇이 교차로를 완전히 빠져나갈 수 없는 경우에는 진입을 차단해야 한다. 그렇지 않으면 즉각적인 충돌이 발생하지 않더라도 차단된 하류 구간으로 차량이 진입하면서 교통 마비(Gridlock)가 발생할 수 있다.

좁은 통로(Narrow Aisle)에서는 로봇이 서로 안전하게 지나갈 수 없기 때문에 유사한 문제가 발생한다. 방향 제어(Directional Control)를 사용하면 기존 차량이 통로에서 모두 빠져나갈 때까지 하나의 이동 방향에 임시로 통로 사용 권한을 부여할 수 있다. 자재 흐름이 안정적인 시설에서는 영구적인 일방통행 경로(One-Way Route)를 사용하여 조정을 단순화하고 예측 가능성을 높일 수 있다. 그러나 과도한 방향 제한은 이동 거리를 증가시킬 수 있으므로 교통 규칙은 안전성과 플릿 수준의 운송 효율성을 함께 고려하여 평가해야 한다.

대기 구역(Waiting Zone)은 AMR이 주요 교통 경로를 방해하지 않고 정지할 수 있는 제어된 위치를 제공한다. 이러한 위치는 피킹 스테이션(Picking Station), 팔레트 이송 지점(Pallet-Transfer Point), 엘리베이터(Elevator), 사용 빈도가 높은 교차로 주변에서 유용하다. 플릿 관리자는 로봇이 공유 통로에서 임의로 대기하는 것을 방지해야 한다. 명확하게 정의된 대기열 및 스테이징 위치(Staging Location)는 교통 동작을 더욱 예측 가능하게 만들고 일시적인 수요 증가를 관리하기 위한 알려진 용량(Known Capacity)을 스케줄러에 제공한다.

혼잡(Congestion)은 로봇이 물리적으로 안전한 상태를 유지하면서도 시스템 성능이 저하될 수 있다는 점에서 충돌(Collision)과 다르다. 특정 구역에 지나치게 많은 AMR이 존재하면 반복적인 정지, 낮은 평균 속도(Average Velocity), 증가하는 대기열이 발생할 수 있다. 혼잡 모니터링(Congestion Monitoring)은 로봇 밀도(Robot Density), 구간 점유율(Segment Occupancy), 대기 시간, 평균 속도, 예약 지연(Reservation Delay)을 활용할 수 있다. 이러한 지표가 임계값을 초과하면 해당 구역의 경로 비용(Route Cost)을 높여 새로운 임무가 과부하된 영역을 회피하도록 할 수 있다.

동적 경로 설정(Dynamic Routing)을 사용하면 교통 관리자가 차량을 여러 대체 경로(Alternative Path)로 분산시킬 수 있다. 기하학적으로 가장 짧은 경로라도 교차로가 심하게 점유되어 있다면 비효율적일 수 있다. 예상 지연(Predicted Delay)을 경로 비용에 포함하면 경로 계획기(Route Planner)는 일부 로봇을 더 길지만 혼잡이 적은 경로로 이동시킬 수 있다. 목표는 각각의 로봇이 이동하는 거리를 독립적으로 최소화하는 것이 아니라 플릿 수준의 전체 이동 시간과 대기 시간을 최소화하는 것이다.

교착상태(Deadlock)는 여러 로봇이 각각 다른 로봇이 점유하거나 차단한 자원을 기다리면서 더 이상 진행할 수 없는 심각한 상태이다. 단순한 예로 두 대의 AMR이 좁은 통로의 서로 반대쪽에서 진입하여 서로 지나가거나 후퇴할 공간이 없는 상황이 있다. 보다 복잡한 교착상태에서는 여러 로봇이 서로 다른 교차로나 경로 구간을 점유하면서 자신이 요청한 자원 사이에 순환 의존성(Circular Dependency)을 형성할 수 있다.

교착상태 분석(Deadlock Analysis)은 자원 할당 관계(Resource-Allocation Relationship)를 이용하여 설명할 수 있다. 각 로봇은 하나 이상의 교통 자원(Traffic Resource)을 점유하면서 경로를 계속 진행하기 위해 필요한 추가 자원을 요청한다. 이러한 의존 관계가 순환 구조를 형성하고 참여하는 어떤 로봇도 현재 자원을 해제할 수 없다면 진행이 중단된다. 이러한 대기 관계 순환(Wait-For Cycle)을 탐지하면 플릿 관리자는 실제 교착상태와 적어도 하나의 로봇이 결국 이동할 수 있는 일시적인 혼잡을 구분할 수 있다.

교착상태 예방(Deadlock Prevention)은 위험한 자원 구성이 발생하지 않도록 하는 것을 목표로 한다. 로봇이 진입하기 전에 전체 제한 구간(Constrained Section)을 예약하도록 요구하거나, 미리 정의된 순서에 따라 자원을 획득하게 하거나, 용량 규칙(Capacity Rule)을 적용하여 최소 하나의 탈출 위치(Escape Position)를 유지할 수 있다. 이러한 방법은 순환 대기 발생 가능성을 줄이지만 지나치게 보수적인 예약은 필요한 범위보다 더 많은 인프라를 차단하여 교통 용량을 감소시킬 수 있다.

교착상태 회피(Deadlock Avoidance)는 현재 플릿 상태를 이용하여 요청된 예약을 승인했을 때 미래에 위험한 구성이 발생할 가능성이 있는지를 판단한다. 교통 관리자는 이동을 승인하기 전에 남아 있는 가용 자원(Free Resource), 로봇 경로, 이용 가능한 탈출 경로(Escape Path)를 평가할 수 있다. 이러한 방식은 엄격한 예방 규칙보다 높은 자원 활용률을 달성할 수 있지만 더 많은 계산이 필요하고 계획된 로봇 이동에 대한 정확한 정보가 요구된다.

모든 잠재적 충돌을 사전에 방지하는 것이 지나치게 제한적일 경우 교착상태 탐지 및 복구(Deadlock Detection and Recovery)를 사용할 수 있다. 시스템은 주기적으로 대기 관계를 분석하고 예상 범위를 초과하여 차단된 로봇을 식별한다. 교착상태가 확인되면 특정 로봇을 양보 로봇(Yielding Robot)으로 선택하여 안전한 위치로 후진시키거나, 예약을 해제하거나, 재계획된 경로(Replanned Route)를 적용함으로써 순환 의존성을 해소할 수 있다.

어떤 로봇이 양보해야 하는지를 선택할 때는 운영 비용(Operational Cost)을 고려해야 한다. 경량 적재물을 운반하거나 우선순위가 낮은 로봇은 긴급 생산용 팔레트를 운반하는 AMR보다 적절한 복구 대상이 될 수 있다. 가장 가까운 후퇴 위치(Retreat Position)까지의 거리, 배터리 수준(Battery Level), 적재물, 임무 우선순위, 대기 시간, 하류 작업에 미치는 영향(Downstream Impact)을 의사결정에 반영할 수 있다. 여러 로봇이 독립적으로 서로 충돌하는 탈출 동작을 시도하지 않도록 복구 과정은 충분히 결정론적(Deterministic)이어야 한다.

우선순위 관리(Priority Management)는 일반적인 충돌을 해결하는 데 도움이 되지만 신중하게 제어해야 한다. 긴급 임무(Emergency Mission) 또는 시간 제약이 큰 임무(Time-Critical Mission)는 교차로와 공유 경로에 우선적으로 접근할 수 있으며, 일반적인 재배치 임무(Relocation Mission)는 대기할 수 있다. 그러나 높은 우선순위가 지속적으로 선호되면 낮은 우선순위의 로봇이 지나치게 오랫동안 차단되는 기아 상태(Starvation)가 발생할 수 있다. 에이징 메커니즘(Aging Mechanism)을 사용하면 대기 중인 임무의 실질적인 우선순위를 점진적으로 높여 공정성(Fairness)을 유지할 수 있다.

교통 조정(Traffic Coordination)은 서로 다른 종류의 로봇(Heterogeneous Robot)도 고려해야 한다. 하나의 창고에는 소형 토트 AMR, 선반 운반 로봇(Shelf Carrier), 팔레트 로봇(Pallet Robot), 자율 지게차(Autonomous Forklift), 사람이 운전하는 차량이 함께 존재할 수 있다. 이러한 플랫폼은 외형 크기(Footprint), 회전 반경(Turning Radius), 속도, 제동 거리(Braking Distance), 적재 특성(Payload Characteristic)이 서로 다르다. 따라서 예약 및 안전 여유 공간 계산(Clearance Calculation)은 모든 로봇이 동일한 공간을 필요로 한다고 가정하지 않고 실제 차량 종류를 반영해야 한다.

사람의 활동(Human Activity)은 플릿 예약만으로 관리할 수 없는 불확실성을 발생시킨다. 작업자, 지게차, 카트 또는 임시 장애물(Temporary Obstacle)은 AMR을 위해 이미 예약된 경로를 차단할 수 있다. 온보드 안전 시스템(Onboard Safety System)은 즉각적인 충돌 방지를 담당하고, 플릿 계층은 장시간 지속되는 차단을 교통 이벤트(Traffic Event)로 해석한다. 이후 예약을 해제하거나 경로를 다시 계산하여 대기열이 창고 전체로 확산되는 것을 방지할 수 있다.

교통 제어는 정확한 자원 점유 상태(Resource Ownership)에 의존하므로 통신 지연(Communication Delay)과 로봇 고장(Robot Failure)도 고려해야 한다. 로봇이 예약된 구간을 점유한 상태에서 통신이 끊어지더라도 플릿 관리자는 해당 자원이 즉시 비어 있다고 가정해서는 안 된다. 안전 상태 정책(Safe-State Policy), 하트비트 모니터링(Heartbeat Monitoring), 예약 타임아웃(Reservation Timeout), 명확한 복구 절차(Recovery Procedure)가 필요하다. 점유 가능성이 있는 경로를 정상 운영으로 복귀시키기 전에 물리적 확인(Physical Confirmation)이 필요할 수도 있다.

교통 관리는 임무가 할당된 이후에만 동작하는 것이 아니라 작업 할당(Task Allocation)과 통합되어야 한다. 혼잡한 동일 구역의 목적지로 여러 로봇을 동시에 할당하면 경로 설정을 시작하기도 전에 불필요한 교통을 발생시킬 수 있다. 혼잡 인식 스케줄러(Congestion-Aware Scheduler)는 예상 운송 비용(Predicted Transportation Cost)을 작업 할당에 반영하여 로봇과 스테이션 사이에 임무를 분산한다. 이를 통해 운영 자원과 운송 네트워크 전체에서 작업량을 균형 있게 유지할 수 있다.

혼잡과 교착상태는 여러 차량이 상호작용할 때 나타나는 경우가 많기 때문에 다중 AMR 교통 설계에는 시뮬레이션(Simulation)이 특히 중요하다. 디지털 창고 모델(Digital Warehouse Model)은 플릿 규모, 교차로 규칙(Intersection Rule), 예약 정책(Reservation Policy), 경로 비용, 대기 구역 용량을 변경하면서 실제 주문 흐름(Order Stream)을 재현할 수 있다. 엔지니어는 로봇을 추가하더라도 처리량이 더 이상 증가하지 않거나 과도한 교통 간섭(Traffic Interference)으로 오히려 성능이 감소하는 포화 지점(Saturation Point)을 식별할 수 있다.

유용한 성능 지표(Performance Metric)에는 평균 임무 시간(Average Mission Time), 이동 시간(Travel Time), 대기 시간(Waiting Time), 교차로 지연(Intersection Delay), 예약 지연시간(Reservation Latency), 로봇 활용률(Robot Utilization), 구간 점유율(Segment Occupancy), 혼잡 발생 빈도(Congestion Frequency), 교착상태 발생 빈도(Deadlock Frequency), 복구 시간(Recovery Duration), 시간당 완료 임무 수(Completed Missions per Hour)가 포함된다. 이러한 지표는 함께 분석해야 한다. 교착상태를 최소화하더라도 지나치게 긴 대기 시간을 발생시키는 정책은 드물게 복구 가능한 충돌을 허용하면서 훨씬 높은 처리량을 제공하는 정책보다 운영 측면에서 더 비효율적일 수 있다.

대규모 플릿(Large Fleet)에서는 수백 대의 로봇 사이의 모든 상호작용을 지속적으로 계획하는 데 상당한 계산 비용이 필요하기 때문에 확장 가능한 조정(Scalable Coordination)이 요구된다. 계층형 교통 관리(Hierarchical Traffic Management)는 창고를 여러 구역으로 분할하고 각 구역 내부의 로컬 이동을 조정하면서 구역 경계(Regional Boundary)를 통과하는 이동을 별도로 관리할 수 있다. 상위 수준의 경로 설정(High-Level Routing)은 전역적인 교통 분산(Global Traffic Distribution)을 담당하고, 하위 수준 제어기는 작은 운영 구역 내에서 세부적인 예약과 이동을 해결한다.

성숙한 다중 AMR 교통 시스템(Mature Multi-AMR Traffic System)은 그래프 기반 경로 설정(Graph-Based Routing), 자원 예약(Resource Reservation), 혼잡 모니터링, 우선순위 제어(Priority Control), 교착상태 예방, 탐지, 복구를 통합한다. 온보드 자율성(Onboard Autonomy)은 즉각적인 이동과 장애물 안전(Obstacle Safety)을 담당하고, 플릿 수준 지능(Fleet-Level Intelligence)은 공유 운송 자원과 미래의 충돌을 관리한다. 이러한 역할 분리를 통해 개별 로봇은 로컬 환경에 신속하게 대응하면서 창고 전체에서는 전역적으로 조정된 동작을 유지할 수 있다.

효과적인 교통 관리는 독립적으로 주행하는 AMR들의 집합을 하나의 조정된 운송 네트워크(Coordinated Transportation Network)로 전환한다. 제한된 자원에 대한 접근을 제어하고, 혼잡을 예측하며, 탈출 가능 공간(Escape Capacity)을 유지하고, 순환 대기(Circular Waiting)를 해결함으로써 로봇 밀도가 창고 인프라의 처리 능력을 초과하지 않도록 플릿을 확장할 수 있다. 이러한 기능은 충전 조정(Charging Coordination), 예외 복구(Exception Recovery), 안전 관리(Safety Management), 수백 대의 AMR이 참여하는 대규모 운영(Large-Scale Operation)을 위한 핵심 기반을 형성한다.

## 01.07. Charging Station Management and Energy Opt [w/Code]

![](images/image7.png){width="7.268055555555556in" height="7.268055555555556in"}

충전소 관리(Charging Station Management)는 창고 AMR이 운송 용량(Transportation Capacity)을 불필요하게 감소시키지 않으면서 언제, 어디에서, 어떤 방식으로 에너지를 보충할지를 결정하는 플릿 수준 기능(Fleet-Level Function)이다. 로봇은 충전 중에는 생산적인 임무(Productive Mission)를 수행할 수 없기 때문에 잘못된 충전 의사결정은 여러 차량이 동시에 사용할 수 없게 되는 상황을 발생시킬 수 있다. 따라서 에너지 최적화(Energy Optimization)는 배터리, 충전기, 임무, 예상 작업량(Expected Workload)을 독립적인 하위 시스템이 아니라 상호 조정되는 자원(Coordinated Resource)으로 관리한다.

각 AMR은 배터리 충전 상태(State of Charge), 전압(Voltage), 온도(Temperature), 전류(Current), 예상 잔여 에너지(Estimated Remaining Energy), 배터리 건전성(Battery Health)에 관한 정보를 지속적으로 관리한다. 배터리 관리 시스템(Battery Management System, BMS)은 이러한 값을 모니터링하고 안전하지 않은 작동 조건으로부터 배터리를 보호한다. 플릿 소프트웨어(Fleet Software)는 상위 수준의 에너지 정보를 이용하여 로봇이 할당된 임무를 안전하게 완료할 수 있는지, 작업을 계속할 수 있는지, 또는 가용 충전소로 이동해야 하는지를 결정한다.

단순한 충전 정책(Charging Policy)은 로봇의 충전 상태가 고정된 임계값(Fixed Threshold) 아래로 떨어지면 충전을 시작하도록 한다. 구현은 간단하지만 여러 로봇이 유사한 작업량을 처리할 경우 충전 시점이 동기화되는 현상(Synchronized Charging)이 발생할 수 있다. 이 경우 플릿의 상당 부분이 동시에 사용할 수 없는 상태가 될 수 있다. 보다 발전된 정책은 충전 시작 시점을 결정하기 전에 현재 수요(Current Demand), 미래의 예상 임무(Predicted Future Mission), 충전기 점유 상태(Charger Occupancy), 로봇 위치, 잔여 에너지를 함께 고려한다.

따라서 충전 임계값(Charging Threshold)은 고정값이 아니라 동적으로 설정할 수 있다. 창고 작업량이 낮은 시간에는 미래의 수요에 대비하기 위해 비교적 높은 배터리 수준에서도 로봇을 충전할 수 있다. 반대로 피크 운영(Peak Operation) 중에는 임무 완료와 충전소까지의 안전한 이동에 필요한 충분한 예비 에너지(Energy Reserve)가 남아 있다면 일부 로봇이 더 낮은 에너지 수준까지 작업을 계속하도록 허용할 수 있다. 동적 임계값(Dynamic Threshold)은 필요한 에너지 안전 여유(Energy Safety Margin)를 유지하면서 운영 용량을 확보하는 데 도움이 된다.

기회 충전(Opportunity Charging)은 자연스럽게 발생하는 짧은 유휴 시간(Idle Period)을 활용하여 에너지를 보충하는 방식이다. 임무 사이에서 대기하거나 충전소 주변에 위치한 AMR은 그대로 유휴 상태를 유지하는 대신 부분 충전(Partial Charging)을 수행할 수 있다. 이러한 전략은 장시간의 전용 충전 세션(Dedicated Charging Session)에 대한 필요성을 줄이고 플릿 가용성(Fleet Availability)을 높일 수 있다. 효과는 배터리 화학 특성(Battery Chemistry), 충전기 성능(Charger Capability), 임무 패턴(Mission Pattern), 유휴 시간의 빈도와 지속시간에 따라 달라진다.

예측 충전(Predictive Charging)은 예상되는 미래 작업량을 고려함으로써 이러한 개념을 확장한다. 과거 주문 패턴(Historical Order Pattern), 생산 일정(Production Schedule), 교대 시간(Shift Change), 입고 일정(Inbound Delivery), 계획된 출하 물량(Planned Shipping Wave)을 이용하면 운송 수요가 증가할 시점을 예측할 수 있다. 플릿 관리자는 이러한 피크가 발생하기 전에 추가 로봇을 충전할 수 있다. 이에 따라 에너지 관리는 배터리가 소진된 이후에만 대응하는 방식이 아니라 충전 용량을 사전에 준비하는 스케줄링 문제(Scheduling Problem)가 된다.

충전소 배치(Charging Station Placement)는 에너지 효율(Energy Efficiency)과 플릿 성능에 큰 영향을 준다. 주요 운영 구역에서 멀리 떨어진 충전기는 비생산적인 이동(Nonproductive Travel)을 발생시키며, 배터리 수준이 낮은 로봇이 충전소까지 이동하기 위해 추가 에너지를 확보해야 할 수 있다. 분산형 충전소(Distributed Charging Station)는 접근 거리를 줄일 수 있지만 과도한 인프라는 비용을 증가시키고 중요한 창고 공간을 차지한다. 따라서 충전소 배치는 교통 패턴(Traffic Pattern), 플릿 규모(Fleet Size), 임무의 공간적 분포(Mission Geography), 예상 충전 수요(Expected Charging Demand)를 반영해야 한다.

충전기 할당(Charger Assignment)은 단순한 물리적 거리 이상을 고려해야 한다. 가장 가까운 충전기에 긴 대기열이 형성되어 있다면 조금 더 먼 충전소를 이용하는 것이 전체적으로 더 빠를 수 있다. 할당 알고리즘(Assignment Algorithm)은 이동 시간(Travel Time), 대기열 길이(Queue Length), 예상 충전 시간(Expected Charging Duration), 충전기 전력(Charger Power), 로봇 호환성(Robot Compatibility), 하류 교통 상황(Downstream Traffic)을 평가할 수 있다. 목표는 단순히 충전기까지의 거리를 최소화하는 것이 아니라 로봇이 다시 운영 가능한 상태가 될 때까지의 전체 시간을 최소화하는 것이다.

충전소 자체가 교통 병목(Traffic Bottleneck)이 될 수도 있다. 사용 중인 충전기 주변에서 로봇들이 대기하면 인접한 통로를 차단하거나 충전 위치로 진입하고 이탈하는 다른 차량을 방해할 수 있다. 전용 대기 구역(Dedicated Waiting Zone), 제어된 접근 경로(Controlled Approach Path), 예약 메커니즘(Reservation Mechanism)을 통해 이러한 상황을 방지할 수 있다. 일반적으로 로봇은 제한된 충전 구역으로 이동하기 전에 충전기 예약(Charger Reservation) 또는 확인된 대기열 위치(Confirmed Queue Position)를 확보해야 한다.

플릿 관리자는 충전과 임무 할당(Mission Assignment)을 함께 조정해야 한다. 에너지가 부족한 로봇에는 임무를 완료한 후 충전소에 접근하기 위한 충분한 예비 에너지가 남지 않는 운송 작업을 할당해서는 안 된다. 임무 실행 가능성(Mission Feasibility)은 경로 길이(Route Length), 적재 중량(Payload), 예상 대기 시간(Expected Waiting), 교통 상황, 과거 에너지 소비량(Historical Energy Consumption)을 이용하여 추정할 수 있다. 에너지 인식 작업 할당(Energy-Aware Task Allocation)은 긴급 충전(Emergency Charging)을 줄이고 활성 임무 중 로봇이 운행 불능 상태가 되는 것을 방지한다.

적재 중량은 특히 팔레트 AMR(Pallet AMR)과 자율 지게차(Autonomous Forklift)의 에너지 소비에 중요한 영향을 준다. 무거운 적재물은 추진 에너지(Propulsion Energy)를 증가시킬 수 있으며, 혼잡한 구역에서 반복적인 가속과 감속은 효율을 더욱 감소시킬 수 있다. 따라서 에너지 예측(Energy Prediction)은 명목상의 이동 거리만 사용하는 것이 아니라 실제 운영 조건을 반영해야 한다. 과거 텔레메트리(Historical Telemetry)를 활용하면 서로 다른 로봇 종류, 적재 중량, 경로, 교통 조건에 대한 에너지 소비 모델(Energy Consumption Model)을 구축할 수 있다.

경로 최적화(Route Optimization)는 이동 시간과 함께 에너지 비용(Energy Cost)을 고려할 수 있다. 길이가 유사한 두 경로라도 바닥 경사(Floor Slope), 표면 저항(Surface Resistance), 회전 빈도(Turning Frequency), 정지 횟수, 혼잡, 적재 상태에 따라 에너지 소비량이 달라질 수 있다. 에너지 인식 경로 계획기(Energy-Aware Planner)는 불필요한 가속이나 장시간 대기를 줄이는 경로를 선택할 수 있다. 그러나 개별 로봇의 에너지 소비 최소화가 전체 플릿의 효율성을 감소시키는 혼잡을 발생시켜서는 안 된다.

배터리 건전성(Battery Health)은 장기적인 최적화 목표(Long-Term Optimization Objective)를 추가한다. 배터리 기술에 따라 반복적인 심방전(Deep Discharge), 과도한 온도, 부적절한 충전 속도(Charging Rate), 불리한 운용 패턴은 열화(Degradation)를 가속할 수 있다. 플릿 관리는 용량 감소(Capacity Loss)와 내부 건전성 지표(Health Indicator)를 모니터링하여 예상 성능을 제공하지 못하는 배터리를 식별할 수 있다. 에너지 최적화는 단기적인 로봇 가용성과 배터리 수명(Battery Lifetime), 유지보수 비용(Maintenance Cost) 사이의 균형을 고려해야 한다.

충전 인프라(Charging Infrastructure)는 서로 다른 전력 수준이나 전기적 특성을 가진 충전기로 구성될 수 있다. 급속 충전(Fast Charging)은 로봇을 빠르게 작업에 복귀시킬 수 있지만 전력 수요를 증가시키며 배터리 설계에 따라 열적 조건(Thermal Condition)이나 배터리 노화(Battery Aging)에 영향을 줄 수 있다. 장시간 유휴 상태가 예상되는 로봇에는 저속 충전(Slower Charging)이 적합할 수 있다. 스케줄러는 운영 긴급성(Operational Urgency), 배터리 상태, 예상 작업량, 사용 가능한 인프라에 따라 적절한 충전 방식을 선택할 수 있다.

대규모 배치에서는 시설 수준의 전력 용량(Facility-Level Electrical Capacity)이 제약조건이 될 수 있다. 충분한 수의 물리적 충전기가 존재하더라도 수백 대의 로봇이 동시에 충전되면 상당한 피크 전력 수요(Peak Power Demand)가 발생할 수 있다. 충전 관리 시스템(Charging Management System)은 동시 충전 전력을 제한하거나, 충전 세션을 분산하거나, 연결된 로봇 사이에 전력을 동적으로 할당할 수 있다. 이를 통해 AMR 에너지 최적화는 보다 광범위한 건물 및 산업 에너지 관리 전략(Industrial Energy-Management Strategy)과 연결된다.

충전 스케줄링(Charging Scheduling)은 자원 할당 문제(Resource-Allocation Problem)로 구성할 수 있다. 로봇은 충전 자원을 요청하고 플릿 관리자는 충전 시작 시간(Start Time), 충전소, 충전 지속시간(Duration), 목표 충전 상태(Target State of Charge)를 결정한다. 향후 임무에 필요한 높은 우선순위의 로봇은 먼저 충전할 수 있으며 충분한 에너지를 보유한 차량은 대기할 수 있다. 또한 긴급 로봇에 대한 반복적인 우선권으로 다른 차량이 지속적으로 충전 부족 상태가 되지 않도록 공정성(Fairness)을 고려해야 한다.

모든 로봇을 항상 완전 충전(Full Charging)하는 것보다 부분 충전(Partial Charging)을 사용하면 더 높은 유연성을 확보할 수 있다. 로봇이 다음 예상 작업 시간 동안 필요한 에너지만 확보하면 되는 경우 짧은 충전 세션을 통해 더 빠르게 작업에 복귀하고 다른 차량을 위해 충전기를 비울 수 있다. 최적 목표 충전 상태(Optimal Target State of Charge)는 예상 수요(Forecast Demand), 배터리 상태, 충전기 가용성(Charger Availability), 임무 불확실성(Mission Uncertainty), 대체 가능한 로봇 수에 따라 달라진다.

고장과 예외 상황(Failure and Exception)은 명확한 에너지 관리 대응을 필요로 한다. 충전기를 사용할 수 없게 되거나, 로봇이 전기적 접촉(Electrical Contact)에 실패하거나, 배터리 온도가 허용 범위를 초과하거나, 충전이 예상하지 못하게 중단될 수 있다. 시스템은 이러한 상태를 감지하고 유효하지 않은 예약을 해제하며 가능한 경우 로봇을 다른 충전소로 전환하고 유지보수 이벤트(Maintenance Event)를 생성해야 한다. 에너지 관련 고장이 플릿 용량을 조용히 감소시켜 창고 성능이 저하될 때까지 발견되지 않는 상황을 방지해야 한다.

로봇, 충전기, BMS, 플릿 관리자 사이의 통신은 일관된 충전 상태(Consistent Charging State)를 유지해야 한다. 도킹 확인(Docking Confirmation), 전기 연결(Electrical Connection), 충전 시작(Charging Start), 현재 충전 전력(Current Power), 목표 수준(Target Level), 충전 완료(Charging Completion), 도킹 해제(Undocking)는 명시적인 상태 전이(State Transition)로 표현되어야 한다. 타임아웃(Timeout)과 응답 확인(Acknowledgment)은 불완전한 동작을 감지하는 데 도움이 된다. 예정된 충전 시간이 경과했더라도 충전 완료가 확인되지 않았다면 해당 로봇을 가용 상태로 판단해서는 안 된다.

에너지 텔레메트리(Energy Telemetry)는 지속적인 최적화(Continuous Optimization)를 지원한다. 유용한 데이터에는 충전 상태 변화(State-of-Charge Trajectory), 임무별 에너지 소비량(Energy Consumed per Mission), 충전 시간, 대기열 시간(Queue Time), 충전기 활용률(Charger Utilization), 배터리 온도, 도킹 시도(Docking Attempt), 유휴 에너지 소비(Idle Energy Use), 열화 지표(Degradation Indicator)가 포함된다. 이러한 정보를 경로, 적재 중량, 교통 상황, 주문 수요와 연계하면 비효율적인 로봇, 과부하된 충전 위치, 비정상 배터리, 스케줄링 개선 기회를 식별할 수 있다.

핵심 성과 지표(Key Performance Indicator)는 플릿 생산성과 에너지 동작을 모두 반영해야 한다. 관련 지표에는 로봇 가용성(Robot Availability), 충전당 완료 임무 수(Missions Completed per Charge), 운송당 에너지 소비량(Energy Consumed per Transport), 충전기 활용률, 충전 대기열 시간(Charging Queue Duration), 충전소까지의 비생산적 이동, 긴급 저전력 이벤트(Emergency Low-Battery Event), 최대 전력 수요, 배터리 열화 추세(Battery Degradation Trend)가 포함된다. 하나의 지표만 최적화하면 높은 가용성을 추구하는 과정에서 에너지 비용이 증가하거나 배터리 수명이 감소하는 등의 문제가 발생할 수 있다.

시뮬레이션(Simulation)과 디지털 트윈(Digital Twin)을 사용하면 플릿 배치 또는 충전 인프라 확장 전에 다양한 충전 전략을 평가할 수 있다. 엔지니어는 플릿 규모, 충전기 수, 충전소 위치, 충전 전력, 임무 수요, 배터리 용량(Battery Capacity), 임계값 정책(Threshold Policy)을 변경하면서 성능을 분석할 수 있다. 시뮬레이션을 통해 피크 시간에 충전 대기열이 발생하는지, 추가 충전기가 실제로 처리량을 향상시키는지를 확인할 수 있으며 목표 플릿 가용성을 지원하기 위한 최소 인프라 규모도 추정할 수 있다.

대규모 AMR 플릿에서는 충전 의사결정이 교통 관리(Traffic Management) 및 창고 실행(Warehouse Execution)과 상호작용해야 한다. 많은 로봇을 동일한 충전 구역으로 동시에 보내면 혼잡이 발생할 수 있으며, 특정 작업 구역에서 지나치게 많은 차량을 충전으로 전환하면 해당 지역의 운송 용량이 감소할 수 있다. 따라서 플릿 관리자는 충전, 작업 할당(Task Allocation), 경로 계획(Route Planning), 교통 관리를 각각 독립적으로 최적화하는 대신 하나의 통합된 자원 제어 문제(Resource-Control Problem)로 조정해야 한다.

성숙한 충전 및 에너지 최적화 아키텍처(Mature Charging and Energy Optimization Architecture)는 배터리 관리를 반응형 유지보수 기능(Reactive Maintenance Function)에서 운영 계획 기능(Operational Planning Capability)으로 전환한다. 배터리 상태, 작업량 예측(Workload Prediction), 충전기 예약, 에너지 인식 작업 할당, 경로 비용(Route Cost), 전력 제약조건(Electrical Constraint), 건전성 모니터링(Health Monitoring)을 결합함으로써 창고는 불필요한 충전 이동, 대기열, 에너지 관련 운영 중단을 줄이면서 충분한 운송 용량을 유지할 수 있다.

창고 플릿이 수십 대에서 수백 대의 AMR로 확장될수록 효과적인 에너지 관리(Energy Management)는 필수적인 요소가 된다. 충전소는 가용성이 시스템 처리량에 직접적인 영향을 미치는 공유 인프라(Shared Infrastructure)가 되며, 배터리 상태는 장기간 유지할 수 있는 생산 용량(Productive Capacity)을 결정한다. 따라서 조정된 충전(Coordinated Charging)은 신뢰성 높은 예외 처리(Exception Handling), 지속적인 플릿 운영(Continuous Fleet Operation), 예측 가능한 유지보수(Predictable Maintenance), 대규모 창고 자동화(Large-Scale Warehouse Automation)를 위한 핵심 기반을 제공한다.

## 01.08. Exception Handling Blocked Path Error Recovery [w/Code]

![](images/image8.png){width="7.268055555555556in" height="7.268055555555556in"}

예외 처리(Exception Handling)는 실제 창고 환경에는 계획 단계에서 완전히 예측할 수 없는 상황이 존재하기 때문에 창고 AMR 운영에서 필수적이다. 임시 장애물(Temporary Obstacle), 잘못 배치된 팔레트(Misplaced Pallet), 차단된 통로(Blocked Aisle), 자동문 고장(Failed Door), 위치추정 오류(Localization Error), 통신 두절(Communication Loss), 센서 고장(Sensor Fault), 도킹 실패(Unsuccessful Docking)는 정상적인 임무를 중단시킬 수 있다. 강건한 시스템(Robust System)은 이러한 상황을 감지하고 영향을 분류하며 전체 플릿을 불필요하게 정지시키지 않고 복구할 수 있어야 한다.

예외(Exception)는 정상적인 운영 변동(Normal Operational Variation)과 구분되어야 한다. 지나가는 작업자를 피하기 위해 로봇이 감속하는 상황에는 로컬 장애물 회피(Local Obstacle Avoidance)만 필요할 수 있지만, 수분 동안 통로가 차단되는 경우에는 플릿 수준의 개입(Fleet-Level Intervention)이 필요하다. 시스템은 심각도(Severity), 지속시간(Duration), 영향을 받는 자원(Affected Resource), 안전 영향(Safety Impact), 복구 가능성(Recoverability)에 따라 이벤트를 분류할 수 있다. 이를 통해 일시적인 장애가 불필요한 경보를 발생시키는 것을 방지하면서 지속적인 문제는 적절하게 상위 단계로 에스컬레이션(Escalation)할 수 있다.

경로 차단(Blocked Path)은 창고에서 가장 빈번하게 발생하는 예외 중 하나이다. 팔레트가 지정된 보관 위치 밖에 놓이거나, 카트가 통로에 방치되거나, 작업자가 경로를 점유하거나, 다른 차량이 예상하지 못하게 정지할 수 있다. 온보드 AMR(Onboard AMR)은 먼저 인지 센서(Perception Sensor)와 안전 센서(Safety Sensor)를 이용하여 장애물을 감지한다. 로컬 내비게이션(Local Navigation)이 정의된 제한 범위 내에서 장애물을 안전하게 우회할 수 없는 경우 해당 상태는 지속적인 경로 차단(Persistent Path Blockage)으로 플릿 관리자(Fleet Manager)에 보고된다.

복구 과정(Recovery Process)은 즉각적인 전역 재계획(Global Replanning)보다 제어된 대기(Controlled Waiting)로 시작하는 것이 적절하다. 많은 장애물은 일시적이며 수초 이내에 사라질 수 있다. 로봇은 경로가 다시 사용 가능해지는지를 모니터링하면서 안전한 위치에서 정지할 수 있다. 대기 임계값(Waiting Threshold)은 위치와 임무 긴급성(Mission Urgency)을 반영해야 한다. 그러나 과도한 대기는 차단된 로봇 뒤에 대기열을 형성할 수 있으므로 플릿 관리자는 개별 로봇뿐만 아니라 네트워크 수준의 영향(Network-Level Effect)도 고려해야 한다.

차단 상태가 지속되면 로컬 재계획(Local Replanning)을 통해 장애물 주변의 대체 경로(Alternative Path)를 탐색할 수 있다. 경로 계획기(Planner)는 로컬 비용 지도(Local Cost Map)를 갱신하고 로봇 외형 크기(Robot Footprint), 적재물(Payload), 안전 여유 공간(Safety Clearance), 운동학적 제약조건(Kinematic Constraint)을 고려하여 주변의 이동 가능한 공간을 평가한다. 이러한 방법은 개방된 공간에서는 효과적이지만 좁은 창고 통로에서는 로컬 우회 경로가 존재하지 않는 경우가 많다. 이 경우 예외는 플릿 경로 설정 계층(Fleet Routing Layer)으로 전달되어야 한다.

플릿 수준 재경로 설정(Fleet-Level Rerouting)은 차단된 구간을 일시적으로 사용할 수 없는 상태로 처리하거나 매우 높은 이동 비용(Traversal Cost)을 부여한다. 이후 영향을 받은 로봇과 해당 구역으로 접근 중인 다른 AMR의 경로를 대체 통로를 이용하도록 다시 계산할 수 있다. 차단 정보를 전파하면 추가 로봇이 문제가 발생한 구역으로 진입하는 것을 방지할 수 있다. 또한 차단된 구간을 정상 경로 설정 상태로 복귀시키기 전에 언제, 어떤 방식으로 장애물 제거 여부를 확인할 것인지 정의해야 한다.

대체 경로가 존재하더라도 경로 차단은 2차적인 혼잡(Secondary Congestion)을 발생시킬 수 있다. 이미 영향을 받은 통로에 진입한 로봇은 정지하거나 후진하거나 지정된 대기 위치(Designated Waiting Position)로 이동해야 할 수 있다. 차단 구역과 관련된 교통 예약(Traffic Reservation)은 재경로 설정 과정에서 새로운 충돌이나 교착상태(Deadlock)가 발생하지 않도록 신중하게 갱신해야 한다. 따라서 예외 복구(Exception Recovery)는 다중 AMR 교통 관리(Multi-AMR Traffic Management)와 직접적으로 조정되어야 한다.

복구 과정 전체에서 임무 상태(Mission State)는 명확하게 유지되어야 한다. 하나의 임무는 실행 중(Executing), 차단(Blocked), 대기(Waiting), 재계획(Replanning), 복구 중(Recovering), 재개(Resumed), 실패(Failed), 취소(Canceled) 상태로 전환될 수 있다. 이러한 상태를 유지하면 플릿 관리자, 창고제어시스템(Warehouse Control System, WCS), 창고실행시스템(Warehouse Execution System, WES), 창고관리시스템(Warehouse Management System, WMS)이 자재가 여전히 목적지로 이동하고 있는지를 파악할 수 있다. 자율 복구 가능성이 남아 있다면 로봇이 일시적으로 정지했다는 이유만으로 임무를 실패 상태로 보고해서는 안 된다.

복구 정책(Recovery Policy)은 단계적으로 높아지는 자율성 수준(Escalating Level of Autonomy)을 사용할 수 있다. 첫 번째 단계에서는 현재 동작을 재시도하고, 이후 로컬 재계획, 플릿 재경로 설정, 대체 스테이션 할당(Alternative Station Assignment), 임무 재할당(Mission Reassignment), 마지막으로 운영자 개입(Operator Intervention)으로 전환할 수 있다. 이러한 단계적 에스컬레이션은 사소한 장애마다 사람을 호출하는 것을 방지하는 동시에 물리적 지원이 필요한 상황에서 자율 복구 시도가 무한정 반복되는 것을 방지한다.

도킹 및 적재물 취급 실패(Docking and Load-Handling Failure)에는 특화된 복구 로직(Recovery Logic)이 필요하다. AMR이 스테이션에 도착했더라도 정확한 정렬에 실패하거나, 예상된 팔레트를 감지하지 못하거나, 리프팅 메커니즘(Lifting Mechanism)을 작동시키지 못하거나, 성공적인 적재물 이송(Load Transfer)을 확인하지 못할 수 있다. 로봇은 알려진 자세(Known Pose)로 후퇴한 후 정의된 횟수 내에서 도킹을 다시 시도할 수 있다. 반복적인 실패가 발생하면 무제한 재시도 대신 스테이션 검사(Station Inspection), 대체 자원 선택(Alternative Resource Selection), 운영자 지원(Operator Assistance)을 요청해야 한다.

위치추정 오류(Localization Error)는 내비게이션이 정확한 로봇 자세 추정(Robot Pose Estimation)에 의존하기 때문에 더욱 심각한 예외를 발생시킬 수 있다. 지도 정합(Map Matching) 실패, 불일치하는 라이다 특징(LiDAR Feature), 휠 슬립(Wheel Slip), 센서 성능 저하(Sensor Degradation)는 위치추정 신뢰도(Localization Confidence)를 감소시킬 수 있다. 불확실성이 안전 한계를 초과하면 로봇은 감속하거나 정지해야 한다. 복구에는 정지 상태 재위치추정(Stationary Relocalization), 알려진 랜드마크(Known Landmark)로의 이동, 센서 재초기화(Sensor Reinitialization), 제어된 수동 위치 조정(Controlled Manual Positioning)이 포함될 수 있다.

센서 및 액추에이터 고장(Sensor and Actuator Fault)은 환경적 경로 차단(Environmental Blockage)과 구분되어야 한다. 안전 스캐너(Safety Scanner) 고장, 손상된 엔코더(Damaged Encoder), 조향 고장(Steering Fault), 리프트 오류(Lift Error), 모터 제어기 경보(Motor-Controller Alarm)는 경로가 비어 있더라도 안전한 자율 운행을 방해할 수 있다. 진단 소프트웨어(Diagnostic Software)는 영향을 받은 하위 시스템(Subsystem)을 식별하고 성능 저하 운전(Degraded Operation)이 허용되는지를 판단해야 한다. 안전 중요 고장(Safety-Critical Fault)은 일반적으로 복구가 검증될 때까지 로봇을 정의된 안전 상태(Safe State)로 전환해야 한다.

통신 두절(Communication Loss)은 로봇과 플릿 관리자 사이에 불확실성을 발생시킨다. 로봇은 여전히 주변 환경을 인식할 수 있지만 플릿 시스템은 로봇의 위치나 자원 사용 상태(Resource Usage)를 확인할 수 없다. 하트비트 모니터링(Heartbeat Monitoring)을 통해 통신 장애를 감지할 수 있으며, 사전에 정의된 동작을 통해 로봇이 즉시 정지할 것인지 또는 안전한 위치까지 이동을 완료할 것인지 결정한다. 예약된 교통 자원(Reserved Traffic Resource)은 로봇 상태가 신뢰성 있게 복구될 때까지 보호된 상태로 유지되어야 한다.

플릿 시스템은 소프트웨어 및 서비스 장애(Software and Service Failure)도 처리해야 한다. 경로 설정 서비스(Routing Service), 데이터베이스(Database), 메시지 브로커(Message Broker), WCS 인터페이스 또는 플릿 관리 구성 요소가 예상하지 못하게 재시작될 수 있다. 영속적 임무 기록(Persistent Mission Record)과 트랜잭션 기반 상태 갱신(Transactional State Update)을 사용하면 활성 작업에 대한 정보를 잃지 않고 운영을 재개할 수 있다. 새로운 명령을 발행하기 전에 복구 로직은 로봇이 보고한 상태와 서버 기록(Server Record)을 조정하여 중복되거나 서로 모순되는 임무를 방지해야 한다.

임무 재할당(Mission Reassignment)은 로봇이 더 이상 임무를 계속할 수 없지만 운송 요청 자체는 여전히 유효한 경우 유용하다. 고장 난 로봇이 아직 적재물을 픽업하지 않았다면 다른 AMR이 해당 작업을 직접 인계받을 수 있다. 그러나 적재물이 이미 로봇에 실려 있다면 물리적 적재물 보유 상태(Physical Custody)를 고려해야 하므로 복구가 더 복잡해진다. 임무를 계속하기 전에 로봇 수리, 수동 하역(Manual Unloading), 다른 차량으로의 적재물 이송이 필요할 수 있다.

공유 장비 고장(Shared Equipment Failure)은 여러 로봇에 동시에 영향을 줄 수 있다. 엘리베이터(Elevator), 자동문(Automatic Door), 컨베이어 인터페이스(Conveyor Interface), 팔레트 이송 스테이션(Pallet-Transfer Station)을 사용할 수 없게 되면 창고 전체 구역의 경로와 임무가 무효화될 수 있다. WCS는 장비 상태(Equipment State)를 발행하여 플릿 관리자가 해당 장비에 의존하는 새로운 임무를 할당하지 않도록 해야 한다. 대체 자원이 존재하면 이를 선택하고, 대기 중인 작업은 장비가 정상 서비스로 복귀할 때까지 보존할 수 있다.

사람의 개입(Human Intervention)은 자동화 시스템 외부의 활동이 아니라 제어된 시스템 작업(Controlled System Operation)으로 취급해야 한다. 운영자 인터페이스(Operator Interface)는 로봇 식별 정보, 위치, 임무, 적재물, 고장 코드(Fault Code), 이미 수행된 복구 작업, 권장 절차(Recommended Procedure)를 표시해야 한다. 운영자가 로봇이나 적재물을 수동으로 이동하는 경우 해당 작업을 디지털 방식으로 확인하여 자율 운행을 재개하기 전에 재고, 교통 예약, 임무 상태, 로봇 위치추정을 다시 일치시켜야 한다.

오류 코드(Error Code)는 자동화된 추론(Automated Reasoning)과 유지보수를 모두 지원할 수 있도록 구조화되어야 한다. 유용한 이벤트 기록(Event Record)은 하위 시스템, 고장 분류(Fault Category), 심각도, 타임스탬프(Timestamp), 로봇, 임무, 위치, 복구 상태(Recovery Status)를 식별한다. 일관된 분류를 사용하면 개별적으로 발생한 사고와 반복적으로 발생하는 장비 또는 레이아웃 문제를 구분할 수 있다. 또한 플릿 분석(Fleet Analytics)을 통해 어떤 예외 상황이 가장 많은 운영 시간을 소비하는지 판단할 수 있다.

재시도 정책(Retry Policy)에는 명확한 제한이 필요하다. 동작을 반복하면 일시적인 통신 오류, 일시적 도킹 실패, 단기간의 장애물을 해결할 수 있지만 제어되지 않는 재시도는 로봇을 비효율적인 반복 루프(Ineffective Loop)에 빠뜨릴 수 있다. 시스템은 각 오류 유형(Error Class)에 대해 최대 시도 횟수(Maximum Attempt), 백오프 간격(Backoff Interval), 에스컬레이션 조건(Escalation Condition)을 정의해야 한다. 이후의 복구 의사결정이 전체 이력을 활용할 수 있도록 모든 시도의 결과를 기록해야 한다.

창고 생산성에 대한 압력이 높은 상황에서도 복구 과정은 안전(Safety)을 유지해야 한다. 운영자 또는 자동 감독 시스템(Automated Supervisor)은 단순히 처리량을 회복하기 위해 보호 기능(Protective Function)을 우회해서는 안 된다. 비상 정지(Emergency Stop), 안전 스캐너 위반(Safety Scanner Violation), 불안정한 적재물(Unstable Load), 불확실한 로봇 위치는 이동을 재개하기 전에 검증된 안전 조건(Validated Safe Condition)을 요구한다. 따라서 기능 복구(Functional Recovery)와 안전 복구(Safety Recovery)는 서로 관련되어 있지만 구분되는 과정이며, 안전 승인(Safety Authorization)이 우선한다.

예외 처리는 또한 로컬 고장(Local Failure)이 플릿 전체로 연쇄 확산(Cascading)되는 것을 방지해야 한다. 차단된 스테이션은 대기열을 생성하고, 이 대기열은 교차로를 점유하며, 충전 중인 로봇의 이동을 지연시키고, 결국 멀리 떨어진 구역에서 교착상태를 발생시킬 수 있다. 플릿 소프트웨어는 새로운 작업 배포(Task Release)를 제한하거나, 교통을 우회시키거나, 특정 구역의 로봇 밀도(Robot Density)를 일시적으로 낮추거나, 상류 스테이징 구역(Upstream Staging Area)에서 임무를 대기시킬 수 있다. 원래 고장을 복구하는 것만큼 장애의 확산을 억제하는 격리(Containment)도 중요하다.

운영 데이터(Operational Data)는 복구 정책의 지속적인 개선(Continuous Improvement)을 가능하게 한다. 예외 발생 빈도(Exception Frequency), 차단 지속시간(Blockage Duration), 재시도 성공률(Retry Success Rate), 평균 복구 시간(Mean Time to Recovery), 운영자 개입 횟수, 영향을 받은 위치, 반복되는 고장 코드를 분석하면 구조적인 문제를 식별할 수 있다. 특정 교차로에서 반복적으로 차단이 발생하면 잘못된 레이아웃 설계(Layout Design)가 원인일 수 있으며, 특정 스테이션에서 반복적인 도킹 실패가 발생하면 내비게이션 알고리즘보다 기계적 정렬 불량(Mechanical Misalignment)이 원인일 수 있다.

시뮬레이션(Simulation)과 고장 주입(Fault Injection)을 사용하면 실제 배치 전에 예외 처리 기능을 검증할 수 있다. 가상 장애물(Virtual Obstacle), 통신 두절, 충전기 고장(Failed Charger), 사용할 수 없는 스테이션(Unavailable Station), 위치추정 성능 저하(Localization Degradation), 로봇 고장을 창고 시뮬레이션에 의도적으로 발생시킬 수 있다. 엔지니어는 임무 상태가 올바르게 전환되는지, 교통이 안전하게 유지되는지, 재시도가 적절하게 종료되는지, 예상된 시점에 사람에게 에스컬레이션되는지를 검증할 수 있다. 드물게 발생하는 고장은 실제 운영 환경에서 재현하기 어렵기 때문에 이러한 테스트는 특히 중요하다.

성숙한 복구 아키텍처(Mature Recovery Architecture)는 온보드 자율성(Onboard Autonomy), 플릿 조정(Fleet Coordination), 창고 실행(Warehouse Execution), 진단(Diagnostics), 운영자 지원(Operator Support)을 결합한다. 로봇은 즉각적인 안전 대응과 로컬 복구를 담당하고, 플릿 관리자는 재경로 설정, 예약, 임무 재할당을 관리한다. WCS 또는 WES는 공유 장비와 워크플로 변경(Workflow Change)을 조정하며, WMS는 실제 물리적 결과가 확인된 이후 올바른 비즈니스 상태와 재고 상태(Inventory State)를 유지한다.

효과적인 예외 처리(Exception Handling)는 불완전한 실제 환경 조건에서도 창고 자동화가 생산성을 유지할 수 있도록 한다. 경로 차단과 장비 고장을 항상 제거할 수는 없지만 감지(Detection), 분류(Classification), 자율 복구(Autonomous Recovery), 에스컬레이션, 상태 조정(State Reconciliation)을 통해 그 영향을 제한할 수 있다. 이러한 기능은 신뢰성 높은 AMR 플릿(Dependable AMR Fleet)을 위한 핵심 요소이며 안전 규정 준수(Safety Compliance)와 대규모 창고 배치(Large-Scale Warehouse Deployment)를 위한 운영 기반을 제공한다.

## 01.09. Warehouse AMR Safety ISO 3691 4 Case [w/Code]

![](images/image9.png){width="7.268055555555556in" height="7.268055555555556in"}

창고 AMR 안전(Warehouse AMR Safety)은 단순한 장애물 회피 기능(Obstacle-Avoidance Feature)이 아니라 전체 시스템의 속성(System Property)으로 설계되어야 한다. ISO 3691-4는 자동 자재 운송에 사용되는 차량을 포함하여 무인 산업용 트럭(Driverless Industrial Truck)과 관련 시스템을 위한 중요한 안전 프레임워크(Safety Framework)를 제공한다. 창고 애플리케이션에서 규정 준수(Compliance)를 달성하려면 차량 동작, 보호 장치(Protective Device), 운영 구역(Operating Zone), 적재물, 인프라, 사람과의 상호작용, 합리적으로 예측 가능한 비정상 상태(Foreseeable Abnormal Condition)를 종합적으로 고려해야 한다.

안전 엔지니어링(Safety Engineering)은 의도된 애플리케이션에 대한 위험성 평가(Risk Assessment)에서 시작한다. 엔지니어는 차량 이동, 충돌(Collision), 압착(Crushing), 끼임(Trapping), 적재물 취급(Load Handling), 제동(Braking), 충전, 유지보수, 작업자와의 상호작용과 관련된 위험요인(Hazard)을 식별한다. 발생 가능한 피해의 심각도(Severity)와 노출 가능성(Probability of Exposure)을 평가하여 적절한 위험 저감 조치(Risk-Reduction Measure)를 선택한다. 이러한 평가는 AMR의 명목상 기능뿐만 아니라 실제 창고 환경을 반영해야 한다.

운영 환경(Operating Environment)은 안전 설계에 큰 영향을 준다. 넓은 자율주행 구역(Autonomous Travel Area), 좁은 통로(Narrow Aisle), 시야가 제한된 교차로(Blind Intersection), 보행자 횡단 구역(Pedestrian Crossing), 적재 스테이션(Loading Station), 충전 구역(Charging Zone), 제한 구역(Restricted Area)은 서로 다른 위험요인을 가진다. 따라서 운영 구역을 정의할 때 교통 방향(Traffic Direction), 가시성(Visibility), 바닥 상태(Floor Condition), 최대 속도(Maximum Speed), 사용 가능한 여유 공간(Available Clearance), 사람의 접근 가능성을 고려해야 한다. 하나의 창고 구역에 적합한 안전 설정(Safety Configuration)이 다른 구역에는 적합하지 않을 수 있다.

안전 레이저 스캐너(Safety Laser Scanner)와 기타 보호 감지 장치(Protective Sensing Device)는 AMR 주변에 감시 영역(Monitored Area)을 설정한다. 보호 필드(Protective Field)는 사람이나 장애물이 이동 중인 차량 주변의 위험 영역에 진입하기 전에 이를 감지할 수 있다. 경고 필드(Warning Field)는 제어된 감속(Controlled Deceleration)을 유발할 수 있으며, 보호 필드 내부로의 침입은 안전 관련 정지(Safety-Related Stop)를 실행할 수 있다. 보호 필드의 크기는 차량 속도, 제동 성능(Braking Performance), 시스템 응답 시간(System Response Time), 적재물, 이동 방향, 환경 조건을 고려하여 설정해야 한다.

동적 보호 필드(Dynamic Protective Field)는 속도와 이동 방향이 자주 변경되는 AMR에 특히 유용하다. 고속에서는 충분한 정지 거리(Stopping Distance)를 확보하기 위해 감시 영역을 더 멀리 확장할 수 있으며, 저속에서는 제한된 공간에서 더 작은 보호 필드를 사용할 수 있다. 회전과 후진 동작에는 서로 다른 필드 형상(Field Geometry)이 필요할 수 있다. 안전 필드 전환(Safety-Field Switching) 자체도 신뢰성을 가져야 하며, 차량이 현재 활성화된 보호 영역과 일치하지 않는 속도로 운행하는 상황이 발생해서는 안 된다.

정지 성능(Stopping Performance)은 기본적인 안전 매개변수(Safety Parameter)이다. 필요한 보호 거리(Protective Distance)는 기계적인 제동 거리뿐만 아니라 센서 감지 시간(Sensor Detection Time), 안전 제어기 응답 시간(Safety-Controller Response), 액추에이터 지연(Actuator Delay), 차량 속도, 바닥 마찰(Floor Friction), 적재 상태(Load Condition)에 따라 결정된다. 검증(Verification)은 현실적인 최악 조건(Worst-Case Operating Condition)을 포함해야 한다. 마찰력이 낮은 바닥에서 무거운 적재물을 운반하는 AMR은 실험실에서 시험한 무부하 로봇보다 훨씬 긴 정지 거리가 필요할 수 있다.

속도 관리(Speed Management)는 또 다른 위험 저감 계층(Risk-Reduction Layer)을 제공한다. AMR은 사람과 분리된 구역에서는 높은 속도로 운행할 수 있지만 보행자 횡단 구역, 워크스테이션(Workstation), 교차로, 출입문 또는 시야가 제한된 구역에서는 자동으로 속도를 낮출 수 있다. 안전 속도 제한(Safe Speed Limit)은 검증된 위치추정(Localization) 또는 구역 감지 메커니즘(Zone-Detection Mechanism)과 연계되어야 한다. 시스템이 로봇이 고속 운행 허용 구역에 있다는 사실을 신뢰성 있게 판단할 수 없다면 적절한 안전 상태(Safer Condition)로 전환해야 한다.

비상 정지 기능(Emergency Stop Function)은 비정상 상황에서 위험한 움직임을 정지시키는 직접적인 수단을 제공한다. 비상 정지 장치(Emergency Stop Device)는 필요한 위치에서 접근 가능해야 하며 안전 관련 제어 아키텍처(Safety-Related Control Architecture)에 통합되어야 한다. 비상 정지가 작동하면 단순히 일반 소프트웨어 명령을 전송하는 것이 아니라 AMR을 정의된 안전 상태(Safe Condition)로 전환해야 한다. 재시작(Restart)은 적절한 리셋 조건(Reset Condition)을 요구해야 하며 예상하지 못한 차량 움직임이 자동으로 발생해서는 안 된다.

안전 관련 제어 기능(Safety-Related Control Function)은 일반적인 내비게이션 및 임무 소프트웨어와 적절하게 분리되어야 한다. 자율 내비게이션 스택(Autonomous Navigation Stack)이 경로와 속도를 계산할 수 있지만 독립적인 안전 기능은 실제 움직임이 허용된 한계 내에서 유지되는지를 감독한다. 따라서 비안전 애플리케이션 프로세스(Non-Safety Application Process)의 고장이 보호 감지 또는 안전 정지(Safe Stopping)를 비활성화해서는 안 된다. 복잡한 인공지능(AI) 또는 계획 소프트웨어가 상위 수준의 로봇 동작을 제어하는 경우 이러한 아키텍처 분리(Architectural Separation)는 특히 중요하다.

기능 안전 원칙(Functional Safety Principle)은 안전 제어기(Safety Controller), 통신, 센서, 액추에이터의 설계에 영향을 준다. 안전 기능은 감지된 고장에 대해 정의된 동작, 진단 범위(Diagnostic Coverage), 관련 위험에 적합한 무결성(Integrity)을 갖추어야 한다. 필요한 경우 이중화 또는 감시 채널(Redundant or Monitored Channel)을 사용할 수 있다. 목표는 구성 요소가 절대 고장 나지 않는다고 가정하는 것이 아니라 고장을 감지하고 시스템을 위험한 움직임을 제한하는 상태로 전환할 수 있도록 하는 것이다.

적재물 안전(Payload Safety)은 팔레트 AMR(Pallet AMR)과 중량물을 운송하는 차량에서 특히 중요하다. 적재물은 차량의 무게중심(Center of Gravity), 제동 특성(Braking Behavior), 외형 크기(Footprint), 가시성, 안정성(Stability)을 변화시킬 수 있다. 시스템은 정상 주행을 시작하기 전에 적재물이 올바르게 획득되었으며 지원 가능한 운용 조건 내에 있는지를 확인해야 한다. 불안정하거나 잘못 배치된 팔레트는 속도 감소, 임무 중단(Mission Interruption), 운영자 개입(Operator Intervention)을 요구할 수 있다.

도킹 및 이송 스테이션(Docking and Transfer Station)은 AMR이 작은 여유 공간을 두고 고정 구조물에 접근할 수 있기 때문에 추가적인 압착 및 끼임 위험(Crushing and Trapping Hazard)을 발생시킨다. 안전 분석(Safety Analysis)은 작업자의 이송 구역 진입, 예상하지 못한 적재물 이동, 컨베이어 또는 리프팅 메커니즘(Lifting Mechanism)과의 상호작용을 고려해야 한다. 인터록(Interlock)과 제어된 핸드셰이크(Controlled Handshake)를 사용하면 자동 이송을 시작하기 전에 로봇, 스테이션, 자재 취급 장비(Material-Handling Equipment)가 서로 호환되는 상태에 도달했는지를 확인할 수 있다.

사람-AMR 상호작용(Human-AMR Interaction)에는 예측 가능한 차량 동작(Predictable Vehicle Behavior)이 필요하다. 작업자는 로봇이 이동 중인지, 양보 중인지, 대기 중인지, 고장 상태인지 또는 재시작을 준비하고 있는지를 이해할 수 있어야 한다. 시각 표시기(Visual Indicator), 음향 신호(Audible Signal), 디스플레이(Display), 표준화된 운영 절차(Standardized Operational Procedure)는 상황 인식(Situational Awareness)을 향상시킬 수 있다. 그러나 경고 장치는 보호 조치를 보완해야 하며 이를 대체해서는 안 된다. 안전이 작업자가 항상 경고를 인지하고 정확하게 해석하는 것에 의존해서는 안 된다.

교차로와 시야가 제한된 모서리(Blind Corner)는 사람과 로봇이 동일한 공간에 가까이 접근할 때까지 인지가 제한될 수 있기 때문에 특별한 주의가 필요하다. 감속 구역(Reduced-Speed Zone), 거울(Mirror), 경고 장치, 교통 제어(Traffic Control), 물리적 분리(Physical Separation)를 통해 위험을 줄일 수 있다. 플릿 수준 예약(Fleet-Level Reservation)은 로봇 간 충돌을 방지할 수 있지만 사람은 플릿 예약 프로토콜에 참여하지 않으므로 인원 보호(Personnel Protection)는 이와 독립적으로 효과를 유지해야 한다.

따라서 창고 레이아웃(Warehouse Layout) 자체가 안전 시스템의 일부이다. 방호 구조물(Guarding), 보행자 통로(Pedestrian Lane), 횡단 지점(Crossing Point), 방호벽(Barrier), 바닥 표시(Floor Marking), 제한 구역, 탈출 공간(Escape Space), 충분한 통로 폭(Aisle Width)을 통해 능동형 로봇 감지(Active Robot Sensing)에 대한 의존성을 줄일 수 있다. 가능한 경우 사람과 자동화 교통을 분리하는 것이 모든 상호작용을 점점 복잡해지는 자율 동작으로 해결하려는 방식보다 더욱 예측 가능한 위험 감소 효과를 제공한다.

고장 상태(Fault Condition)에 대해서는 명시적으로 정의된 안전 대응(Safe Response)이 필요하다. 위치추정 상실(Loss of Localization), 안전 스캐너 고장, 조향 오류(Steering Error), 브레이크 고장(Brake Fault), 통신 두절(Communication Loss), 예상하지 못한 장애물 감지, 일관되지 않은 속도 피드백(Inconsistent Speed Feedback)은 자율 이동에 사용되는 가정을 무효화할 수 있다. 고장의 종류에 따라 AMR은 제어된 감속 또는 안전 관련 정지를 수행할 수 있다. 복구는 필요한 조건이 복원되고 검증된 이후에만 수행되어야 한다.

플릿 관리자(Fleet Manager)와의 통신은 운영상 중요하지만 플릿 통신이 끊어졌다고 해서 필수적인 온보드 안전 보호(Onboard Safety Protection)가 제거되어서는 안 된다. AMR은 상위 수준 명령을 사용할 수 없는 상황에서도 즉각적인 위험을 제어하는 데 필요한 안전 기능을 유지해야 한다. 통신이 복구될 때까지 교통 예약(Traffic Reservation)과 임무를 차단 상태로 유지해야 할 수 있지만 보호 감지와 정지 동작은 독립적으로 계속 작동해야 한다.

충전 구역(Charging Area)은 별도의 위험성 평가를 필요로 한다. 자동 도킹(Automatic Docking)은 전기 접점(Electrical Contact), 제한된 공간에서의 기동, 공유 인프라에 접근하는 여러 로봇과 관련될 수 있다. 대기하거나 도킹하는 로봇이 보행자 또는 교통에 위험한 상태를 만들지 않도록 충전소를 배치해야 한다. 전기적 보호(Electrical Protection), 배터리 모니터링(Battery Monitoring), 열적 한계(Thermal Limit), 비상 절차(Emergency Procedure), 유지보수 접근성(Maintenance Access)을 전체 안전 개념에 포함해야 한다.

검증(Validation)은 구현된 안전 조치가 실제 애플리케이션에서 의도한 대로 동작한다는 것을 입증해야 한다. 시험을 통해 보호 필드 응답(Protective-Field Response), 정지 거리, 속도 감소, 비상 정지, 구역 전환(Zone Transition), 장애물 감지, 재시작 동작, 적재물 취급, 고장 대응을 측정할 수 있다. 검증은 이상적인 시험 조건에만 의존하지 않고 대표적인 적재물, 속도, 바닥 상태, 접근 방향(Approach Direction), 합리적으로 예측 가능한 운영 시나리오를 포함해야 한다.

안전 검증(Safety Verification)은 비정상 상황과 합리적으로 예측 가능한 오사용(Foreseeable Misuse) 시나리오도 포함해야 한다. 작업자가 갑자기 통로에 진입하거나, 물체가 센서의 일부를 가리거나, 팔레트가 예상된 크기를 넘어 돌출되거나, 운영자가 고장 이후 복구를 시도할 수 있다. 이러한 조건을 시험하면 실제 창고 운영이 초기 시스템 설계에서 가정한 이상적인 프로세스와 다르게 진행될 때에도 보호 조치가 효과적으로 유지되는지를 판단할 수 있다.

소프트웨어, 지도(Map), 차량 매개변수(Vehicle Parameter), 안전 필드(Safety Field), 창고 레이아웃, 적재물 유형(Payload Type), 운영 속도(Operating Speed)의 변경은 이미 검증된 안전 상태(Validated Safety Condition)를 변화시킬 수 있다. 따라서 변경 관리(Change Management)는 수정 사항이 기존 위험성 평가나 안전 기능에 영향을 주는지를 평가해야 한다. 예를 들어 최대 속도의 작은 증가도 정지 거리를 늘려 기존에 설정된 보호 필드 크기를 더 이상 유효하지 않게 만들 수 있다.

운영 안전(Operational Safety)은 시운전(Commissioning)이 완료된 이후에도 계속 유지되어야 한다. 정기 검사(Periodic Inspection)를 통해 안전 스캐너, 비상 정지 장치, 브레이크, 경고 장치, 기계 구성 요소(Mechanical Component), 충전 장비를 검증할 수 있다. 유지보수 절차(Maintenance Procedure)는 정비 작업 중 로봇을 격리하거나 예상하지 못한 움직임을 방지하는 방법을 정의해야 한다. 고장 이력(Fault History)과 준사고 정보(Near-Miss Information)는 초기 검증에서 명확하지 않았던 새로운 위험을 발견하는 데 활용할 수 있으며 다시 위험성 평가에 반영되어야 한다.

교육 및 운영 절차(Training and Procedure)도 창고 안전이 기술과 운영 조직 전체에 걸쳐 공유되기 때문에 중요하다. 작업자는 보행자 경로, 로봇 운영 구역, 비상 대응(Emergency Action), 고장 복구 범위(Fault Recovery Boundary), 자동화 작업 구역 진입 제한을 이해해야 한다. 유지보수 담당자와 감독자는 안전한 리셋(Safe Reset), 수동 이동(Manual Movement), 진단 접근(Diagnostic Access), AMR을 자율 운행 상태로 복귀시킬 수 있는 조건에 대한 추가적인 지식을 갖추어야 한다.

실제적인 ISO 3691-4 지향 배치(ISO 3691-4-Oriented Deployment)는 위험성 평가, 안전 관련 제어 기능, 보호 감지(Protective Sensing), 검증된 정지 성능, 속도 관리, 안전한 적재물 취급, 인프라 설계(Infrastructure Design), 운영 절차, 검증을 통합한다. 단순히 안전 스캐너를 설치하는 것만으로 규정 준수를 달성할 수 있는 것은 아니다. 차량과 차량이 운용되는 환경은 전체 수명주기(Lifecycle)에 걸쳐 하나의 통합 산업 운송 시스템(Integrated Industrial Transport System)으로 평가되어야 한다.

대규모 창고 AMR 플릿(Large Warehouse AMR Fleet)에서는 안전이 교통 관리(Traffic Management), 충전(Charging), 예외 복구(Exception Recovery), WMS/WCS 통합과 함께 동작해야 하지만 즉각적인 인원 보호를 이러한 상위 기능에 의존해서는 안 된다. 플릿 지능(Fleet Intelligence)은 전체적인 조정을 향상시킬 수 있지만 상위 수준 시스템이 고장 나더라도 각각의 차량은 적절한 안전 동작을 유지해야 한다. 이러한 계층형 접근 방식(Layered Approach)은 예측 가능하고 검증 가능하며 유지보수 가능한 안전 성능(Safety Performance)을 유지하면서 창고 자동화를 대규모로 확장할 수 있도록 한다.

## 01.10. 500 AMR Warehouse Fleet Operation Case

![](images/image10.png){width="7.268055555555556in" height="7.268055555555556in"}

약 500대 규모의 AMR 창고 플릿(Warehouse Fleet)을 운영하는 것은 자동화를 개별 로봇 제어(Individual Robot Control)에서 대규모 운송 시스템 관리(Large-Scale Transportation-System Management)로 전환하는 것을 의미한다. 이 규모에서는 전체 성능이 단일 로봇의 내비게이션 품질보다 작업 할당(Task Allocation), 교통 제어(Traffic Control), 충전(Charging), 예외 복구(Exception Recovery), 스테이션 부하 균형(Station Balancing), 창고 시스템 통합(Warehouse-System Integration)의 조정 능력에 더욱 크게 좌우된다. 플릿은 하나의 분산 운영 자원(Distributed Operational Resource)처럼 동작해야 한다.

창고는 보관 구역(Storage Zone), 피킹 구역(Picking Area), 팔레트 이송 위치(Pallet-Transfer Location), 보충 구역(Replenishment Zone), 포장 스테이션(Packing Station), 출하 버퍼(Shipping Buffer), 충전 구역(Charging Area)과 같은 기능별 영역으로 구분할 수 있다. 각 영역은 서로 다른 운송 패턴(Transport Pattern)과 용량 제약조건(Capacity Constraint)을 발생시킨다. 플릿 오케스트레이션(Fleet Orchestration)은 현재 작업량에 따라 로봇을 각 영역에 분산시키면서 과도한 차량 집중으로 혼잡(Congestion)이 발생하는 것을 방지해야 한다.

주문은 창고관리시스템(Warehouse Management System, WMS)에서 생성되며 창고실행시스템(Warehouse Execution System, WES) 또는 창고제어시스템(Warehouse Control System, WCS)을 통해 실행 가능한 자재 이동 요구사항(Material-Movement Requirement)으로 변환된다. 플릿 관리자(Fleet Manager)는 출발지, 목적지, 적재물, 우선순위, 시간 정보를 포함하는 운송 요청(Transport Request)을 수신한다. 이후 적절한 AMR을 선택하여 실행을 조정하고 임무 상태(Mission Status)를 상위 시스템에 지속적으로 보고한다.

수백 대의 로봇을 사용할 수 있는 환경에서 작업 할당(Task Allocation)은 지속적인 최적화 과정(Continuous Optimization Process)이 된다. 모든 임무에 가장 가까운 유휴 AMR(Idle AMR)을 선택하는 방식은 로봇이 인기 있는 스테이션 주변에 집중되거나 창고의 먼 거리를 반복적으로 이동하게 만들어 전체적으로 비효율적인 동작을 발생시킬 수 있다. 작업 할당은 로봇 위치, 예상 완료 시간(Expected Completion Time), 배터리 수준(Battery Level), 적재 호환성(Payload Compatibility), 교통 상황, 지역별 수요(Regional Demand), 미래 임무 가능성(Future Mission Opportunity)을 함께 고려해야 한다.

플릿 균형 조정(Fleet Balancing)은 각 운영 구역에서 충분한 로봇 처리 용량을 유지한다. 단기적인 수요를 충족하기 위해 많은 차량이 한 구역에서 다른 구역으로 이동하면 원래 구역에서 이후 발생하는 작업의 지연 시간이 크게 증가할 수 있다. 스케줄러(Scheduler)는 주문 대기열(Order Queue)과 과거 패턴(Historical Pattern)을 이용하여 가까운 미래의 작업량을 예측하고 유휴 로봇을 선제적으로 재배치(Proactive Repositioning)할 수 있다. 전략적 재배치(Strategic Repositioning)는 응답 시간을 줄일 수 있지만 에너지와 교통 용량을 낭비하는 과도한 공차 이동(Empty Travel)은 피해야 한다.

500대 AMR 배치에서는 교통 관리(Traffic Management)가 가장 중요한 제약조건 중 하나가 된다. 개별적으로는 유효한 수백 개의 경로가 동일한 교차로, 좁은 통로, 스테이션 입구, 이송 통로(Transfer Corridor)를 두고 경쟁할 수 있다. 중앙집중형 또는 계층형 교통 관리자(Central or Hierarchical Traffic Manager)는 경로 예약(Path Reservation)과 교차로 접근을 조정하면서 혼잡 상태를 모니터링한다. 목표는 각각의 로봇 경로 길이를 독립적으로 최소화하는 것이 아니라 창고 전체의 흐름(Warehouse Flow)을 최대화하는 것이다.

확장성(Scalability)을 향상시키기 위해 창고 영역을 교통 구역(Traffic Zone)으로 관리할 수 있다. 로컬 제어기(Local Controller)는 각 구역 내부의 세부 이동을 조정하고, 상위 수준 경로 설정(High-Level Routing)은 주요 통로 전체에 차량을 분산시키며 구역 사이의 전환을 관리한다. 이러한 계층형 구조(Hierarchical Structure)는 가능한 모든 로봇 상호작용을 전역적으로 평가하는 계산 부담을 줄인다. 또한 각 영역의 구조와 운영 특성에 따라 서로 다른 혼잡 정책(Congestion Policy)을 적용할 수 있다.

혼잡 모니터링(Congestion Monitoring)은 구간 점유율(Segment Occupancy), 로봇 밀도(Robot Density), 대기열 길이(Queue Length), 평균 속도(Average Speed), 예약 지연(Reservation Delay)을 이용하여 과부하된 영역을 식별한다. 혼잡이 증가하면 경로 비용(Route Cost)을 변경하여 새로운 교통 흐름을 대체 통로로 전환할 수 있다. 영향을 받는 스테이션에 대한 작업 배포(Task Release)를 일시적으로 줄일 수도 있다. 포화 상태(Saturated Region)에 추가 로봇이 진입하는 것을 방지하는 것이 교통 마비(Gridlock)가 발생한 이후 복구하는 것보다 효과적인 경우가 많다.

작은 로컬 차단(Local Blockage)이 대규모 플릿 전체로 확산될 수 있기 때문에 교착상태 예방(Deadlock Prevention)이 중요하다. 제한된 통로와 교차로에서는 탈출 공간(Escape Space)을 유지하고 순환 자원 의존성(Circular Resource Dependency)을 방지하는 예약 규칙(Reservation Rule)을 사용할 수 있다. 교착상태가 발생하면 플릿 관리자는 대기 관계(Waiting Relationship)를 식별하고 적절한 로봇을 선택하여 양보시키며 예약을 해제한 후 복구 경로(Recovery Path)를 생성한다. 이러한 해결 과정은 주변 교통에 미치는 영향을 최소화해야 한다.

스테이션(Station)은 또 다른 주요 용량 제약조건을 형성한다. 피킹 스테이션(Picking Station), 팔레트 인터페이스(Pallet Interface), 컨베이어(Conveyor), 엘리베이터(Elevator), 포장 구역은 도착하는 로봇을 제한된 속도로만 처리할 수 있다. 스테이션이 처리할 수 있는 속도보다 빠르게 AMR을 보내는 것은 운송 용량을 단순히 대기열로 변환할 뿐이다. 따라서 스테이션 인식 스케줄링(Station-Aware Scheduling)은 추가 임무를 배포하기 전에 처리율(Processing Rate), 대기열 용량(Queue Capacity), 예상 서비스 시간(Predicted Service Time), 하류 구간 가용성(Downstream Availability)을 고려한다.

충전(Charging)은 개별 배터리에 대한 대응이 아니라 플릿 스케줄링 문제(Fleet Scheduling Problem)가 된다. 많은 로봇이 동시에 낮은 충전 상태(State of Charge)에 도달하면 운송 용량이 급격하게 감소할 수 있다. 동적 충전 정책(Dynamic Charging Policy)은 배터리 상태, 예상 작업량(Expected Workload), 충전기 가용성(Charger Availability), 미래 수요(Future Demand)를 이용하여 충전 세션을 시간적으로 분산한다. 자연스럽게 발생하는 유휴 시간 동안 기회 충전(Opportunity Charging)을 수행하면 많은 로봇을 동시에 운영에서 제외하지 않고도 에너지 예비량(Energy Reserve)을 유지할 수 있다.

충전 인프라(Charging Infrastructure) 역시 운영상의 지리적 특성(Operational Geography)에 따라 분산되어야 한다. 로봇이 단순히 충전기에 접근하기 위해 반복적으로 창고 전체를 횡단하면 공차 이동과 추가적인 교통이 발생한다. 충전기 할당(Charger Assignment)은 이동 시간, 대기열 길이, 충전 속도(Charging Rate), 배터리 상태, 지역별 플릿 수요(Local Fleet Demand)를 고려할 수 있다. 대규모 환경에서는 전력 제한(Electrical Power Limit)으로 인해 여러 충전소 사이에서 충전 전력을 스케줄링해야 할 수도 있다.

예외 처리(Exception Handling)는 개별 고장이 플릿 전체의 장애로 확산되는 것을 방지해야 한다. 차단된 통로, 고장 난 로봇, 사용할 수 없는 스테이션, 통신 문제는 동일한 자원에 의존하는 많은 임무에 영향을 줄 수 있다. 플릿 관리자는 자원 상태(Resource State)의 변경을 전파하고, 접근 중인 로봇의 경로를 변경하며, 예약을 갱신하고, 영향을 받는 구역에 새로운 작업이 할당되는 것을 제한한다. 운영자 개입(Operator Intervention)을 요청하기 전에 자율 복구(Autonomous Recovery)를 우선적으로 시도한다.

고장 난 AMR은 가능한 한 빠르고 안전하게 정상 교통에서 격리되어야 한다. 중요한 통로를 차단하고 있다면 복구 인력이 투입되는 동안 주변 로봇의 경로를 변경해야 할 수 있다. 아직 자재를 운반하지 않는 임무는 대부분 자동으로 다른 로봇에 재할당(Mission Reassignment)할 수 있다. 고장 난 차량이 이미 팔레트 또는 토트를 적재하고 있는 경우에는 재고 기록을 갱신하기 전에 적재물 식별 정보(Load Identity)를 유지하면서 물리적 복구(Physical Recovery)를 조정해야 한다.

소프트웨어 아키텍처(Software Architecture)는 수백 대의 로봇이 생성하는 높은 이벤트 발생률(High Event Rate)을 처리할 수 있어야 한다. 고주파 위치추정(Localization), 센서, 이동 데이터는 로봇 및 플릿 제어 계층에 유지하고, 비즈니스 시스템에는 집계된 임무 및 처리 용량 정보(Aggregated Mission and Capacity Information)를 제공해야 한다. 이벤트 기반 메시징(Event-Driven Messaging), 영속적 대기열(Persistent Queue), 확장 가능한 서비스(Scalable Service), 분산 상태 관리(Distributed State Management)를 사용하면 불필요한 저수준 텔레메트리로 인해 WMS 또는 WCS 애플리케이션이 과부하되는 것을 방지할 수 있다.

임무 식별자(Mission Identifier)와 상관관계 정보(Correlation Information)는 종단 간 추적성(End-to-End Traceability)을 제공한다. 하나의 운송 요청은 WMS 생성 단계부터 WES 또는 WCS 오케스트레이션(Orchestration), 플릿 할당(Fleet Assignment), 로봇 실행, 예외 처리, 최종 배송 확인(Final Delivery Confirmation)에 이르기까지 추적할 수 있다. 짧은 시간 동안 수천 개의 임무가 실행되거나 완료되는 환경에서는 이러한 기능이 특히 중요하다. 운영자는 수백 대 차량의 관련 없는 로그를 모두 검색하지 않고도 개별 이벤트를 재구성할 수 있어야 한다.

관측 가능성(Observability)은 이러한 규모의 플릿을 운영하기 위한 필수 요소이다. 관제실 대시보드(Control-Room Dashboard)는 플릿 가용성(Fleet Availability), 활성 임무(Active Mission), 대기 중인 로봇, 혼잡 구역, 충전기 활용률(Charger Utilization), 스테이션 대기열, 통신 장애, 해결되지 않은 예외 상황을 표시할 수 있다. 구역별 화면(Regional View)을 사용하면 운영자가 어느 위치에서 처리 용량 손실이 발생하는지 파악할 수 있다. 경보(Alert)는 모든 일시적인 로봇 이벤트를 표시하여 운영자를 압도하기보다 실제 개입이 필요한 상태를 강조해야 한다.

안전(Safety)은 플릿 생산성 목표(Fleet Productivity Objective)와 독립적으로 유지되어야 한다. 플릿 조정(Fleet Coordination)은 로봇 간 충돌을 방지하고 혼잡을 감소시킬 수 있지만 각각의 AMR은 사람과 장애물에 대한 안전을 위해 적절한 온보드 보호 기능(Onboard Protective Function)을 유지해야 한다. 속도 구역(Speed Zone), 보호 필드(Protective Field), 안전 정지(Safe Stopping), 비상 기능(Emergency Function), 검증된 운영 규칙(Validated Operational Rule)은 상위 수준 플릿 서비스가 고장 나더라도 계속 유효해야 한다. 대규모 운영이라는 이유로 중앙집중형 소프트웨어가 유일한 안전 장벽(Safety Barrier)이 되어서는 안 된다.

운영 성능(Operational Performance)은 로봇 수준과 창고 수준 모두에서 측정해야 한다. 로봇 활용률(Robot Utilization)과 이동 효율(Travel Efficiency)도 유용하지만 완료 주문 수(Completed Orders), 시간당 임무 수(Missions per Hour), 스테이션 처리량(Station Throughput), 평균 운송 시간(Average Transport Time), 대기 시간, 공차 이동, 혼잡 발생 빈도(Congestion Frequency), 충전 손실(Charging Loss), 복구 시간(Recovery Time), 플릿 가용성은 보다 종합적인 성능을 보여준다. 개별 로봇의 활용률을 최대화하면 과도한 교통을 발생시켜 오히려 전체 처리량을 감소시킬 수도 있다.

플릿 규모(Fleet Size) 자체도 최대화가 아니라 최적화되어야 한다. AMR을 추가하면 초기에는 운송 용량이 증가하지만 결국 공유 통로, 교차로, 스테이션, 충전기가 포화된다. 이 지점을 넘어서면 추가 로봇은 완료되는 작업량을 증가시키지 못하면서 대기 시간을 늘리고 평균 속도를 감소시킬 수 있다. 따라서 용량 계획(Capacity Planning)은 차량 가용성보다 인프라가 주요 제약조건이 되는 플릿 규모를 식별해야 한다.

시뮬레이션(Simulation)과 디지털 트윈(Digital Twin)은 실제 운영 플릿을 변경하기 전에 이러한 포화 특성(Saturation Behavior)을 평가하는 데 유용하다. 과거 주문 흐름(Historical Order Stream)을 서로 다른 로봇 수, 교통 정책, 스테이션 용량, 충전 구성, 고장 시나리오(Failure Scenario)를 적용하여 재현할 수 있다. 엔지니어는 300대, 400대, 500대 또는 그 이상의 플릿 구성을 비교하여 추가 차량, 인프라 변경(Infrastructure Change), 스케줄링 개선 중 어느 방식이 가장 큰 운영상의 이점을 제공하는지 판단할 수 있다.

피크 시간 운영(Peak-Period Operation)에는 예측 제어(Predictive Control)가 필요하다. 출하 물량 집중(Shipping Wave), 보충 주기(Replenishment Cycle), 교대 시간(Shift Change), 생산 일정(Production Schedule)은 일평균보다 훨씬 높은 일시적인 운송 수요를 발생시킬 수 있다. 플릿 관리자는 피크가 시작되기 전에 로봇을 사전 배치(Pre-Positioning)하고, 충전 일정을 조정하며, 지역별 처리 용량을 확보하고, 낮은 우선순위의 재배치 작업(Relocation Task)을 지연시킬 수 있다. 이러한 예측 기반 준비는 대기열이 이미 형성된 이후에 대응하는 방식보다 운영 중단을 줄일 수 있다.

유지보수(Maintenance) 역시 데이터 기반(Data-Driven)으로 전환되어야 한다. 500대의 로봇을 운영하면 개별 로봇의 고장률이 낮더라도 정상 운영 중 여러 건의 유지보수 이벤트가 발생할 수 있다. 배터리 건전성(Battery Health), 모터 전류(Motor Current), 휠 상태(Wheel Condition), 센서 진단(Sensor Diagnostics), 도킹 실패(Docking Failure), 위치추정 품질(Localization Quality), 반복되는 고장 코드(Fault Code)를 분석하여 성능 저하를 식별할 수 있다. 예측 유지보수(Predictive Maintenance)를 적용하면 중요한 임무 수행 중 로봇이 고장 나는 대신 수요가 낮은 시간에 정비할 수 있다.

복원력 있는 배치(Resilient Deployment)는 불필요한 단일 장애점(Single Point of Failure)을 피해야 한다. 플릿 서비스, 데이터베이스, 메시징 인프라(Messaging Infrastructure), 네트워크 연결(Network Connectivity), 창고 인터페이스는 제어된 재시작(Controlled Restart)과 복구를 지원해야 한다. 영속적 상태(Persistent State)를 유지하면 서비스 중단 이후 활성 임무를 재구성할 수 있다. 구성 요소가 복구되면 정상적인 임무 배포를 다시 시작하기 전에 로봇이 보고하는 물리적 상태와 소프트웨어 기록을 조정(State Reconciliation)해야 한다.

지속적인 개선(Continuous Improvement)은 창고 전체에서 수집되는 운영 데이터를 통합하는 것에 의존한다. 교통 이력(Traffic History)을 통해 비효율적인 통로 설계를 발견할 수 있고, 스테이션 대기열을 통해 부족한 처리 용량을 식별할 수 있으며, 충전 기록을 통해 인프라 부족을 확인할 수 있고, 예외 패턴(Exception Pattern)을 통해 반복되는 물리적 문제를 발견할 수 있다. 따라서 500대 AMR 플릿은 레이아웃, 스케줄링, 유지보수, 자동화 정책(Automation Policy)을 개선하기 위해 분석할 수 있는 대규모 사이버-물리 데이터 소스(Cyber-Physical Data Source)가 된다.

성숙한 500대 AMR 창고는 하나의 거대한 단일 제어기(Monolithic Controller)가 아니라 서로 조정되는 여러 계층(Coordinated Layer)을 통해 운영된다. WMS는 재고와 주문 이행 의도(Fulfillment Intent)를 관리하고, WES 또는 WCS는 창고 실행(Warehouse Execution)을 조정하며, 플릿 지능(Fleet Intelligence)은 작업 할당과 교통 최적화(Traffic Optimization)를 수행하고, 개별 AMR은 안전한 자율 이동(Safe Autonomous Motion)을 실행한다. 충전, 복구, 안전, 모니터링, 유지보수는 명확하게 정의된 상태와 인터페이스를 통해 이러한 계층과 상호작용한다.

대규모 플릿 운영(Large-Scale Fleet Operation)의 핵심은 확장성이 단순한 로봇 수가 아니라 조정 품질(Coordination Quality)에 의해 결정된다는 것이다. 높은 성능의 AMR 500대를 배치하더라도 제한된 인프라를 놓고 효과적인 오케스트레이션 없이 경쟁한다면 높은 처리량을 달성할 수 없다. 작업 할당, 교통, 스테이션, 충전, 예외 처리, 안전, 창고 시스템을 하나의 통합 시스템(Integrated System)으로 관리할 때 수백 대의 로봇은 신뢰성 있고 지속적으로 최적화되는 자재 흐름 플랫폼(Material-Flow Platform)으로 동작할 수 있다.
