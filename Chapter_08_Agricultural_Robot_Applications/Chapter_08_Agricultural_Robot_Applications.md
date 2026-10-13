**Volume 26. Industrial Robot Applications**


# Chapter 08. Agricultural Robot Applications

##  

## 08.01. Agricultural Robot Market and SW Challenges

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

Agricultural robotics is evolving from isolated automation equipment into software-defined autonomous systems capable of sensing crops, interpreting field conditions, planning operations, and executing agricultural tasks with limited human supervision. The application scope now includes field navigation, crop monitoring, precision spraying, selective harvesting, soil analysis, greenhouse automation, and coordinated agricultural robot fleets.

The agricultural robot market is driven by several structural pressures. Farms face labor shortages, increasing labor costs, aging agricultural workforces, demands for higher productivity, and pressure to reduce water, fertilizer, pesticide, and energy consumption. At the same time, growers need more consistent crop quality and better traceability. Robots therefore create value not simply by replacing labor, but by enabling repeatable and data-driven agricultural operations.

Agricultural automation differs fundamentally from conventional factory automation because the operating environment is only partially structured. Factory robots normally operate around fixed equipment, known workspaces, controlled illumination, and repeatable objects. Agricultural robots encounter changing terrain, mud, dust, rain, wind, direct sunlight, vegetation growth, irregular crop geometry, moving workers, animals, agricultural vehicles, and seasonal changes that continuously modify the environment.

This environmental variability makes robust software one of the primary technical barriers to commercialization. A navigation algorithm that performs reliably during a dry morning may behave differently after rainfall changes soil traction or vegetation partially blocks a row. Camera-based perception may experience severe illumination changes, shadows, glare, leaf occlusion, and visually similar backgrounds. Agricultural software must consequently tolerate uncertainty rather than assume that sensor observations remain stable.

Localization is another major challenge. Outdoor agricultural robots can use Global Navigation Satellite System positioning combined with Real-Time Kinematic correction to obtain high-accuracy global coordinates, but satellite signals can degrade near trees, greenhouses, buildings, hills, or other obstructions. Reliable autonomy therefore requires fusion of GNSS-RTK with inertial sensors, wheel odometry, cameras, LiDAR, or other localization sources and graceful operation when individual sensors become unreliable.

Navigation software must convert localization results into safe motion through crop rows, headlands, access roads, and irregular field boundaries. Unlike warehouse AMRs that usually navigate relatively flat floors, agricultural vehicles must account for wheel slip, slopes, soft soil, ruts, vegetation, drainage channels, and changing vehicle dynamics. Path planning and control therefore need terrain awareness, vehicle-specific motion constraints, and continuous estimation of whether the planned trajectory remains physically executable.

Perception introduces an equally difficult software problem because agricultural objects are biological rather than manufactured. Crops, fruits, weeds, branches, leaves, and disease symptoms vary substantially in size, shape, color, maturity, orientation, and appearance. A perception model trained on one farm or season may not generalize reliably to another. Crop detection and phenotyping therefore require diverse datasets, robust AI models, confidence estimation, and mechanisms for continuous model improvement.

Precision agriculture increases the importance of connecting perception directly to action. In precision spraying, for example, the system must identify a target, determine its location, estimate the appropriate treatment, and activate a nozzle at the correct position and time. Similar perception-to-action pipelines appear in mechanical weeding, fertilization, thinning, and selective harvesting. Software latency and spatial calibration become operational variables because detection errors can immediately produce incorrect physical actions.

Selective harvesting represents one of the most demanding agricultural robotics applications. The robot must distinguish harvestable produce from leaves and branches, estimate maturity and three-dimensional position, select an approach trajectory, manipulate the crop without damaging it, and verify successful harvesting. The chapter structure therefore treats strawberry harvesting as both a dedicated software problem and an integrated field case combining perception, navigation, manipulation, and operational autonomy.

Agricultural manipulation is especially difficult because crops are deformable, fragile, irregular, and frequently occluded. Manipulators must operate around stems, leaves, support structures, and neighboring produce while controlling contact forces. Software must coordinate vision, depth estimation, motion planning, gripper control, force sensing, and recovery behaviors. Success cannot be measured only by grasp completion; cycle time, crop damage, missed targets, and harvesting quality are equally important.

Soil monitoring robots illustrate another class of agricultural automation in which mobility is integrated with scientific measurement. A robot may navigate predefined sampling locations, position a probe, acquire measurements, associate results with geographic coordinates, and generate spatial datasets for later analysis. The software challenge extends beyond robot control to synchronization, georeferencing, data quality validation, metadata management, and integration with farm-management or geographic information systems.

Greenhouses provide a more structured environment than open fields, but they introduce narrow aisles, repetitive visual features, dense vegetation, human workers, irrigation infrastructure, and restricted maneuvering space. GNSS reception may also be poor or unavailable inside greenhouse structures. Autonomous greenhouse robots therefore require localization and navigation methods that can operate independently of continuous satellite positioning while maintaining safe interaction with crops and people.

Fleet operation becomes important as agricultural robots move from experimental prototypes to commercial deployment. A single robot can automate one task, but large farms may require multiple machines working simultaneously across different fields. Fleet software must assign missions, coordinate routes, monitor robot state, manage charging or refueling, detect failures, and redistribute work when equipment becomes unavailable. Agricultural fleet management is consequently a distributed operational problem rather than merely a navigation problem.

Connectivity complicates fleet architecture because rural environments cannot always provide continuous high-bandwidth networking. Agricultural robots may move beyond reliable Wi-Fi, 4G, or 5G coverage and experience variable latency or complete communication loss. The application structure explicitly treats rural 4G/5G connectivity as a separate concern, reflecting the need for systems that can continue essential autonomous functions locally while synchronizing data when network connectivity becomes available.

This constraint encourages an edge-first software architecture. Safety-critical perception, localization, navigation, control, and task execution should remain available on the robot without depending on a remote server. Cloud or on-premise services can support fleet analytics, model training, historical data management, remote supervision, and optimization, but temporary network loss should not immediately stop a robot operating safely in the field. Local autonomy and remote intelligence therefore need clearly defined boundaries.

Reliability requirements also differ from laboratory robotics. Agricultural machines may operate for long periods in dust, moisture, heat, vibration, and mechanically demanding terrain. Software must detect degraded sensors, actuator faults, localization uncertainty, blocked routes, excessive wheel slip, communication failures, and abnormal task execution. Fault handling should move the system toward a safe operational state while preserving enough diagnostic information for maintenance personnel to understand the original failure.

Agricultural robotics also creates a significant data-management problem. Cameras, LiDAR, GNSS, machine telemetry, crop observations, environmental measurements, and task results can generate large volumes of spatially and temporally correlated information. Effective systems must associate robot data with fields, crop rows, individual plants, missions, and timestamps so that operational records can support agronomic analysis, AI training, traceability, maintenance, and future mission planning.

Software lifecycle management becomes increasingly important as deployed robots accumulate operational experience. Perception models may require retraining for new crops or seasons, navigation parameters may need adaptation to different terrain, and mission software may evolve as agricultural practices change. Version management, remote diagnostics, secure software updates, model deployment, rollback mechanisms, and reproducible configuration therefore become essential capabilities for maintaining geographically distributed agricultural robot fleets.

Commercial success ultimately depends on whether autonomy produces measurable agricultural value. A technically sophisticated robot may still fail commercially if it requires frequent intervention, operates too slowly, damages crops, cannot handle environmental variation, or imposes excessive maintenance costs. Evaluation must therefore combine autonomy metrics with hectares covered, crops processed, intervention frequency, task success rate, crop damage, chemical reduction, labor savings, energy consumption, uptime, and total operating cost.

The central software challenge is consequently not the implementation of a single superior algorithm. Agricultural autonomy requires a resilient system in which navigation, perception, manipulation, task planning, connectivity, fleet management, data infrastructure, safety, and recovery mechanisms cooperate under highly variable physical conditions. This broader software-system perspective connects agricultural applications with the volume\'s wider robotics foundations in localization, perception, planning, fleet intelligence, edge computing, and testing.

A mature agricultural robot should therefore be understood as a mobile Physical AI platform that continuously closes the loop between environmental observation and physical action. Sensors describe crops and terrain, AI interprets their meaning, planning determines the next operation, control executes that operation, and field results provide new evidence for future decisions. The competitiveness of agricultural robotics will increasingly depend on how reliably this closed loop can operate across farms, seasons, crops, and changing real-world conditions.

농업 로보틱스(Agricultural Robotics)는 개별 자동화 장비 중심의 형태에서 작물을 감지하고, 농경지 환경을 해석하며, 작업을 계획하고, 제한적인 인간의 감독만으로 농업 작업을 수행할 수 있는 소프트웨어 정의 자율 시스템(Software-Defined Autonomous System)으로 발전하고 있다. 적용 범위는 농경지 주행(Field Navigation), 작물 모니터링(Crop Monitoring), 정밀 살포(Precision Spraying), 선택적 수확(Selective Harvesting), 토양 분석(Soil Analysis), 온실 자동화(Greenhouse Automation), 농업 로봇 플릿(Agricultural Robot Fleet)의 협업 운영까지 확대되고 있다.

농업 로봇 시장(Agricultural Robot Market)은 여러 구조적인 압력에 의해 성장하고 있다. 농가는 노동력 부족(Labor Shortage), 인건비 상승, 농업 인력의 고령화, 생산성 향상 요구와 함께 물, 비료, 농약, 에너지 사용량을 줄여야 하는 문제에 직면하고 있다. 동시에 생산자는 더욱 일관된 작물 품질과 향상된 추적성(Traceability)을 요구받는다. 따라서 로봇의 가치는 단순한 노동력 대체가 아니라 반복 가능하고 데이터 기반(Data-Driven)의 농업 운영을 가능하게 하는 데 있다.

농업 자동화(Agricultural Automation)는 운영 환경이 부분적으로만 구조화되어 있다는 점에서 기존 공장 자동화(Factory Automation)와 근본적으로 다르다. 공장 로봇은 일반적으로 고정된 장비, 알려진 작업 공간, 제어된 조명, 반복적인 객체를 중심으로 동작한다. 반면 농업 로봇은 변화하는 지형, 진흙, 먼지, 비, 바람, 직사광선, 식생 성장, 불규칙한 작물 형상, 이동하는 작업자와 동물, 농기계, 계절 변화 등 지속적으로 변하는 환경을 상대해야 한다.

이러한 환경적 가변성(Environmental Variability)은 강건한 소프트웨어(Robust Software)의 구현을 상용화 과정의 핵심 기술 장벽으로 만든다. 건조한 아침에 안정적으로 동작했던 주행 알고리즘도 비가 내린 후 토양의 접지력이 변하거나 식물이 작물 열(Row)을 부분적으로 가리면 다르게 동작할 수 있다. 카메라 기반 인식(Camera-Based Perception) 역시 급격한 조명 변화, 그림자, 눈부심, 잎에 의한 가림, 시각적으로 유사한 배경의 영향을 받는다. 따라서 농업 소프트웨어는 센서 관측값이 항상 일정하다고 가정하기보다 불확실성(Uncertainty)을 견딜 수 있어야 한다.

위치 추정(Localization) 역시 중요한 문제이다. 실외 농업 로봇은 위성항법시스템(Global Navigation Satellite System, GNSS)과 실시간 이동측위(Real-Time Kinematic, RTK) 보정을 결합하여 높은 정확도의 전역 좌표(Global Coordinate)를 확보할 수 있지만, 나무, 온실, 건물, 언덕 등의 장애물 주변에서는 위성 신호 품질이 저하될 수 있다. 따라서 신뢰성 높은 자율주행을 위해서는 GNSS-RTK와 관성 센서(Inertial Sensor), 휠 오도메트리(Wheel Odometry), 카메라(Camera), 라이다(LiDAR) 등의 위치 추정 정보를 융합하고, 개별 센서의 신뢰도가 저하되더라도 안정적으로 동작할 수 있어야 한다.

주행 소프트웨어(Navigation Software)는 위치 추정 결과를 작물 열(Crop Row), 두둑 끝 회전 구간(Headland), 농로(Access Road), 불규칙한 농경지 경계에서의 안전한 움직임으로 변환해야 한다. 비교적 평탄한 바닥을 주행하는 창고 자율이동로봇(AMR)과 달리 농업 차량은 바퀴 미끄러짐(Wheel Slip), 경사면, 연약한 토양, 바퀴 자국, 식생, 배수로, 변화하는 차량 동역학을 고려해야 한다. 따라서 경로 계획(Path Planning)과 제어(Control)는 지형 인식(Terrain Awareness), 차량별 운동 제약조건, 계획된 궤적의 물리적 실행 가능성에 대한 지속적인 평가를 필요로 한다.

인지(Perception)는 농업 객체가 제조된 물체가 아니라 생물학적 대상이라는 점에서 또 다른 어려운 소프트웨어 문제를 만든다. 작물, 과일, 잡초, 가지, 잎, 질병 증상은 크기, 형태, 색상, 성숙도, 방향, 외관에서 큰 차이를 보인다. 한 농장이나 특정 계절에서 학습된 인식 모델(Perception Model)이 다른 환경에서도 안정적으로 일반화된다고 보장할 수 없다. 따라서 작물 감지(Crop Detection)와 표현형 분석(Phenotyping)에는 다양한 데이터셋(Dataset), 강건한 인공지능 모델(AI Model), 신뢰도 추정(Confidence Estimation), 지속적인 모델 개선 체계가 필요하다.

정밀 농업(Precision Agriculture)은 인지 결과와 물리적 행동(Action)을 직접 연결하는 능력의 중요성을 높인다. 예를 들어 정밀 살포(Precision Spraying) 시스템은 대상을 식별하고 위치를 결정하며 적절한 처리량을 계산한 다음 정확한 위치와 시점에서 노즐을 작동시켜야 한다. 이와 유사한 인지-행동 파이프라인(Perception-to-Action Pipeline)은 기계식 제초, 비료 살포, 솎아내기, 선택적 수확에서도 사용된다. 감지 오류가 즉시 잘못된 물리적 행동으로 이어질 수 있으므로 소프트웨어 지연시간(Software Latency)과 공간 보정(Spatial Calibration)은 실제 운영 성능을 결정하는 중요한 변수가 된다.

선택적 수확(Selective Harvesting)은 농업 로보틱스에서 가장 어려운 응용 분야 중 하나이다. 로봇은 수확 가능한 농산물을 잎과 가지에서 구별하고, 성숙도와 3차원 위치를 추정하며, 접근 궤적을 선택하고, 작물을 손상시키지 않으면서 조작한 후 수확 성공 여부를 검증해야 한다. 따라서 딸기 수확(Strawberry Harvesting)은 독립적인 소프트웨어 문제인 동시에 인지, 주행, 조작(Manipulation), 운영 자율성(Operational Autonomy)을 통합하는 대표적인 현장 사례(Field Case)가 된다.

농업용 조작(Agricultural Manipulation)은 작물이 변형 가능하고(Deformable), 손상되기 쉬우며, 불규칙하고, 다른 식물 조직에 의해 자주 가려지기 때문에 특히 어렵다. 매니퓰레이터(Manipulator)는 접촉력을 제어하면서 줄기, 잎, 지지 구조물, 주변 농산물을 피해 동작해야 한다. 이를 위해 소프트웨어는 비전(Vision), 깊이 추정(Depth Estimation), 모션 계획(Motion Planning), 그리퍼 제어(Gripper Control), 힘 센싱(Force Sensing), 복구 행동(Recovery Behavior)을 조정해야 한다. 성공 여부 역시 단순한 파지(Grasp) 완료만으로 평가할 수 없으며 작업 주기 시간(Cycle Time), 작물 손상, 미수확 대상, 수확 품질까지 함께 고려해야 한다.

토양 모니터링 로봇(Soil Monitoring Robot)은 이동성(Mobility)과 과학적 측정(Scientific Measurement)이 통합되는 또 다른 형태의 농업 자동화를 보여준다. 로봇은 사전에 정의된 샘플링 위치로 이동하여 탐침(Probe)을 배치하고, 측정값을 획득하며, 결과를 지리 좌표와 연결하고, 후속 분석을 위한 공간 데이터셋(Spatial Dataset)을 생성할 수 있다. 이 과정에서 소프트웨어 문제는 로봇 제어뿐만 아니라 동기화(Synchronization), 지리참조(Georeferencing), 데이터 품질 검증(Data Quality Validation), 메타데이터 관리(Metadata Management), 농장 관리 시스템 또는 지리정보시스템(GIS)과의 통합까지 확장된다.

온실(Greenhouse)은 노지보다 구조화된 환경을 제공하지만 좁은 통로, 반복적인 시각 특징, 밀집된 식생, 작업자, 관개 시설, 제한된 회전 공간이라는 새로운 문제를 가진다. 또한 온실 구조물 내부에서는 GNSS 신호가 약하거나 사용할 수 없는 경우가 있다. 따라서 자율 온실 로봇(Autonomous Greenhouse Robot)은 지속적인 위성 위치 정보 없이도 작동할 수 있는 위치 추정 및 주행 기술을 필요로 하며, 작물과 사람 주변에서 안전한 동작을 유지해야 한다.

농업 로봇이 실험적 시제품에서 상용 배치(Commercial Deployment) 단계로 발전하면서 플릿 운영(Fleet Operation)의 중요성도 커진다. 한 대의 로봇은 하나의 작업을 자동화할 수 있지만 대규모 농장은 서로 다른 농경지에서 동시에 작업하는 여러 대의 장비를 필요로 할 수 있다. 플릿 소프트웨어(Fleet Software)는 임무 할당, 경로 조정, 로봇 상태 모니터링, 충전 또는 연료 보급 관리, 고장 감지, 장비 사용 불가 시 작업 재분배를 수행해야 한다. 따라서 농업 플릿 관리(Agricultural Fleet Management)는 단순한 주행 문제가 아니라 분산 운영 문제(Distributed Operational Problem)가 된다.

농촌 환경에서는 지속적인 고대역폭 네트워크(High-Bandwidth Network)를 항상 확보할 수 없기 때문에 연결성(Connectivity)은 플릿 아키텍처를 더욱 복잡하게 만든다. 농업 로봇은 안정적인 와이파이(Wi-Fi), 4G, 5G 통신 범위를 벗어나 이동할 수 있으며 가변적인 지연시간이나 완전한 통신 단절을 경험할 수 있다. 따라서 시스템은 필수적인 자율 기능을 로컬(Local)에서 계속 수행하면서 네트워크 연결이 가능해졌을 때 데이터를 동기화할 수 있어야 한다.

이러한 제약은 엣지 우선 소프트웨어 아키텍처(Edge-First Software Architecture)의 필요성을 높인다. 안전에 중요한 인지, 위치 추정, 주행, 제어, 작업 실행 기능은 원격 서버에 의존하지 않고 로봇 자체에서 사용할 수 있어야 한다. 클라우드(Cloud) 또는 온프레미스(On-Premise) 서비스는 플릿 분석, 모델 학습, 이력 데이터 관리, 원격 감독, 최적화를 지원할 수 있지만 일시적인 네트워크 장애가 안전하게 작업하던 로봇을 즉시 정지시키는 구조가 되어서는 안 된다. 따라서 로컬 자율성(Local Autonomy)과 원격 지능(Remote Intelligence) 사이의 경계를 명확하게 정의해야 한다.

신뢰성(Reliability) 요구사항 역시 실험실 로보틱스와 다르다. 농업 기계는 먼지, 습기, 고온, 진동, 기계적으로 가혹한 지형에서 장시간 동작할 수 있다. 소프트웨어는 성능이 저하된 센서, 액추에이터 고장, 위치 추정 불확실성, 차단된 경로, 과도한 바퀴 미끄러짐, 통신 장애, 비정상적인 작업 실행을 감지해야 한다. 고장 처리(Fault Handling)는 시스템을 안전한 운영 상태로 전환하면서 유지보수 담당자가 원래의 고장 원인을 파악할 수 있도록 충분한 진단 정보를 보존해야 한다.

농업 로보틱스는 상당한 데이터 관리(Data Management) 문제도 발생시킨다. 카메라, 라이다, GNSS, 장비 텔레메트리(Telemetry), 작물 관측 정보, 환경 측정값, 작업 결과는 공간적·시간적으로 연관된 대규모 데이터를 생성할 수 있다. 효과적인 시스템은 로봇 데이터를 농경지, 작물 열, 개별 식물, 임무, 타임스탬프(Timestamp)와 연결해야 하며, 이러한 운영 기록은 농업 분석, 인공지능 학습, 추적성, 유지보수, 향후 임무 계획에 활용될 수 있어야 한다.

배치된 로봇이 현장 경험을 축적할수록 소프트웨어 생명주기 관리(Software Lifecycle Management)의 중요성도 증가한다. 새로운 작물이나 계절에 맞추어 인식 모델을 재학습해야 할 수 있고, 서로 다른 지형에 맞게 주행 매개변수를 조정해야 하며, 농업 방식이 변화하면서 임무 소프트웨어도 발전해야 한다. 따라서 버전 관리(Version Management), 원격 진단(Remote Diagnostics), 안전한 소프트웨어 업데이트, 모델 배포(Model Deployment), 롤백(Rollback), 재현 가능한 구성 관리(Reproducible Configuration)는 지리적으로 분산된 농업 로봇 플릿을 유지하기 위한 핵심 기능이 된다.

상업적 성공(Commercial Success)은 궁극적으로 자율화가 측정 가능한 농업적 가치(Agricultural Value)를 만들어 내는지에 의해 결정된다. 기술적으로 정교한 로봇이라도 빈번한 인간 개입이 필요하거나, 작업 속도가 지나치게 느리거나, 작물을 손상시키거나, 환경 변화에 대응하지 못하거나, 유지보수 비용이 지나치게 높다면 상업적으로 실패할 수 있다. 따라서 평가에는 자율성 지표뿐만 아니라 작업 면적, 처리 작물 수, 개입 빈도, 작업 성공률, 작물 손상률, 농약 절감량, 인건비 절감, 에너지 소비, 가동률(Uptime), 총운영비용(Total Operating Cost)이 포함되어야 한다.

따라서 핵심 소프트웨어 과제는 하나의 뛰어난 알고리즘을 구현하는 것이 아니다. 농업 자율 시스템(Agricultural Autonomous System)은 매우 변화가 큰 물리적 환경에서 주행, 인지, 조작, 작업 계획(Task Planning), 연결성, 플릿 관리, 데이터 인프라(Data Infrastructure), 안전, 복구 메커니즘(Recovery Mechanism)이 서로 협력하는 강건한 시스템을 필요로 한다. 이러한 소프트웨어 시스템 관점은 농업 응용을 위치 추정, 인지, 계획, 플릿 지능(Fleet Intelligence), 엣지 컴퓨팅(Edge Computing), 시험 및 검증(Testing and Validation)과 같은 로보틱스 기반 기술과 연결한다.

성숙한 농업 로봇(Agricultural Robot)은 환경 관측(Environmental Observation)과 물리적 행동(Physical Action) 사이의 폐루프(Closed Loop)를 지속적으로 수행하는 이동형 피지컬 AI 플랫폼(Mobile Physical AI Platform)으로 이해할 수 있다. 센서는 작물과 지형을 관측하고, 인공지능(AI)은 그 의미를 해석하며, 계획 시스템은 다음 작업을 결정하고, 제어 시스템은 해당 작업을 실행한다. 그리고 현장 결과는 이후 의사결정을 위한 새로운 근거를 제공한다. 농업 로보틱스의 경쟁력은 이러한 폐루프를 서로 다른 농장, 계절, 작물, 그리고 지속적으로 변화하는 실제 환경에서 얼마나 안정적으로 운영할 수 있는가에 의해 점점 더 크게 결정될 것이다.

##  

## 08.02. Field Navigation GPS RTK Row Following [w/Code]

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

Field navigation is a foundational capability for agricultural robots because most field operations require the vehicle to follow repeatable trajectories while maintaining accurate position relative to crops. Seeding, spraying, weeding, phenotyping, soil sampling, and harvesting all depend on reliable mobility. Agricultural navigation therefore combines global positioning, local perception, trajectory generation, and vehicle control into a continuous autonomy loop.

Global Navigation Satellite System positioning provides the basic geographic reference for outdoor agricultural robots. Standard GNSS can determine approximate vehicle position, but its normal accuracy is often insufficient when a robot must travel through narrow crop rows without damaging plants. Real-Time Kinematic positioning improves this capability by applying correction information to carrier-phase satellite measurements, enabling centimeter-level positioning under suitable satellite and communication conditions.

An RTK system commonly consists of a GNSS receiver on the robot and correction information obtained from a local base station or network-based correction service. The rover receiver continuously estimates its position while incorporating correction data to reduce satellite-related errors. The navigation software must monitor RTK solution quality because the localization state can change between fixed, float, degraded, and unavailable conditions during field operation.

Centimeter-level coordinates alone do not guarantee reliable navigation. Agricultural vehicles experience wheel slip, vibration, pitch and roll, uneven terrain, and temporary GNSS degradation. A practical localization system therefore combines GNSS-RTK with an Inertial Measurement Unit, wheel odometry, steering information, and potentially cameras or LiDAR. Sensor fusion provides a smoother estimate of position, orientation, velocity, and vehicle motion than any single sensor can provide independently.

The coordinate system used by the navigation stack must also be carefully managed. GNSS measurements are expressed in geographic or global coordinates, while motion planning and vehicle control are usually easier to perform in a local Cartesian frame. Software therefore transforms latitude, longitude, and altitude into a field-relative coordinate representation and maintains consistent transformations among global, map, vehicle, sensor, and implement reference frames.

Before autonomous work begins, the system may define field boundaries, exclusion zones, crop rows, headlands, access routes, and task-specific waypoints. These elements form an operational field map rather than a conventional road map. The map describes where the robot may travel, where crops or obstacles are expected, and where turning maneuvers can occur. Accurate georeferencing allows the same agricultural mission to be repeated across multiple operating sessions.

Row following converts this global navigation information into precise motion relative to the crop structure. A row may be represented by recorded GNSS waypoints, a fitted geometric line or curve, or features detected directly from cameras and LiDAR. The robot estimates lateral displacement and heading error relative to the desired row centerline and continuously generates steering commands that reduce these errors while maintaining an appropriate forward velocity.

GNSS-based row following works particularly well when crop rows were created from known georeferenced planting trajectories. The navigation system can reuse these trajectories for later spraying, monitoring, or harvesting operations. This creates spatial consistency across the agricultural lifecycle. However, actual crop geometry may deviate from the original reference because of planting errors, terrain effects, vegetation growth, or inaccurate field records, requiring local perception to refine the trajectory.

Vision-based row detection can identify crop boundaries, vegetation lines, soil corridors, or vanishing-point structures from camera images. LiDAR can provide complementary geometric information about vegetation and surrounding terrain. These observations allow the robot to estimate its local relationship to the physical row even when GNSS accuracy deteriorates. Combining global RTK localization with local row perception provides stronger robustness than relying exclusively on either method.

The fusion strategy should account for measurement confidence rather than treating every sensor as equally reliable. GNSS uncertainty can increase near trees or structures, cameras can become unreliable under glare or shadows, and LiDAR observations can change as vegetation density increases. Navigation software should monitor measurement quality and dynamically determine how much each information source contributes to the final localization and row-following estimate.

Trajectory generation translates the desired crop row into a path that satisfies vehicle kinematic constraints. Agricultural platforms may use differential drive, Ackermann steering, skid steering, articulated steering, or other configurations, and each has different curvature and turning limitations. A controller must therefore consider wheelbase, steering limits, minimum turning radius, velocity, implement geometry, and the offset between the positioning sensor and the physical working tool.

Path-tracking controllers can use geometric or model-based methods to minimize cross-track and heading errors. The objective is not merely to keep the vehicle chassis near a reference line. A spraying nozzle, mechanical weeder, sampling probe, or harvesting mechanism may require greater positional accuracy than the vehicle body itself. Navigation accuracy should consequently be evaluated at the agricultural implement where the physical task is actually performed.

Headland navigation introduces another important problem because the robot must leave one row and enter the next without crossing prohibited areas or damaging crops. The system identifies the end of the current row, reduces speed when necessary, generates a feasible turning trajectory, and aligns the vehicle with the target row. The maneuver depends on row spacing, available headland width, vehicle dimensions, steering geometry, and attached implements.

Obstacle handling must operate simultaneously with nominal row following. Workers, animals, tractors, irrigation equipment, fallen branches, rocks, or unexpected objects may appear on the planned route. Local perception identifies these hazards and the navigation system determines whether to stop, slow down, temporarily deviate from the row, or request operator assistance. Safety behavior must take priority over maintaining the nominal agricultural trajectory.

Terrain conditions directly affect path-tracking performance. Soft soil, mud, slopes, and uneven surfaces can produce significant differences between commanded and actual vehicle motion. Wheel odometry becomes less reliable when tires slip, while steering responses can vary with load and ground condition. Navigation software should therefore estimate tracking performance continuously and reduce speed or modify control behavior when vehicle motion becomes inconsistent with the predicted model.

Loss of RTK corrections must be treated as a normal operational condition rather than an exceptional software failure. Rural communication networks can be intermittent, and satellite visibility can change as the robot moves. When RTK quality decreases, the system can continue temporarily using inertial estimation, odometry, and local perception while increasing localization uncertainty. If uncertainty exceeds the safe operating threshold, the robot should slow down or transition to a controlled stop.

Navigation software also needs explicit recovery behavior. A robot may become unable to identify a crop row, deviate beyond an allowed corridor, encounter persistent wheel slip, or reach a location inconsistent with the planned mission. Recovery can involve stopping, reversing to a previously valid pose, reacquiring the row, recalculating the local trajectory, or requesting remote assistance. Autonomous recovery prevents minor navigation errors from becoming prolonged field interruptions.

Operational logging is essential for diagnosing these events. GNSS position, RTK status, correction age, satellite information, IMU measurements, wheel velocities, steering commands, estimated pose, cross-track error, perception confidence, controller output, and safety events should be synchronized with timestamps. These records allow engineers to distinguish localization problems from perception errors, control instability, terrain effects, and mechanical failures during field testing.

Performance evaluation should extend beyond average localization accuracy. Important measures include cross-track error, heading error, row completion rate, headland-turn success, intervention frequency, RTK availability, localization recovery time, obstacle response, and task-specific implement accuracy. Percentile and worst-case errors are particularly important because a small number of large deviations may damage crops even when the average navigation error appears acceptable.

The resulting architecture forms a layered navigation system in which GNSS-RTK provides precise global positioning, inertial and odometric sensing maintain motion continuity, local perception identifies the physical crop structure, planning generates feasible field trajectories, and control converts those trajectories into vehicle motion. This structure supports the chapter\'s progression from field navigation toward crop perception, precision spraying, harvesting, soil sampling, greenhouse navigation, and agricultural fleet operation.

Reliable row following ultimately depends on maintaining agreement between the digital field representation and the physical environment. The robot must continuously answer where it is globally, where the actual crop row lies locally, how confidently those estimates can be trusted, and what motion remains safe. By combining RTK positioning, multi-sensor localization, crop-row perception, trajectory planning, control, and recovery, agricultural robots can achieve the repeatable mobility required for practical autonomous field operations.

농경지 주행(Field Navigation)은 대부분의 농업 작업에서 로봇이 작물에 대한 정확한 위치를 유지하면서 반복 가능한 궤적을 따라 이동해야 하기 때문에 농업 로봇(Agricultural Robot)의 핵심 기반 기능이다. 파종(Seeding), 살포(Spraying), 제초(Weeding), 표현형 분석(Phenotyping), 토양 샘플링(Soil Sampling), 수확(Harvesting)은 모두 신뢰성 높은 이동성에 의존한다. 따라서 농업 주행은 전역 위치 측정(Global Positioning), 지역 인지(Local Perception), 궤적 생성(Trajectory Generation), 차량 제어(Vehicle Control)를 연속적인 자율주행 루프(Autonomy Loop)로 통합한다.

위성항법시스템(Global Navigation Satellite System, GNSS)은 실외 농업 로봇에 기본적인 지리적 기준을 제공한다. 일반적인 GNSS는 차량의 대략적인 위치를 결정할 수 있지만, 로봇이 작물을 손상시키지 않고 좁은 작물 열(Crop Row) 사이를 주행해야 하는 경우 일반적인 위치 정확도만으로는 충분하지 않은 경우가 많다. 실시간 이동측위(Real-Time Kinematic, RTK)는 반송파 위상(Carrier-Phase) 위성 측정값에 보정 정보를 적용하여 이러한 성능을 향상시키며, 적절한 위성 및 통신 조건에서는 센티미터 수준의 위치 측정(Centimeter-Level Positioning)을 가능하게 한다.

RTK 시스템(RTK System)은 일반적으로 로봇에 장착된 GNSS 수신기와 로컬 기준국(Local Base Station) 또는 네트워크 기반 보정 서비스(Network-Based Correction Service)에서 제공되는 보정 정보로 구성된다. 이동국 수신기(Rover Receiver)는 위성과 관련된 오차를 줄이기 위해 보정 데이터를 적용하면서 지속적으로 위치를 추정한다. 농경지 작업 중 위치 추정 상태가 고정해(Fixed), 부동해(Float), 성능 저하(Degraded), 사용 불가(Unavailable) 상태 사이에서 변화할 수 있으므로 주행 소프트웨어는 RTK 솔루션의 품질을 지속적으로 감시해야 한다.

센티미터 수준의 좌표만으로 신뢰성 높은 주행이 보장되는 것은 아니다. 농업 차량은 바퀴 미끄러짐(Wheel Slip), 진동(Vibration), 피치(Pitch)와 롤(Roll), 불규칙한 지형, 일시적인 GNSS 성능 저하를 경험한다. 따라서 실용적인 위치 추정 시스템(Localization System)은 GNSS-RTK를 관성측정장치(Inertial Measurement Unit, IMU), 휠 오도메트리(Wheel Odometry), 조향 정보(Steering Information), 필요에 따라 카메라(Camera) 또는 라이다(LiDAR)와 결합한다. 센서 융합(Sensor Fusion)은 개별 센서만 사용하는 것보다 위치, 자세, 속도, 차량 움직임을 더욱 안정적으로 추정할 수 있도록 한다.

주행 스택(Navigation Stack)에서 사용하는 좌표계(Coordinate System) 역시 세심하게 관리해야 한다. GNSS 측정값은 지리 좌표(Geographic Coordinate) 또는 전역 좌표(Global Coordinate)로 표현되는 반면, 모션 계획(Motion Planning)과 차량 제어는 일반적으로 지역 직교 좌표계(Local Cartesian Frame)에서 수행하는 것이 더 용이하다. 따라서 소프트웨어는 위도, 경도, 고도를 농경지 기준 좌표 표현(Field-Relative Coordinate Representation)으로 변환하고 전역, 지도, 차량, 센서, 작업 장치 좌표 프레임 사이의 일관된 좌표 변환을 유지해야 한다.

자율 작업이 시작되기 전에 시스템은 농경지 경계(Field Boundary), 진입 금지 구역(Exclusion Zone), 작물 열(Crop Row), 두둑 끝 회전 구역(Headland), 접근 경로(Access Route), 작업별 웨이포인트(Waypoint)를 정의할 수 있다. 이러한 요소는 일반적인 도로 지도와 다른 운영용 농경지 지도(Operational Field Map)를 구성한다. 이 지도는 로봇이 이동할 수 있는 영역, 작물이나 장애물이 예상되는 위치, 회전 기동이 가능한 위치를 정의한다. 정확한 지리참조(Georeferencing)를 사용하면 여러 작업 세션에 걸쳐 동일한 농업 임무를 반복할 수 있다.

작물 열 추종(Row Following)은 이러한 전역 주행 정보를 작물 구조에 대한 정밀한 움직임으로 변환한다. 작물 열은 기록된 GNSS 웨이포인트, 피팅된 기하학적 직선 또는 곡선, 카메라와 라이다를 통해 직접 감지된 특징으로 표현할 수 있다. 로봇은 목표 작물 열의 중심선에 대한 횡방향 편차(Lateral Displacement)와 방향 오차(Heading Error)를 추정하고, 적절한 전진 속도를 유지하면서 이러한 오차를 감소시키는 조향 명령을 지속적으로 생성한다.

GNSS 기반 작물 열 추종(GNSS-Based Row Following)은 작물 열이 이미 지리참조된 파종 궤적(Georeferenced Planting Trajectory)을 기반으로 생성된 경우 특히 효과적이다. 주행 시스템은 이후의 살포, 모니터링, 수확 작업에서 이러한 궤적을 다시 사용할 수 있다. 이를 통해 농업 생산주기 전반에 걸쳐 공간적 일관성(Spatial Consistency)을 확보할 수 있다. 그러나 실제 작물 형상은 파종 오차, 지형 영향, 식생 성장, 부정확한 농경지 기록으로 인해 원래 기준과 달라질 수 있으므로 지역 인지(Local Perception)를 이용하여 궤적을 보정해야 한다.

비전 기반 작물 열 감지(Vision-Based Row Detection)는 카메라 영상에서 작물 경계, 식생 라인, 토양 통로, 소실점 구조(Vanishing-Point Structure)를 식별할 수 있다. 라이다는 식생과 주변 지형에 대한 보완적인 기하학 정보를 제공할 수 있다. 이러한 관측을 이용하면 GNSS 정확도가 저하되더라도 로봇과 실제 작물 열 사이의 지역적 관계를 추정할 수 있다. 전역 RTK 위치 추정과 지역 작물 열 인지를 결합하면 어느 하나의 방법에만 의존하는 것보다 높은 강건성(Robustness)을 확보할 수 있다.

융합 전략(Fusion Strategy)은 모든 센서의 신뢰성을 동일하게 취급하기보다 측정 신뢰도(Measurement Confidence)를 고려해야 한다. 나무나 구조물 주변에서는 GNSS 불확실성이 증가할 수 있고, 카메라는 눈부심이나 그림자에 의해 신뢰성이 낮아질 수 있으며, 라이다 관측값은 식생 밀도가 증가하면서 달라질 수 있다. 주행 소프트웨어는 측정 품질을 감시하고 각각의 정보원이 최종 위치 추정 및 작물 열 추종 결과에 어느 정도 기여해야 하는지를 동적으로 결정해야 한다.

궤적 생성(Trajectory Generation)은 목표 작물 열을 차량의 운동학적 제약조건(Kinematic Constraint)을 만족하는 경로로 변환한다. 농업 플랫폼은 차동 구동(Differential Drive), 애커먼 조향(Ackermann Steering), 스키드 조향(Skid Steering), 굴절식 조향(Articulated Steering) 등 다양한 구조를 사용할 수 있으며 각각 곡률과 회전 제약조건이 다르다. 따라서 제어기는 휠베이스(Wheelbase), 조향 한계, 최소 회전반경, 속도, 작업 장치 형상, 위치 센서와 실제 작업 도구 사이의 오프셋(Offset)을 고려해야 한다.

경로 추종 제어기(Path-Tracking Controller)는 기하학적 또는 모델 기반 방법을 사용하여 횡방향 오차(Cross-Track Error)와 방향 오차를 최소화할 수 있다. 여기서 목표는 단순히 차량 차체를 기준선 근처에 유지하는 것만이 아니다. 살포 노즐, 기계식 제초 장치, 샘플링 탐침 또는 수확 장치는 차량 차체 자체보다 더 높은 위치 정확도를 요구할 수 있다. 따라서 주행 정확도는 실제 물리적 농업 작업을 수행하는 작업 장치(Agricultural Implement)의 위치를 기준으로 평가해야 한다.

두둑 끝 회전 주행(Headland Navigation)은 로봇이 금지 구역을 침범하거나 작물을 손상시키지 않고 현재 작물 열을 빠져나와 다음 작물 열에 진입해야 하므로 또 하나의 중요한 문제를 만든다. 시스템은 현재 작물 열의 끝을 식별하고 필요한 경우 속도를 낮추며, 실행 가능한 회전 궤적을 생성한 후 목표 작물 열에 차량을 정렬한다. 이러한 기동은 작물 열 간격, 사용 가능한 회전 공간의 폭, 차량 크기, 조향 구조, 부착된 작업 장치의 형상에 따라 달라진다.

장애물 처리(Obstacle Handling)는 정상적인 작물 열 추종과 동시에 수행되어야 한다. 작업자, 동물, 트랙터, 관개 장비, 떨어진 나뭇가지, 돌 또는 예상하지 못한 물체가 계획된 경로에 나타날 수 있다. 지역 인지 시스템(Local Perception System)은 이러한 위험 요소를 식별하고 주행 시스템은 정지, 감속, 일시적인 작물 열 이탈 또는 작업자 지원 요청 여부를 결정한다. 안전 행동(Safety Behavior)은 항상 정상적인 농업 궤적 유지보다 우선해야 한다.

지형 조건(Terrain Condition)은 경로 추종 성능에 직접적인 영향을 준다. 연약한 토양, 진흙, 경사면, 불규칙한 지면은 명령된 차량 움직임과 실제 움직임 사이에 상당한 차이를 발생시킬 수 있다. 타이어가 미끄러지면 휠 오도메트리의 신뢰성이 감소하며 하중과 지면 상태에 따라 조향 응답도 달라질 수 있다. 따라서 주행 소프트웨어는 추종 성능을 지속적으로 추정하고 차량 움직임이 예측 모델과 일치하지 않을 경우 속도를 낮추거나 제어 동작을 변경해야 한다.

RTK 보정 정보의 손실은 예외적인 소프트웨어 고장이 아니라 정상적인 운영 조건 중 하나로 처리해야 한다. 농촌 지역의 통신 네트워크는 간헐적으로 단절될 수 있으며 로봇의 이동에 따라 위성 가시성(Satellite Visibility)도 달라질 수 있다. RTK 품질이 저하되면 시스템은 위치 불확실성을 증가시키면서 관성 추정(Inertial Estimation), 오도메트리, 지역 인지를 이용해 일시적으로 작업을 지속할 수 있다. 불확실성이 안전 운영 임계값을 초과하면 로봇은 감속하거나 제어된 정지(Controlled Stop) 상태로 전환해야 한다.

주행 소프트웨어에는 명시적인 복구 동작(Recovery Behavior)도 필요하다. 로봇이 작물 열을 식별하지 못하거나 허용된 주행 통로를 벗어나거나 지속적인 바퀴 미끄러짐을 경험하거나 계획된 임무와 일치하지 않는 위치에 도달할 수 있다. 복구 과정에는 정지, 이전의 유효한 위치로 후진, 작물 열 재인식, 지역 궤적 재계산, 원격 지원 요청 등이 포함될 수 있다. 자율 복구(Autonomous Recovery)는 작은 주행 오류가 장시간의 농경지 작업 중단으로 확대되는 것을 방지한다.

이러한 문제를 진단하기 위해서는 운영 로그(Operational Logging)가 필수적이다. GNSS 위치, RTK 상태, 보정 정보 경과 시간(Correction Age), 위성 정보, IMU 측정값, 휠 속도, 조향 명령, 추정 자세, 횡방향 오차, 인지 신뢰도, 제어기 출력, 안전 이벤트를 타임스탬프와 함께 동기화하여 기록해야 한다. 이러한 기록을 이용하면 현장 시험(Field Testing)에서 위치 추정 문제와 인지 오류, 제어 불안정성, 지형 영향, 기계적 고장을 구분할 수 있다.

성능 평가는 평균 위치 정확도만으로 제한해서는 안 된다. 중요한 지표에는 횡방향 오차, 방향 오차, 작물 열 완주율(Row Completion Rate), 두둑 끝 회전 성공률(Headland-Turn Success), 인간 개입 빈도, RTK 가용률, 위치 추정 복구 시간, 장애물 대응 성능, 작업 장치별 정확도가 포함된다. 특히 백분위수 오차(Percentile Error)와 최악 조건 오차(Worst-Case Error)가 중요하다. 평균 주행 오차가 작더라도 소수의 큰 편차가 작물을 손상시킬 수 있기 때문이다.

결과적으로 전체 아키텍처는 GNSS-RTK가 정밀한 전역 위치 정보를 제공하고, 관성 센싱과 오도메트리가 움직임의 연속성을 유지하며, 지역 인지가 실제 작물 구조를 식별하고, 계획 시스템이 실행 가능한 농경지 궤적을 생성하며, 제어 시스템이 이러한 궤적을 실제 차량 움직임으로 변환하는 계층형 주행 시스템(Layered Navigation System)을 형성한다. 이러한 구조는 농경지 주행에서 작물 인지, 정밀 살포, 수확, 토양 샘플링, 온실 주행, 농업 플릿 운영으로 이어지는 기술적 기반을 제공한다.

신뢰성 높은 작물 열 추종은 궁극적으로 디지털 농경지 표현(Digital Field Representation)과 실제 물리적 환경 사이의 일관성을 유지하는 것에 달려 있다. 로봇은 자신의 전역 위치가 어디인지, 실제 작물 열이 지역적으로 어디에 존재하는지, 이러한 추정값을 어느 정도 신뢰할 수 있는지, 어떤 움직임이 안전한지를 지속적으로 판단해야 한다. RTK 위치 측정, 다중 센서 위치 추정(Multi-Sensor Localization), 작물 열 인지, 궤적 계획, 제어, 복구 기능을 결합함으로써 농업 로봇은 실질적인 자율 농경지 작업에 필요한 반복 가능하고 정밀한 이동성을 확보할 수 있다.

##  

## 08.03. Crop Detection and Phenotyping AI Vision [w/Code]

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

Crop detection and phenotyping are central perception capabilities for agricultural robots because autonomous machines must understand not only where plants are located but also their biological condition. Cameras and AI vision transform visual observations into structured information about crops, fruits, leaves, weeds, growth stages, and plant health. This perception layer supports precision spraying, selective harvesting, monitoring, and data-driven farm management.

Crop detection begins with image acquisition from cameras mounted on mobile robots, tractors, manipulators, greenhouse platforms, or fixed monitoring systems. RGB cameras provide detailed color and texture information, while depth, stereo, multispectral, or other sensing modalities can add geometric and spectral information. The camera configuration must consider viewing distance, field of view, motion, illumination, crop geometry, and the agricultural task being performed.

Agricultural imagery is considerably more variable than imagery captured in controlled industrial environments. Plants continuously change in size, shape, orientation, color, and density as they grow. Leaves overlap, fruits are partially hidden, weeds resemble crops, and soil appearance changes with moisture. Sunlight introduces shadows, glare, and strong exposure variations. AI vision must therefore recognize biological targets despite substantial intra-class variation and environmental uncertainty.

Object detection models can identify crops, fruits, flowers, weeds, disease symptoms, or other agricultural targets and return their locations as bounding boxes. These detections provide a useful first level of scene understanding for mobile robots. A harvesting system can identify candidate fruits, while a precision spraying robot can distinguish treatment targets from surrounding vegetation and associate detections with locations in the robot coordinate system.

When bounding boxes are insufficient, image segmentation provides more precise spatial information. Semantic segmentation classifies image pixels into categories such as crop, weed, soil, fruit, or background, while instance segmentation separates individual objects belonging to the same class. Pixel-level information is valuable for estimating plant boundaries, vegetation coverage, fruit shape, leaf area, and the precise location of targets for manipulation or selective treatment.

Detection outputs must often be converted from two-dimensional image coordinates into three-dimensional physical coordinates. Depth cameras, stereo vision, LiDAR, or geometric reconstruction can estimate target distance and position relative to the robot. Camera calibration and coordinate transformation then connect the detected crop with the vehicle, manipulator, or agricultural implement. This transformation is essential when perception must directly trigger a physical operation.

Phenotyping extends agricultural vision beyond simple object recognition. Plant phenotyping measures observable characteristics associated with plant structure, growth, development, and condition. A robotic phenotyping system can estimate attributes such as plant height, canopy size, leaf area, fruit count, growth rate, flowering state, or maturity. Repeated measurements allow robots to convert visual observations into longitudinal records of crop development.

Fruit counting is a representative phenotyping task because individual detections can be aggregated into estimates of crop load and potential yield. However, repeated observations create a risk of counting the same fruit multiple times as the robot moves through the field. Tracking, localization, and spatial association are therefore important. A useful agricultural vision system must determine not only what was detected but whether the observation represents a new physical object.

Maturity estimation introduces another level of semantic interpretation. Color, texture, shape, size, and potentially spectral characteristics can be used to estimate whether fruit is immature, ready for harvest, overripe, or damaged. The output may be represented as discrete categories or continuous maturity scores. For harvesting robots, maturity estimation directly influences task planning because only appropriate targets should be selected for manipulation.

Plant health monitoring can similarly use AI vision to identify visual symptoms associated with stress, nutrient deficiency, pest damage, or disease. These symptoms may initially occupy only a small portion of a leaf or canopy, making resolution and viewing geometry important. The system must also distinguish actual biological symptoms from shadows, dirt, water, physical damage, or normal color variation to avoid unnecessary agricultural treatment.

Dataset quality is one of the most important factors determining field performance. Training images should represent different farms, crop varieties, growth stages, seasons, illumination conditions, camera viewpoints, weather conditions, and levels of occlusion. A model trained primarily on clean and well-exposed images may perform poorly when deployed under strong sunlight, after rain, or in dense vegetation. Dataset diversity is therefore part of system robustness.

Annotation strategy depends on the intended task. Bounding boxes may be sufficient for detection and counting, while segmentation masks provide detailed plant geometry. Keypoints can represent stems, fruit attachment points, flowers, or structural landmarks, and continuous labels can describe size or maturity. Annotation quality directly influences model behavior, so ambiguous agricultural categories require consistent definitions and quality-control procedures.

Data augmentation can increase apparent training diversity by modifying brightness, contrast, scale, orientation, crop regions, blur, or other image properties. Agricultural augmentation should nevertheless remain physically meaningful. Unrealistic transformations can create samples that do not represent plausible field conditions. The objective is to expose the model to realistic variation that it will encounter during operation rather than simply maximize visual diversity.

Generalization across farms remains a major challenge. Soil color, crop variety, planting density, cultivation method, camera installation, and local weather can produce significant domain shifts. Models that perform well on the original training field may lose accuracy at a new site. Validation should therefore include geographically and temporally separated data rather than relying only on random image splits collected from the same environment.

Confidence estimation is important because agricultural robots convert AI predictions into physical decisions. A low-confidence fruit detection should not automatically trigger a harvesting attempt, and uncertain weed classification should not necessarily activate a herbicide nozzle. Perception software should expose confidence information to downstream planning so that uncertain observations can be ignored, re-observed, verified using another sensor, or escalated for human review.

Temporal information can improve reliability beyond independent frame-by-frame inference. Consecutive observations of the same crop can be associated through tracking and robot motion. Stable detections across multiple frames provide stronger evidence than isolated predictions, while inconsistent detections can be rejected or reconsidered. Temporal fusion also supports growth monitoring by connecting observations collected during different field visits.

Georeferencing transforms perception results into agricultural information that remains useful after the robot has moved away. A detected plant, weed, disease symptom, or fruit estimate can be associated with GNSS-RTK coordinates, crop-row identifiers, or individual plant records. This creates spatial crop maps that can guide later spraying, harvesting, inspection, or sampling operations and connects perception with broader precision-agriculture workflows.

Real-time deployment introduces computational constraints. Agricultural robots may need to process several camera streams while simultaneously running localization, navigation, safety monitoring, and control. Vision models must therefore balance detection accuracy with inference latency, memory consumption, power demand, and accelerator availability. Model compression, reduced input resolution, optimized inference engines, and selective processing can help maintain real-time operation on edge computers.

Perception failures should be treated explicitly within the robot software architecture. Cameras can become dirty, lenses may be covered by water or dust, exposure can fail under rapidly changing illumination, and vegetation can completely occlude targets. The system should monitor image quality and model confidence, detect abnormal input conditions, and avoid presenting unreliable perception as valid information to planning or control modules.

Evaluation should reflect agricultural objectives rather than relying exclusively on generic computer-vision metrics. Precision, recall, detection accuracy, segmentation quality, and inference latency remain important, but field evaluation should also measure fruit-counting error, maturity classification accuracy, missed treatment targets, false spraying decisions, localization error of detected objects, and the effect of perception errors on complete robotic task success.

The resulting perception pipeline connects sensing, AI inference, spatial reasoning, and agricultural decision making. Images are captured and calibrated, models detect or segment biological targets, depth and localization place those targets in physical space, phenotyping algorithms estimate crop properties, and the resulting information is stored or transferred to planning modules. This structure provides the perception foundation for precision spraying and selective harvesting.

Crop detection and phenotyping ultimately transform agricultural robots from machines that merely move through fields into systems capable of interpreting the biological environment. Reliable AI vision allows each plant or fruit to become a measurable entity linked to position, condition, history, and potential action. When integrated with field navigation, manipulation, and farm data systems, this capability enables increasingly precise and autonomous crop management.

작물 감지(Crop Detection)와 표현형 분석(Phenotyping)은 자율 농업 기계가 식물의 위치뿐만 아니라 생물학적 상태까지 이해해야 하기 때문에 농업 로봇(Agricultural Robot)의 핵심 인지 기능이다. 카메라와 AI 비전(AI Vision)은 시각적 관측을 작물, 과일, 잎, 잡초, 성장 단계, 식물 건강 상태에 대한 구조화된 정보로 변환한다. 이러한 인지 계층(Perception Layer)은 정밀 살포(Precision Spraying), 선택적 수확(Selective Harvesting), 모니터링, 데이터 기반 농장 관리(Data-Driven Farm Management)를 지원한다.

작물 감지는 이동 로봇(Mobile Robot), 트랙터(Tractor), 매니퓰레이터(Manipulator), 온실 플랫폼(Greenhouse Platform), 고정형 모니터링 시스템에 장착된 카메라로부터 영상을 획득하는 과정에서 시작된다. RGB 카메라는 세부적인 색상과 질감 정보를 제공하며, 깊이 카메라(Depth Camera), 스테레오 비전(Stereo Vision), 다중분광(Multispectral) 또는 기타 센싱 방식은 기하학적·분광적 정보를 추가할 수 있다. 카메라 구성은 촬영 거리, 시야각(Field of View), 움직임, 조명, 작물 형상, 수행할 농업 작업을 고려해야 한다.

농업 영상(Agricultural Imagery)은 제어된 산업 환경에서 획득되는 영상보다 훨씬 큰 변동성을 가진다. 식물은 성장하면서 크기, 형태, 방향, 색상, 밀도가 지속적으로 변화한다. 잎은 서로 겹치고, 과일은 부분적으로 가려지며, 잡초는 작물과 유사하게 보이고, 토양의 외관은 수분 상태에 따라 변한다. 햇빛은 그림자, 눈부심, 큰 노출 변화를 발생시킨다. 따라서 AI 비전은 상당한 클래스 내 변동성(Intra-Class Variation)과 환경적 불확실성(Environmental Uncertainty) 속에서도 생물학적 대상을 인식해야 한다.

객체 감지 모델(Object Detection Model)은 작물, 과일, 꽃, 잡초, 질병 증상 또는 기타 농업 대상을 식별하고 해당 위치를 바운딩 박스(Bounding Box)로 반환할 수 있다. 이러한 감지 결과는 이동 로봇이 장면을 이해하기 위한 첫 번째 수준의 유용한 정보를 제공한다. 수확 시스템은 수확 후보 과일을 식별할 수 있으며, 정밀 살포 로봇은 처리 대상을 주변 식생과 구분하고 감지된 객체를 로봇 좌표계(Robot Coordinate System)의 위치 정보와 연결할 수 있다.

바운딩 박스만으로 충분하지 않은 경우 영상 분할(Image Segmentation)을 사용하여 더욱 정밀한 공간 정보를 얻을 수 있다. 의미론적 분할(Semantic Segmentation)은 영상의 픽셀을 작물, 잡초, 토양, 과일, 배경 등의 범주로 분류하며, 인스턴스 분할(Instance Segmentation)은 동일한 클래스에 속하는 개별 객체를 서로 구분한다. 픽셀 수준 정보(Pixel-Level Information)는 식물 경계, 식생 피복률, 과일 형태, 잎 면적, 조작 또는 선택적 처리를 위한 정확한 목표 위치를 추정하는 데 유용하다.

감지 결과는 종종 2차원 영상 좌표에서 3차원 물리 좌표(Three-Dimensional Physical Coordinate)로 변환되어야 한다. 깊이 카메라, 스테레오 비전, 라이다(LiDAR), 기하학적 재구성(Geometric Reconstruction)을 이용하여 대상까지의 거리와 로봇에 대한 상대 위치를 추정할 수 있다. 이후 카메라 보정(Camera Calibration)과 좌표 변환(Coordinate Transformation)을 통해 감지된 작물을 차량, 매니퓰레이터 또는 농업 작업 장치와 연결한다. 이러한 변환은 인지 결과가 직접 물리적 작업을 실행해야 하는 경우 필수적이다.

표현형 분석(Phenotyping)은 농업 비전을 단순한 객체 인식 이상의 영역으로 확장한다. 식물 표현형 분석(Plant Phenotyping)은 식물의 구조, 성장, 발달, 상태와 관련된 관측 가능한 특성을 측정한다. 로봇 표현형 분석 시스템(Robotic Phenotyping System)은 식물 높이, 수관 크기(Canopy Size), 잎 면적, 과일 수, 성장률, 개화 상태, 성숙도 등을 추정할 수 있다. 반복적인 측정을 수행하면 로봇의 시각적 관측을 작물 성장 과정에 대한 종단 기록(Longitudinal Record)으로 변환할 수 있다.

과일 계수(Fruit Counting)는 개별 감지 결과를 통합하여 작물 착과량(Crop Load)과 잠재적 수확량을 추정할 수 있기 때문에 대표적인 표현형 분석 작업이다. 그러나 로봇이 농경지를 이동하면서 반복적으로 관측하면 동일한 과일을 여러 번 계산할 위험이 있다. 따라서 추적(Tracking), 위치 추정(Localization), 공간적 연관(Spatial Association)이 중요하다. 실용적인 농업 비전 시스템은 무엇이 감지되었는지뿐만 아니라 해당 관측이 새로운 물리적 객체를 의미하는지도 판단해야 한다.

성숙도 추정(Maturity Estimation)은 한 단계 더 높은 의미론적 해석(Semantic Interpretation)을 요구한다. 색상, 질감, 형태, 크기와 필요한 경우 분광 특성을 이용하여 과일이 미성숙 상태인지, 수확 가능한 상태인지, 과숙 상태인지 또는 손상되었는지를 추정할 수 있다. 출력은 이산적인 범주(Discrete Category) 또는 연속적인 성숙도 점수(Continuous Maturity Score)로 표현할 수 있다. 수확 로봇에서는 적절한 대상만 조작 대상으로 선택해야 하므로 성숙도 추정 결과가 작업 계획(Task Planning)에 직접적인 영향을 준다.

식물 건강 모니터링(Plant Health Monitoring)은 AI 비전을 이용하여 스트레스, 영양 결핍, 해충 피해 또는 질병과 관련된 시각적 증상을 식별할 수 있다. 이러한 증상은 초기에는 잎이나 수관의 매우 작은 영역에만 나타날 수 있으므로 영상 해상도와 관측 기하(Viewing Geometry)가 중요하다. 또한 불필요한 농업 처리를 방지하기 위해 실제 생물학적 증상과 그림자, 먼지, 물, 물리적 손상, 정상적인 색상 변화를 구분해야 한다.

데이터셋 품질(Dataset Quality)은 현장 성능을 결정하는 가장 중요한 요소 중 하나이다. 학습 영상은 서로 다른 농장, 작물 품종, 성장 단계, 계절, 조명 조건, 카메라 시점, 기상 조건, 가림 정도를 포함해야 한다. 깨끗하고 노출이 적절한 영상만을 중심으로 학습된 모델은 강한 햇빛, 비가 내린 이후의 환경, 밀집된 식생에서 성능이 크게 저하될 수 있다. 따라서 데이터셋 다양성(Dataset Diversity)은 시스템 강건성(System Robustness)의 일부로 간주해야 한다.

어노테이션 전략(Annotation Strategy)은 목표 작업에 따라 달라진다. 객체 감지와 계수에는 바운딩 박스로 충분할 수 있지만, 분할 마스크(Segmentation Mask)는 세부적인 식물 형상 정보를 제공한다. 키포인트(Keypoint)는 줄기, 과일 부착 지점, 꽃 또는 구조적 랜드마크를 표현할 수 있으며, 연속형 레이블(Continuous Label)은 크기나 성숙도를 나타낼 수 있다. 어노테이션 품질은 모델 동작에 직접적인 영향을 미치므로 모호한 농업 범주에는 일관된 정의와 품질 관리 절차가 필요하다.

데이터 증강(Data Augmentation)은 밝기, 대비, 크기, 방향, 영상 영역, 블러(Blur) 또는 기타 영상 속성을 변경하여 학습 데이터의 실질적인 다양성을 높일 수 있다. 그러나 농업 분야의 데이터 증강은 물리적으로 의미 있는 범위에서 수행되어야 한다. 비현실적인 변환은 실제 농경지 조건을 나타내지 않는 샘플을 생성할 수 있다. 목표는 단순히 시각적 다양성을 극대화하는 것이 아니라 실제 운영 과정에서 발생할 수 있는 현실적인 변화에 모델을 노출시키는 것이다.

농장 간 일반화(Generalization Across Farms)는 여전히 중요한 과제이다. 토양 색상, 작물 품종, 식재 밀도, 재배 방식, 카메라 설치 조건, 지역 기상 환경은 상당한 도메인 변화(Domain Shift)를 발생시킬 수 있다. 원래 학습 농경지에서 높은 성능을 보이는 모델도 새로운 현장에서는 정확도가 감소할 수 있다. 따라서 검증(Validation)은 동일한 환경에서 수집된 영상의 무작위 분할에만 의존하지 않고 지리적·시간적으로 분리된 데이터를 포함해야 한다.

농업 로봇은 AI 예측 결과를 물리적 의사결정으로 변환하기 때문에 신뢰도 추정(Confidence Estimation)이 중요하다. 신뢰도가 낮은 과일 감지가 자동으로 수확 시도를 발생시켜서는 안 되며, 불확실한 잡초 분류가 반드시 제초제 노즐을 작동시켜서도 안 된다. 인지 소프트웨어는 신뢰도 정보를 후속 계획 시스템에 제공하여 불확실한 관측을 무시하거나, 다시 관측하거나, 다른 센서로 검증하거나, 인간 검토(Human Review)를 요청할 수 있도록 해야 한다.

시간적 정보(Temporal Information)를 사용하면 각각의 프레임을 독립적으로 추론하는 것보다 신뢰성을 향상시킬 수 있다. 동일한 작물에 대한 연속 관측은 추적과 로봇 움직임 정보를 이용하여 서로 연결할 수 있다. 여러 프레임에서 안정적으로 유지되는 감지는 단일 프레임의 독립적인 예측보다 강한 근거를 제공하며, 일관되지 않은 감지는 제거하거나 다시 평가할 수 있다. 시간적 융합(Temporal Fusion)은 서로 다른 농경지 방문 시점에서 획득한 관측을 연결하여 성장 모니터링에도 활용할 수 있다.

지리참조(Georeferencing)는 인지 결과를 로봇이 해당 위치를 떠난 이후에도 활용할 수 있는 농업 정보로 변환한다. 감지된 식물, 잡초, 질병 증상 또는 과일 추정 결과를 GNSS-RTK 좌표, 작물 열 식별자(Crop-Row Identifier), 개별 식물 기록과 연결할 수 있다. 이를 통해 이후의 살포, 수확, 검사, 샘플링 작업을 안내할 수 있는 공간 작물 지도(Spatial Crop Map)를 생성하고 인지 기능을 더 광범위한 정밀 농업(Precision Agriculture) 작업 흐름과 연결할 수 있다.

실시간 배포(Real-Time Deployment)는 연산 자원의 제약을 발생시킨다. 농업 로봇은 위치 추정, 주행, 안전 모니터링, 제어를 동시에 실행하면서 여러 카메라 스트림을 처리해야 할 수 있다. 따라서 비전 모델(Vision Model)은 감지 정확도와 추론 지연시간(Inference Latency), 메모리 사용량, 전력 소비, 가속기 가용성 사이의 균형을 유지해야 한다. 모델 압축(Model Compression), 입력 해상도 감소, 최적화된 추론 엔진(Inference Engine), 선택적 영상 처리를 통해 엣지 컴퓨터(Edge Computer)에서 실시간 동작을 유지할 수 있다.

인지 실패(Perception Failure)는 로봇 소프트웨어 아키텍처에서 명시적으로 처리해야 한다. 카메라가 오염되거나 렌즈에 물 또는 먼지가 묻을 수 있고, 급격하게 변화하는 조명 환경에서 노출 제어가 실패할 수 있으며, 식생이 대상을 완전히 가릴 수도 있다. 시스템은 영상 품질과 모델 신뢰도를 감시하고 비정상적인 입력 조건을 감지하여 신뢰할 수 없는 인지 결과가 유효한 정보인 것처럼 계획 또는 제어 모듈에 전달되지 않도록 해야 한다.

평가는 일반적인 컴퓨터 비전(Computer Vision) 지표에만 의존하지 않고 실제 농업 목적을 반영해야 한다. 정밀도(Precision), 재현율(Recall), 감지 정확도, 분할 품질, 추론 지연시간도 중요하지만 현장 평가에서는 과일 계수 오차, 성숙도 분류 정확도, 누락된 처리 대상, 잘못된 살포 결정, 감지 객체의 위치 추정 오차, 인지 오류가 전체 로봇 작업 성공률에 미치는 영향까지 측정해야 한다.

결과적으로 인지 파이프라인(Perception Pipeline)은 센싱(Sensing), AI 추론(AI Inference), 공간 추론(Spatial Reasoning), 농업 의사결정(Agricultural Decision Making)을 연결한다. 영상을 획득하고 보정한 후 모델이 생물학적 대상을 감지하거나 분할하며, 깊이 정보와 위치 추정을 이용하여 대상을 물리적 공간에 배치한다. 이후 표현형 분석 알고리즘이 작물 특성을 추정하고, 생성된 정보를 저장하거나 계획 모듈로 전달한다. 이러한 구조는 정밀 살포와 선택적 수확을 위한 핵심 인지 기반을 제공한다.

작물 감지와 표현형 분석은 궁극적으로 농업 로봇을 단순히 농경지를 이동하는 기계에서 생물학적 환경을 해석할 수 있는 시스템으로 변화시킨다. 신뢰성 높은 AI 비전은 각각의 식물이나 과일을 위치, 상태, 이력, 잠재적 행동과 연결된 측정 가능한 객체로 만든다. 이러한 기능이 농경지 주행(Field Navigation), 조작(Manipulation), 농장 데이터 시스템(Farm Data System)과 통합되면 더욱 정밀하고 자율적인 작물 관리(Autonomous Crop Management)가 가능해진다.

##  

## 08.04. Precision Spraying Variable Rate Application [w/Code]

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

Precision spraying transforms crop protection from uniform field-wide application into targeted treatment based on the condition of individual plants or localized field regions. An autonomous agricultural robot combines navigation, crop perception, treatment planning, and electronically controlled spraying so that chemicals are delivered where they are required. Variable-rate application further adjusts the amount applied according to target characteristics and agronomic requirements.

Conventional spraying typically applies a predefined rate across a large area even when weeds, pests, disease symptoms, or crop conditions are spatially uneven. This can increase chemical consumption and expose non-target plants and surrounding areas unnecessarily. Precision spraying attempts to reduce this inefficiency by connecting sensor observations with individual nozzle actions and adapting treatment continuously as the robot moves through the field.

The software pipeline begins with accurate localization and perception. GNSS-RTK, inertial sensing, odometry, and row-following information establish the robot pose, while cameras or other agricultural sensors observe vegetation ahead of the spraying mechanism. AI vision detects crops, weeds, leaves, disease symptoms, or other treatment targets and estimates their position relative to the robot and spraying implement.

Target classification is critical because detection alone does not determine whether spraying is appropriate. A perception model may distinguish crop from weed, identify a specific weed category, recognize visible disease symptoms, or estimate vegetation density. Each detected target is associated with a confidence value and spatial position. The decision layer then determines whether the observation satisfies the conditions required to authorize treatment.

The system must transform image-space detections into physical spraying coordinates. Camera calibration defines the geometric relationship between image pixels and sensor coordinates, while extrinsic calibration relates the camera to the robot and nozzle assembly. Depth estimation, ground-plane geometry, stereo vision, or additional range sensors can provide target distance. Accurate transformation is essential because a small spatial error can cause the spray to miss the intended plant.

Vehicle motion introduces a timing problem between perception and actuation. The camera normally observes a target before the corresponding nozzle reaches its location. Software must estimate the time required for the robot to travel from the sensing position to the spray position while accounting for current velocity, sensor-to-nozzle offset, processing latency, valve response, and fluid transport delay. The nozzle command is then scheduled for the predicted target arrival time.

This perception-to-actuation latency should be treated as a complete system quantity rather than only an AI inference time. Image capture, preprocessing, neural-network inference, target localization, decision making, communication, valve activation, and fluid dynamics all contribute to the final timing error. Timestamp synchronization across sensing, computation, navigation, and actuator interfaces is therefore essential for high-accuracy spraying at practical vehicle speeds.

A multi-nozzle boom can divide the treatment width into independently controlled spatial zones. After a target is localized, software selects the nozzle or group of nozzles whose spray footprint best intersects the target region. As the robot moves, multiple target events may be queued simultaneously. The controller must schedule these events while preventing duplicated applications, missed targets, and conflicting commands between neighboring spray channels.

Variable-rate application extends binary spray or no-spray control by determining how much material should be delivered. Application rate can depend on vegetation density, weed size, disease severity, crop growth stage, prescribed field maps, or other agronomic variables. The desired dose is translated into actuator parameters such as valve duty cycle, opening duration, flow rate, pressure setting, or vehicle-speed-dependent command values.

Vehicle speed must be included in rate control because the amount deposited per unit area changes when the robot accelerates or decelerates. A constant nozzle flow applied at different speeds produces different spatial application rates. The control system therefore combines target dose, measured velocity, nozzle characteristics, and spray geometry to maintain the requested treatment level while the mobile platform changes its motion.

Prescription maps provide another source of variable-rate commands. A field can be divided into georeferenced management zones containing recommended treatment levels derived from previous surveys, crop observations, soil measurements, or agronomic analysis. GNSS-RTK localization determines the robot\'s current position within this map, and the application controller combines the prescribed rate with real-time perception when both information sources are available.

Real-time vision and prescription maps serve complementary purposes. A prescription map represents knowledge acquired before the current operation, while onboard perception describes conditions observed at execution time. A robust system can use the map to define expected treatment requirements and local sensing to confirm or modify them. This allows the robot to respond to changes that occurred after the original field survey.

Safety constraints must remain independent of the treatment optimization logic. Spraying should be inhibited when the robot enters prohibited zones, loses reliable localization, detects people near the treatment area, exceeds configured operating conditions, or experiences actuator and sensor faults. The software should default toward a safe state when the validity of the spraying decision cannot be established with sufficient confidence.

Environmental conditions can also affect treatment quality. Wind may cause spray drift, while temperature and humidity can influence evaporation and deposition. Although the available sensor configuration varies between agricultural platforms, environmental measurements can be incorporated into treatment authorization and rate adjustment. When operating conditions exceed acceptable thresholds, the robot can reduce application, pause spraying, or postpone the mission.

Actuator feedback improves reliability because issuing a valve command does not guarantee that chemical was actually delivered. Flow meters, pressure sensors, valve-state feedback, tank-level sensors, or pump diagnostics can confirm whether the spraying subsystem responded correctly. Comparing commanded and measured behavior allows software to detect blocked nozzles, empty tanks, pressure abnormalities, valve failures, or unexpected flow conditions.

Calibration is therefore a major operational requirement. Each nozzle has a physical spray pattern, flow characteristic, response delay, and possible manufacturing variation. Camera-to-nozzle geometry must also remain accurate after maintenance or mechanical adjustment. Calibration procedures should measure spatial alignment, timing offset, flow behavior, and actuator response so that software parameters represent the actual physical system rather than nominal specifications.

Precision spraying generates valuable operational data. Each treatment event can contain timestamp, robot pose, target category, perception confidence, selected nozzle, requested dose, measured flow, and execution result. When associated with GNSS coordinates, these records form a treatment map showing where material was applied. Such maps support traceability, agronomic analysis, chemical inventory management, and comparison with later crop outcomes.

Logging also provides the basis for software improvement. Engineers can replay situations in which a target was missed, a crop was incorrectly treated, or a nozzle activated at the wrong position. Sensor frames, localization states, inference outputs, vehicle velocity, actuator commands, and feedback should be synchronized so that failures can be traced across the complete perception-to-action pipeline rather than attributed only to the AI model.

Evaluation must therefore include both perception and application performance. Detection precision and recall are important, but field metrics should also measure target treatment rate, false application rate, spatial spray error, dosage error, chemical reduction, crop exposure, nozzle response reliability, and treatment coverage. End-to-end evaluation reveals whether improvements in AI accuracy actually produce better physical agricultural outcomes.

Edge computing is particularly important because treatment decisions often have strict latency requirements and should not depend on continuous remote connectivity. Crop detection, target localization, nozzle scheduling, rate control, and safety interlocks can execute locally on the agricultural robot. Cloud or on-premise systems can support model training, historical analysis, fleet monitoring, prescription generation, and long-term optimization without becoming part of the immediate control loop.

Precision spraying consequently represents a direct Physical AI interaction loop. The robot observes biological and environmental conditions, AI interprets whether treatment is required, spatial reasoning determines where the target will intersect the implement, and control software determines when and how much material to apply. Actuator feedback then verifies the physical result and returns information to the software system.

When integrated with RTK field navigation and crop-detection capabilities, variable-rate spraying demonstrates how agricultural autonomy progresses from perception to controlled intervention. The value of the system is determined not simply by whether weeds or crops can be recognized, but by whether each observation can be converted into a timely, spatially accurate, safe, and measurable physical action while the robot continuously moves through a changing field environment.

정밀 살포(Precision Spraying)는 작물 보호(Crop Protection) 방식을 농경지 전체에 균일하게 살포하는 방식에서 개별 식물이나 국소적인 농경지 영역의 상태를 기반으로 하는 표적 처리(Targeted Treatment) 방식으로 전환한다. 자율 농업 로봇(Autonomous Agricultural Robot)은 주행, 작물 인지, 처리 계획, 전자 제어 살포 기능을 결합하여 필요한 위치에만 약제를 공급한다. 가변 살포(Variable-Rate Application)는 대상의 특성과 농업적 요구조건에 따라 살포량까지 조절한다.

기존 살포(Conventional Spraying)는 잡초, 해충, 질병 증상 또는 작물 상태가 공간적으로 균일하지 않은 경우에도 넓은 영역에 사전에 정의된 일정한 살포량을 적용하는 경우가 많다. 이는 약제 사용량을 증가시키고 비표적 식물과 주변 환경을 불필요하게 약제에 노출시킬 수 있다. 정밀 살포는 센서 관측 결과를 개별 노즐 동작과 연결하고 로봇이 농경지를 이동하는 동안 처리 방법을 지속적으로 조정하여 이러한 비효율성을 줄이는 것을 목표로 한다.

소프트웨어 파이프라인(Software Pipeline)은 정확한 위치 추정(Localization)과 인지(Perception)에서 시작된다. GNSS-RTK, 관성 센싱(Inertial Sensing), 오도메트리(Odometry), 작물 열 추종(Row Following) 정보를 이용하여 로봇 자세(Robot Pose)를 결정하고, 카메라 또는 기타 농업 센서가 살포 장치 전방의 식생을 관측한다. AI 비전(AI Vision)은 작물, 잡초, 잎, 질병 증상 또는 기타 처리 대상을 감지하고 로봇과 살포 작업 장치에 대한 상대 위치를 추정한다.

표적 분류(Target Classification)는 감지만으로는 살포가 적절한지 판단할 수 없기 때문에 매우 중요하다. 인지 모델(Perception Model)은 작물과 잡초를 구분하거나 특정 잡초 종류를 식별하고, 눈에 보이는 질병 증상을 인식하거나 식생 밀도를 추정할 수 있다. 각각의 감지 대상에는 신뢰도 값(Confidence Value)과 공간 위치가 연결된다. 이후 의사결정 계층(Decision Layer)은 해당 관측 결과가 처리를 허용하기 위한 조건을 충족하는지 판단한다.

시스템은 영상 공간(Image Space)의 감지 결과를 실제 물리적 살포 좌표(Physical Spraying Coordinate)로 변환해야 한다. 카메라 보정(Camera Calibration)은 영상 픽셀과 센서 좌표 사이의 기하학적 관계를 정의하고, 외부 보정(Extrinsic Calibration)은 카메라와 로봇 및 노즐 어셈블리(Nozzle Assembly) 사이의 관계를 정의한다. 깊이 추정(Depth Estimation), 지면 평면 기하(Ground-Plane Geometry), 스테레오 비전(Stereo Vision) 또는 추가 거리 센서를 이용하여 대상까지의 거리를 구할 수 있다. 작은 공간 오차도 의도한 식물을 벗어난 살포로 이어질 수 있으므로 정확한 좌표 변환이 필수적이다.

차량 움직임은 인지와 작동 사이에 시간 동기화 문제를 발생시킨다. 일반적으로 카메라는 해당 노즐이 대상 위치에 도달하기 전에 표적을 관측한다. 소프트웨어는 현재 차량 속도, 센서와 노즐 사이의 오프셋, 처리 지연시간(Processing Latency), 밸브 응답시간, 유체 전달 지연(Fluid Transport Delay)을 고려하여 로봇이 센싱 위치에서 살포 위치까지 이동하는 데 필요한 시간을 추정해야 한다. 이후 예측된 표적 도달 시간에 맞추어 노즐 명령을 예약한다.

이러한 인지-작동 지연시간(Perception-to-Actuation Latency)은 단순히 AI 추론 시간만이 아니라 전체 시스템의 지연시간으로 다루어야 한다. 영상 획득, 전처리, 신경망 추론(Neural-Network Inference), 표적 위치 추정, 의사결정, 통신, 밸브 작동, 유체 동역학(Fluid Dynamics)이 모두 최종 시간 오차에 영향을 준다. 따라서 고속으로 이동하는 실제 농업 차량에서 높은 살포 정확도를 확보하려면 센싱, 연산, 주행, 액추에이터 인터페이스 전체에 걸친 타임스탬프 동기화(Timestamp Synchronization)가 필수적이다.

다중 노즐 붐(Multi-Nozzle Boom)은 처리 폭을 독립적으로 제어할 수 있는 여러 공간 영역으로 나눌 수 있다. 대상의 위치가 결정되면 소프트웨어는 살포 영역(Spray Footprint)이 표적 영역과 가장 적절하게 교차하는 노즐 또는 노즐 그룹을 선택한다. 로봇이 이동하면서 여러 개의 표적 이벤트가 동시에 대기열(Queue)에 등록될 수 있다. 제어기는 중복 살포, 표적 누락, 인접 살포 채널 간의 명령 충돌을 방지하면서 이러한 이벤트를 스케줄링해야 한다.

가변 살포(Variable-Rate Application)는 단순한 살포 또는 비살포(Spray/No-Spray) 제어를 넘어 실제 공급해야 할 약제의 양을 결정한다. 살포량은 식생 밀도, 잡초 크기, 질병 심각도, 작물 성장 단계, 처방 지도(Prescription Map) 또는 기타 농업 변수에 따라 결정될 수 있다. 목표 투여량(Target Dose)은 밸브 듀티 사이클(Valve Duty Cycle), 개방 시간, 유량(Flow Rate), 압력 설정 또는 차량 속도에 따른 명령값과 같은 액추에이터 매개변수로 변환된다.

차량 속도는 로봇이 가속하거나 감속할 때 단위 면적당 살포량이 달라지기 때문에 살포량 제어(Rate Control)에 포함되어야 한다. 서로 다른 속도에서 일정한 노즐 유량을 유지하면 공간적인 살포량이 달라진다. 따라서 제어 시스템은 이동 플랫폼의 속도가 변화하는 동안에도 요구된 처리 수준을 유지하기 위해 목표 투여량, 측정 속도, 노즐 특성, 살포 기하(Spray Geometry)를 함께 고려해야 한다.

처방 지도(Prescription Map)는 가변 살포 명령을 제공하는 또 다른 정보원이다. 농경지는 이전 조사, 작물 관측, 토양 측정 또는 농업 분석을 통해 산출된 권장 처리 수준을 포함하는 지리참조 관리 구역(Georeferenced Management Zone)으로 나눌 수 있다. GNSS-RTK 위치 추정을 이용하여 지도 내 로봇의 현재 위치를 결정하고, 두 가지 정보가 모두 사용 가능한 경우 살포 제어기는 처방된 살포량과 실시간 인지(Real-Time Perception) 결과를 결합한다.

실시간 비전(Real-Time Vision)과 처방 지도는 상호 보완적인 역할을 수행한다. 처방 지도는 현재 작업 이전에 획득한 정보를 나타내는 반면, 온보드 인지(Onboard Perception)는 실제 작업 시점에 관측된 상태를 나타낸다. 강건한 시스템은 지도를 이용하여 예상 처리 요구조건을 정의하고 지역 센싱(Local Sensing)을 이용하여 이를 확인하거나 수정할 수 있다. 이를 통해 로봇은 최초 농경지 조사 이후 발생한 변화에도 대응할 수 있다.

안전 제약조건(Safety Constraint)은 처리 최적화 로직과 독립적으로 유지되어야 한다. 로봇이 금지 구역에 진입하거나 신뢰할 수 있는 위치 추정 정보를 잃거나 처리 영역 주변에서 사람을 감지하거나 설정된 운영 조건을 초과하거나 액추에이터 또는 센서 고장이 발생하면 살포가 차단되어야 한다. 살포 결정의 유효성을 충분한 신뢰도로 확인할 수 없는 경우 소프트웨어는 기본적으로 안전 상태(Safe State)로 전환되어야 한다.

환경 조건(Environmental Condition) 역시 처리 품질에 영향을 줄 수 있다. 바람은 약제 비산(Spray Drift)을 발생시킬 수 있으며 온도와 습도는 증발과 부착에 영향을 줄 수 있다. 사용 가능한 센서 구성은 농업 플랫폼마다 다르지만 환경 측정값을 처리 허가와 살포량 조정 과정에 포함할 수 있다. 운영 조건이 허용 가능한 임계값을 초과하면 로봇은 살포량을 줄이거나 살포를 일시 중지하거나 임무 자체를 연기할 수 있다.

액추에이터 피드백(Actuator Feedback)은 밸브 명령을 전달했다고 해서 실제로 약제가 공급되었다고 보장할 수 없기 때문에 신뢰성을 향상시킨다. 유량계(Flow Meter), 압력 센서(Pressure Sensor), 밸브 상태 피드백, 탱크 수위 센서(Tank-Level Sensor), 펌프 진단 정보를 이용하여 살포 하위 시스템이 명령에 올바르게 응답했는지 확인할 수 있다. 명령된 동작과 실제 측정된 동작을 비교하면 노즐 막힘, 탱크 고갈, 압력 이상, 밸브 고장, 비정상적인 유량 상태를 감지할 수 있다.

따라서 보정(Calibration)은 중요한 운영 요구사항이다. 각각의 노즐은 고유한 물리적 살포 패턴, 유량 특성, 응답 지연시간과 제조 편차를 가질 수 있다. 카메라와 노즐 사이의 기하학적 관계 역시 유지보수나 기계적 조정 이후에도 정확하게 유지되어야 한다. 보정 절차에서는 공간 정렬(Spatial Alignment), 시간 오프셋(Timing Offset), 유량 특성, 액추에이터 응답을 측정하여 소프트웨어 매개변수가 명목상의 사양이 아니라 실제 물리 시스템을 반영하도록 해야 한다.

정밀 살포는 가치 있는 운영 데이터(Operational Data)를 생성한다. 각각의 처리 이벤트에는 타임스탬프, 로봇 자세, 표적 범주, 인지 신뢰도, 선택된 노즐, 요구 투여량, 측정 유량, 실행 결과를 포함할 수 있다. 이러한 정보를 GNSS 좌표와 연결하면 약제가 어디에 살포되었는지를 보여주는 처리 지도(Treatment Map)를 생성할 수 있다. 이러한 지도는 추적성(Traceability), 농업 분석, 약제 재고 관리, 이후 작물 결과와의 비교를 지원한다.

운영 로그(Logging)는 소프트웨어 개선의 기반도 제공한다. 엔지니어는 표적을 놓친 상황, 작물을 잘못 처리한 상황 또는 잘못된 위치에서 노즐이 작동한 상황을 재현할 수 있다. 센서 프레임, 위치 추정 상태, 추론 출력, 차량 속도, 액추에이터 명령, 피드백 정보를 동기화하여 기록해야 하며, 이를 통해 고장의 원인을 AI 모델에만 한정하지 않고 전체 인지-행동 파이프라인(Perception-to-Action Pipeline)에 걸쳐 추적할 수 있다.

따라서 평가는 인지 성능과 실제 살포 성능을 모두 포함해야 한다. 감지 정밀도(Precision)와 재현율(Recall)도 중요하지만 현장 지표에는 표적 처리율(Target Treatment Rate), 오살포율(False Application Rate), 공간 살포 오차, 투여량 오차, 약제 절감량, 작물 노출량, 노즐 응답 신뢰성, 처리 커버리지(Treatment Coverage)가 포함되어야 한다. 엔드투엔드 평가(End-to-End Evaluation)를 수행해야 AI 정확도 향상이 실제 물리적 농업 결과의 개선으로 이어지는지를 확인할 수 있다.

엣지 컴퓨팅(Edge Computing)은 처리 결정이 엄격한 지연시간 요구조건을 가지며 지속적인 원격 연결에 의존해서는 안 되기 때문에 특히 중요하다. 작물 감지, 표적 위치 추정, 노즐 스케줄링, 살포량 제어, 안전 인터록(Safety Interlock)은 농업 로봇에서 로컬로 실행할 수 있다. 클라우드(Cloud) 또는 온프레미스(On-Premise) 시스템은 모델 학습, 이력 분석, 플릿 모니터링, 처방 생성, 장기 최적화를 지원할 수 있지만 즉각적인 제어 루프(Immediate Control Loop)의 일부가 될 필요는 없다.

따라서 정밀 살포는 직접적인 피지컬 AI 상호작용 루프(Physical AI Interaction Loop)를 형성한다. 로봇은 생물학적·환경적 상태를 관측하고, AI는 처리가 필요한지를 해석하며, 공간 추론(Spatial Reasoning)은 표적이 작업 장치와 어디에서 교차할지를 결정하고, 제어 소프트웨어는 언제 얼마만큼의 약제를 적용할지를 결정한다. 이후 액추에이터 피드백은 물리적 실행 결과를 검증하고 그 정보를 다시 소프트웨어 시스템으로 반환한다.

가변 살포는 RTK 농경지 주행(RTK Field Navigation) 및 작물 감지(Crop Detection) 기능과 통합될 때 농업 자율화가 인지에서 제어된 물리적 개입(Controlled Physical Intervention)으로 발전하는 방식을 보여준다. 시스템의 가치는 단순히 잡초나 작물을 인식할 수 있는지에 의해 결정되는 것이 아니라, 로봇이 지속적으로 변화하는 농경지를 이동하는 동안 각각의 관측 결과를 적시에 공간적으로 정확하고 안전하며 측정 가능한 물리적 행동으로 변환할 수 있는지에 의해 결정된다.

##  

## 08.05. Selective Harvesting Robot SW Strawberry [w/Code]

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

Selective harvesting is one of the most demanding agricultural robotics applications because the robot must identify harvestable produce, approach it through complex vegetation, remove it without damage, and verify successful collection. Strawberry harvesting is a representative case because fruits are fragile, partially occluded by leaves, distributed irregularly, and harvested according to maturity rather than simply by geometric position.

The harvesting software begins with visual perception of the crop environment. RGB, depth, or stereo cameras observe plants from positions that provide useful views of fruit and surrounding vegetation. AI vision detects individual strawberries and distinguishes them from leaves, stems, flowers, supports, soil, and background objects. Instance-level recognition is particularly important because each fruit becomes an independent candidate for manipulation.

Detection alone is insufficient because the robot should harvest only fruit that satisfies predefined quality requirements. A maturity estimation model can evaluate color, texture, size, shape, and other visible characteristics to classify strawberries as immature, harvestable, overripe, damaged, or uncertain. The task planner uses this information to prioritize suitable targets and avoid unnecessary manipulation of fruit that should remain on the plant.

Occlusion is a fundamental problem in strawberry perception. Leaves, stems, neighboring fruit, cultivation structures, and other vegetation can hide important portions of the target. A robot may therefore need to combine observations from multiple viewpoints rather than making a decision from a single image. Active perception can reposition the camera or manipulator to obtain a clearer view before committing to a harvesting action.

Once a strawberry is selected, the perception system must estimate its three-dimensional position relative to the harvesting mechanism. Depth sensing, stereo reconstruction, or multi-view geometry can provide target coordinates, while calibrated transformations connect the camera frame to the robot and manipulator frames. Position accuracy is critical because even a small error may cause the end effector to collide with the fruit or surrounding plant structure.

Harvest planning also requires information beyond the fruit center. The system may estimate fruit orientation, visible surface geometry, stem location, attachment direction, and accessible approach regions. These properties influence where the end effector should approach and how the fruit should be detached. Agricultural manipulation therefore converts semantic perception into task-specific geometric information suitable for motion planning.

The manipulator must move through a constrained workspace containing fragile and deformable obstacles. Conventional collision avoidance can model greenhouse structures and rigid equipment, but leaves and stems require more careful treatment because they can move when contacted. Motion planning should generate a feasible approach trajectory while minimizing unnecessary contact with the crop and maintaining appropriate orientation of the harvesting tool.

End-effector design and software control are tightly coupled. A strawberry may be harvested using gripping, cutting, suction, twisting, or a combination of mechanisms depending on the robot design. The controller must coordinate the manipulator pose with gripper closure, suction activation, cutter operation, or other tool commands. Timing and force must be controlled carefully because excessive contact can bruise or deform the fruit.

Force and tactile information can complement vision during the final stage of manipulation. Visual estimates become less reliable when the end effector approaches the target and blocks the camera view. Force sensing, motor current, vacuum pressure, tactile sensors, or gripper position can indicate whether contact occurred and whether the fruit was successfully secured. These signals help convert an open-loop visual approach into a closed-loop manipulation process.

Detachment is a separate manipulation phase because successfully contacting a strawberry does not guarantee successful harvesting. The robot must apply the appropriate cutting, pulling, twisting, or gripping action while limiting forces transmitted to the fruit and plant. Software should monitor the expected tool response and detect abnormal conditions such as failed cutting, fruit slippage, unexpected resistance, or incomplete separation.

After detachment, the robot must verify that the fruit has actually been harvested. Verification may use camera observations, gripper state, force measurements, suction pressure, or comparison of the scene before and after the action. Without verification, a failed attempt could be recorded as a successful harvest. Reliable autonomy therefore requires explicit confirmation of physical task completion rather than assuming success after issuing commands.

The harvested strawberry must then be transferred to a collection container without creating additional damage. Motion planning should consider fruit retention, manipulator acceleration, collision risk, and the location of the storage area. The release action should also be controlled to avoid excessive drop height or impact. Harvesting software consequently manages the complete cycle from target selection through collection rather than only the picking motion.

Task scheduling becomes important when many strawberries are visible simultaneously. The robot can prioritize targets according to maturity, accessibility, confidence, travel distance, expected harvesting time, or risk of failure. Selecting the nearest fruit is not always optimal if another target provides a safer approach or reduces manipulator motion. Efficient scheduling improves throughput while preserving harvest quality and reducing unnecessary arm movement.

Failure recovery is essential because agricultural manipulation operates in uncertain biological environments. A fruit may move during approach, become occluded, slip from the gripper, resist detachment, or prove inaccessible after the manipulator begins moving. The software should recognize these conditions and decide whether to retry from another viewpoint, modify the grasp, select another approach, postpone the target, or request operator assistance.

Repeated failed attempts should not continue indefinitely. Each target can maintain an execution state containing detection confidence, maturity estimate, attempted approaches, manipulation outcomes, and failure reasons. After a configured number of unsuccessful attempts, the robot can mark the fruit as temporarily unreachable and continue the mission. This prevents one difficult strawberry from significantly reducing the productivity of the entire harvesting operation.

Mobile harvesting platforms must coordinate manipulation with vehicle navigation. The vehicle first positions itself so that target plants fall within the manipulator workspace, then establishes a sufficiently stable pose before precision harvesting begins. After accessible targets are processed, the platform advances to the next working position. Navigation and manipulation therefore operate as coordinated phases of a larger agricultural task rather than independent subsystems.

Calibration strongly influences harvesting accuracy. Camera intrinsics, camera-to-manipulator transformations, tool-center-point position, depth alignment, and mechanical offsets must accurately represent the physical robot. Small calibration errors can accumulate across the perception and motion chain and become significant near the fruit. Periodic calibration checks are therefore necessary, particularly after camera, manipulator, or end-effector maintenance.

Operational data should record the complete harvesting process. Useful information includes target images, maturity estimates, three-dimensional positions, planned trajectories, execution times, gripper or tool states, force measurements, success results, and failure categories. Associating these records with plant or row locations allows engineers to evaluate both individual manipulation events and harvesting performance across the field.

Performance evaluation must extend beyond simple picking success rate. Important measures include detection recall, maturity classification accuracy, localization error, successful detachment rate, fruit damage rate, cycle time, intervention frequency, inaccessible-target rate, and harvested fruit per operating hour. Commercial performance depends on the interaction of these measures because high picking success has limited value if each cycle is excessively slow or damages produce.

Edge computing is well suited to selective harvesting because perception, motion planning, manipulation monitoring, and recovery decisions require low latency and must remain available without continuous network connectivity. Remote systems can support model training, fleet analytics, historical crop records, and software updates, while the immediate harvesting loop remains local to the robot for responsive and reliable physical interaction.

Strawberry harvesting therefore illustrates a complete Physical AI loop in which biological perception and physical manipulation are inseparable. The robot observes fruit, estimates maturity and accessibility, determines three-dimensional geometry, plans an approach, controls physical interaction, verifies detachment, and records the result. Each stage influences the next, and uncertainty must be managed throughout the complete task.

A mature selective harvesting system is consequently not defined by a single fruit detector or robotic arm algorithm. It emerges from the integration of crop perception, maturity estimation, three-dimensional localization, active perception, motion planning, compliant manipulation, tool control, verification, recovery, and mobile-platform coordination. This integrated software architecture enables fragile crops such as strawberries to be harvested autonomously with increasing consistency, quality, and operational efficiency.

선택적 수확(Selective Harvesting)은 로봇이 수확 가능한 농산물을 식별하고, 복잡한 식생 사이로 접근하여 손상 없이 분리한 후 성공적으로 수집되었는지까지 검증해야 하기 때문에 가장 까다로운 농업 로보틱스(Agricultural Robotics) 응용 분야 중 하나이다. 딸기 수확(Strawberry Harvesting)은 과일이 연약하고 잎에 부분적으로 가려지며 불규칙하게 분포하고 단순한 기하학적 위치가 아니라 성숙도(Maturity)에 따라 수확 여부가 결정된다는 점에서 대표적인 사례이다.

수확 소프트웨어(Harvesting Software)는 작물 환경에 대한 시각적 인지(Visual Perception)에서 시작된다. RGB 카메라, 깊이 카메라(Depth Camera), 스테레오 카메라(Stereo Camera)는 과일과 주변 식생을 효과적으로 관측할 수 있는 위치에서 식물을 촬영한다. AI 비전(AI Vision)은 개별 딸기를 감지하고 잎, 줄기, 꽃, 지지 구조물, 토양, 배경 객체와 구분한다. 각각의 과일이 독립적인 조작 후보가 되기 때문에 인스턴스 수준 인식(Instance-Level Recognition)이 특히 중요하다.

로봇은 사전에 정의된 품질 요구조건을 만족하는 과일만 수확해야 하므로 감지(Detection)만으로는 충분하지 않다. 성숙도 추정 모델(Maturity Estimation Model)은 색상, 질감, 크기, 형태 및 기타 시각적 특성을 평가하여 딸기를 미성숙(Immature), 수확 가능(Harvestable), 과숙(Overripe), 손상(Damaged), 불확실(Uncertain) 상태로 분류할 수 있다. 작업 계획기(Task Planner)는 이러한 정보를 이용하여 적절한 대상을 우선적으로 선택하고 아직 식물에 남겨두어야 할 과일에 대한 불필요한 조작을 방지한다.

가림(Occlusion)은 딸기 인지에서 근본적인 문제이다. 잎, 줄기, 인접한 과일, 재배 구조물 및 기타 식생이 대상의 중요한 부분을 가릴 수 있다. 따라서 로봇은 하나의 영상만으로 판단하기보다 여러 시점(Multiple Viewpoint)의 관측 정보를 결합해야 할 수 있다. 능동 인지(Active Perception)는 수확 동작을 실행하기 전에 카메라 또는 매니퓰레이터(Manipulator)의 위치를 변경하여 대상을 더 명확하게 관측할 수 있도록 한다.

딸기가 선택되면 인지 시스템(Perception System)은 수확 장치에 대한 딸기의 3차원 위치(Three-Dimensional Position)를 추정해야 한다. 깊이 센싱(Depth Sensing), 스테레오 재구성(Stereo Reconstruction), 다중 시점 기하(Multi-View Geometry)를 이용하여 대상 좌표를 계산할 수 있으며, 보정된 좌표 변환(Calibrated Transformation)을 통해 카메라 좌표계와 로봇 및 매니퓰레이터 좌표계를 연결한다. 작은 위치 오차도 엔드 이펙터(End Effector)가 과일이나 주변 식물 구조와 충돌하게 만들 수 있으므로 위치 정확도가 매우 중요하다.

수확 계획(Harvest Planning)에는 과일 중심 위치 이상의 정보가 필요하다. 시스템은 과일 방향, 관측 가능한 표면 형상, 줄기 위치, 부착 방향, 접근 가능한 영역 등을 추정할 수 있다. 이러한 특성은 엔드 이펙터가 어느 위치와 방향에서 접근해야 하는지, 그리고 과일을 어떤 방식으로 분리해야 하는지를 결정하는 데 영향을 준다. 따라서 농업 조작(Agricultural Manipulation)은 의미론적 인지(Semantic Perception)를 모션 계획(Motion Planning)에 사용할 수 있는 작업별 기하학 정보(Task-Specific Geometric Information)로 변환해야 한다.

매니퓰레이터는 연약하고 변형 가능한 장애물(Deformable Obstacle)이 존재하는 제한된 작업 공간을 통과해야 한다. 일반적인 충돌 회피(Collision Avoidance)는 온실 구조물이나 단단한 장비를 모델링할 수 있지만, 잎과 줄기는 접촉 시 움직일 수 있으므로 더욱 세심하게 처리해야 한다. 모션 계획은 작물과의 불필요한 접촉을 최소화하면서 수확 도구의 적절한 방향을 유지하는 실행 가능한 접근 궤적(Feasible Approach Trajectory)을 생성해야 한다.

엔드 이펙터 설계(End-Effector Design)와 소프트웨어 제어는 긴밀하게 결합되어 있다. 로봇 설계에 따라 딸기는 파지(Gripping), 절단(Cutting), 흡착(Suction), 비틀기(Twisting) 또는 여러 방식의 조합을 이용하여 수확할 수 있다. 제어기는 매니퓰레이터 자세와 그리퍼 폐쇄, 흡착 작동, 절단기 동작 또는 기타 도구 명령을 조정해야 한다. 과도한 접촉은 과일에 멍이나 변형을 발생시킬 수 있으므로 동작 시점과 힘을 세심하게 제어해야 한다.

힘 및 촉각 정보(Force and Tactile Information)는 조작의 최종 단계에서 비전 정보를 보완할 수 있다. 엔드 이펙터가 대상에 접근하여 카메라 시야를 가리기 시작하면 시각적 추정의 신뢰성이 낮아질 수 있다. 힘 센싱(Force Sensing), 모터 전류(Motor Current), 진공 압력(Vacuum Pressure), 촉각 센서(Tactile Sensor), 그리퍼 위치를 이용하여 접촉 여부와 과일이 성공적으로 확보되었는지를 판단할 수 있다. 이러한 신호는 개방 루프 시각 접근(Open-Loop Visual Approach)을 폐루프 조작(Closed-Loop Manipulation) 과정으로 전환하는 데 도움을 준다.

분리(Detachment)는 딸기에 성공적으로 접촉했다고 해서 수확이 완료되는 것은 아니므로 별도의 조작 단계로 다루어야 한다. 로봇은 과일과 식물에 전달되는 힘을 제한하면서 적절한 절단, 당김, 비틀기 또는 파지 동작을 수행해야 한다. 소프트웨어는 예상되는 도구 응답을 감시하고 절단 실패, 과일 미끄러짐, 예상하지 못한 저항 또는 불완전한 분리와 같은 비정상 상태를 감지해야 한다.

분리 이후에는 실제로 과일이 수확되었는지를 로봇이 검증해야 한다. 검증(Verification)에는 카메라 관측, 그리퍼 상태, 힘 측정값, 흡착 압력 또는 작업 전후 장면 비교를 사용할 수 있다. 검증 과정이 없다면 실패한 시도도 성공적인 수확으로 기록될 수 있다. 따라서 신뢰성 높은 자율성(Reliable Autonomy)을 확보하려면 단순히 명령을 실행한 후 성공했다고 가정하는 것이 아니라 물리적 작업 완료(Physical Task Completion)를 명시적으로 확인해야 한다.

수확된 딸기는 추가적인 손상을 발생시키지 않으면서 수집 용기(Collection Container)로 이동되어야 한다. 모션 계획은 과일 유지 상태, 매니퓰레이터 가속도, 충돌 위험, 저장 영역의 위치를 고려해야 한다. 과도한 낙하 높이나 충격을 방지하도록 과일 방출 동작(Release Action) 역시 제어해야 한다. 따라서 수확 소프트웨어는 단순한 과일 따기 동작만이 아니라 대상 선택부터 최종 수집까지의 전체 작업 주기(Complete Harvesting Cycle)를 관리한다.

여러 개의 딸기가 동시에 관측되는 경우 작업 스케줄링(Task Scheduling)이 중요해진다. 로봇은 성숙도, 접근 가능성, 신뢰도, 이동 거리, 예상 수확 시간, 실패 위험 등을 기준으로 대상을 우선순위화할 수 있다. 가장 가까운 과일을 선택하는 것이 항상 최적인 것은 아니며, 다른 대상이 더 안전한 접근 경로를 제공하거나 매니퓰레이터 움직임을 줄일 수도 있다. 효율적인 스케줄링은 수확 품질을 유지하면서 처리량(Throughput)을 향상시키고 불필요한 로봇 팔 움직임을 줄인다.

농업 조작은 불확실한 생물학적 환경에서 수행되기 때문에 실패 복구(Failure Recovery)가 필수적이다. 접근 과정에서 과일이 움직이거나 가려질 수 있고, 그리퍼에서 미끄러지거나 분리에 실패하거나 매니퓰레이터가 이동을 시작한 이후 접근할 수 없는 대상으로 판명될 수도 있다. 소프트웨어는 이러한 상태를 인식하고 다른 시점에서 재시도하거나 파지 방법을 변경하거나 다른 접근 경로를 선택하거나 해당 대상을 연기하거나 작업자 지원을 요청할지를 결정해야 한다.

반복적인 실패 시도가 무한정 계속되어서는 안 된다. 각각의 대상은 감지 신뢰도, 성숙도 추정값, 시도한 접근 방법, 조작 결과, 실패 원인을 포함하는 실행 상태(Execution State)를 유지할 수 있다. 설정된 횟수만큼 시도한 후에도 성공하지 못하면 로봇은 해당 과일을 일시적으로 접근 불가능(Unreachable) 상태로 표시하고 다음 작업을 계속할 수 있다. 이를 통해 하나의 어려운 딸기가 전체 수확 작업의 생산성을 크게 저하시키는 것을 방지할 수 있다.

이동형 수확 플랫폼(Mobile Harvesting Platform)은 조작 기능과 차량 주행을 조정해야 한다. 차량은 먼저 대상 식물이 매니퓰레이터 작업 공간(Manipulator Workspace)에 들어오도록 위치를 조정하고, 정밀 수확을 시작하기 전에 충분히 안정된 자세를 확보한다. 접근 가능한 대상의 처리가 완료되면 플랫폼은 다음 작업 위치로 이동한다. 따라서 주행(Navigation)과 조작(Manipulation)은 독립적인 하위 시스템이 아니라 더 큰 농업 작업을 구성하는 상호 조정된 단계로 동작한다.

보정(Calibration)은 수확 정확도에 큰 영향을 준다. 카메라 내부 파라미터(Camera Intrinsics), 카메라-매니퓰레이터 변환(Camera-to-Manipulator Transformation), 도구 중심점(Tool Center Point) 위치, 깊이 정렬(Depth Alignment), 기계적 오프셋(Mechanical Offset)은 실제 로봇의 물리적 구조를 정확하게 표현해야 한다. 작은 보정 오차도 인지와 모션 체인을 거치면서 누적되어 과일 주변에서 큰 오차로 나타날 수 있다. 따라서 특히 카메라, 매니퓰레이터 또는 엔드 이펙터 유지보수 이후에는 정기적인 보정 검사가 필요하다.

운영 데이터(Operational Data)는 전체 수확 과정을 기록해야 한다. 유용한 정보에는 대상 영상, 성숙도 추정값, 3차원 위치, 계획된 궤적, 실행 시간, 그리퍼 또는 도구 상태, 힘 측정값, 성공 여부, 실패 범주가 포함된다. 이러한 기록을 식물 또는 작물 열 위치와 연결하면 엔지니어는 개별 조작 이벤트뿐만 아니라 농경지 전체의 수확 성능도 평가할 수 있다.

성능 평가(Performance Evaluation)는 단순한 수확 성공률만을 넘어야 한다. 중요한 지표에는 감지 재현율(Detection Recall), 성숙도 분류 정확도, 위치 추정 오차, 성공적인 분리율(Successful Detachment Rate), 과일 손상률, 작업 주기 시간(Cycle Time), 인간 개입 빈도, 접근 불가능 대상 비율, 시간당 수확 과일 수가 포함된다. 높은 수확 성공률을 달성하더라도 각 작업 주기가 지나치게 느리거나 농산물을 손상시킨다면 상업적 가치가 제한되므로 이러한 지표들의 상호작용이 실제 상용 성능을 결정한다.

엣지 컴퓨팅(Edge Computing)은 인지, 모션 계획, 조작 모니터링, 복구 의사결정이 낮은 지연시간을 요구하고 지속적인 네트워크 연결 없이도 유지되어야 하므로 선택적 수확에 적합하다. 원격 시스템은 모델 학습, 플릿 분석(Fleet Analytics), 과거 작물 기록, 소프트웨어 업데이트를 지원할 수 있으며, 즉각적인 수확 루프(Immediate Harvesting Loop)는 신속하고 신뢰성 높은 물리적 상호작용을 위해 로봇 내부에서 로컬로 실행된다.

따라서 딸기 수확은 생물학적 인지(Biological Perception)와 물리적 조작(Physical Manipulation)을 분리할 수 없는 완전한 피지컬 AI 루프(Physical AI Loop)를 보여준다. 로봇은 과일을 관측하고, 성숙도와 접근 가능성을 추정하며, 3차원 형상을 결정하고, 접근 경로를 계획하고, 물리적 상호작용을 제어하고, 분리 결과를 검증한 후 결과를 기록한다. 각각의 단계는 다음 단계에 영향을 주며 전체 작업 과정에서 불확실성(Uncertainty)을 지속적으로 관리해야 한다.

따라서 성숙한 선택적 수확 시스템(Selective Harvesting System)은 하나의 과일 감지기나 로봇 팔 알고리즘만으로 정의되지 않는다. 작물 인지(Crop Perception), 성숙도 추정(Maturity Estimation), 3차원 위치 추정(Three-Dimensional Localization), 능동 인지(Active Perception), 모션 계획(Motion Planning), 순응 조작(Compliant Manipulation), 도구 제어(Tool Control), 검증(Verification), 복구(Recovery), 이동 플랫폼 협조(Mobile-Platform Coordination)의 통합을 통해 완성된다. 이러한 통합 소프트웨어 아키텍처(Integrated Software Architecture)는 딸기와 같은 연약한 작물을 점차 높은 일관성, 품질, 운영 효율성으로 자율 수확할 수 있도록 한다.

##  

## 08.06. Soil Sampling and Analysis Robot SW [w/Code]

![](images/image6.png){width="7.268055555555556in" height="7.268055555555556in"}

Soil sampling robots combine autonomous mobility with scientific measurement to convert field conditions into spatially referenced agricultural data. Instead of relying entirely on manual collection at a limited number of locations, a mobile robot can navigate to predefined or adaptively selected sampling points, operate a probe or sampling mechanism, record sensor measurements, and associate every observation with an accurate field position.

The sampling mission begins with spatial planning. A field boundary can be divided into a regular grid, management zones, crop rows, or regions selected from previous soil and crop information. Each target location becomes a sampling waypoint with associated measurement requirements. Mission software determines the visiting sequence while considering travel distance, terrain accessibility, restricted areas, remaining energy, and the expected duration of each sampling operation.

Accurate localization is essential because soil measurements become significantly more useful when they can be compared spatially across the field. GNSS-RTK can provide centimeter-level global coordinates under suitable conditions, while IMU and wheel odometry maintain motion continuity. The robot records the sampling location together with localization quality so that later analysis can distinguish precise measurements from observations collected under degraded positioning conditions.

Reaching a waypoint does not automatically mean that sampling can begin. The vehicle must stop within an acceptable positional tolerance and establish a sufficiently stable pose for the measurement mechanism. Software can verify position, orientation, vehicle motion, and terrain condition before authorizing probe deployment. This prevents inaccurate sampling caused by vehicle movement or by operating the mechanism at an unsuitable location.

Physical soil sampling requires coordinated control of the sampling mechanism. Depending on the system, a probe, auger, corer, or insertion tool may be lowered into the ground to a predefined depth. The controller manages actuator position, insertion speed, depth, force, and extraction. Mechanical resistance can vary substantially with soil compaction, moisture, stones, roots, and surface conditions, requiring feedback rather than a purely fixed motion sequence.

Force, motor current, position, or torque feedback can indicate whether the sampling tool is penetrating the soil normally. Unexpected resistance may indicate a stone or highly compacted region, while unusually low resistance may suggest loose soil or incomplete contact. The software should recognize abnormal insertion behavior and decide whether to retry, modify the insertion parameters, shift the sampling position, or mark the point as unsuccessful.

Some robots physically collect soil material for later laboratory analysis, while others perform in-situ measurements directly in the field. Sensors may measure moisture, temperature, electrical conductivity, pH, or other soil properties depending on the instrument configuration. The software architecture should separate sensor-specific acquisition logic from the general mission layer so that different measurement devices can be integrated without redesigning the complete autonomy system.

Sensor readings require contextual information to become scientifically useful. Each measurement should be associated with timestamp, geographic position, sampling depth, sensor identifier, calibration state, environmental conditions, and robot operating state. When physical samples are collected, a sample identifier should link the container or specimen with the digital record. This creates traceability from field location through measurement and later laboratory processing.

Measurement quality control is especially important because agricultural sensors can be affected by contamination, temperature, soil contact, calibration drift, and previous samples. The robot may perform repeated readings at the same location and evaluate whether measurements remain within an acceptable variation range. Outliers can be flagged automatically, while unstable readings can trigger additional measurement time or a repeated sampling procedure.

Cross-contamination must also be considered when the same physical tool is used at multiple sampling points. Residual soil from one location can influence the next measurement or physical sample. Depending on the mechanism, the robot may include cleaning, shaking, wiping, purging, or tool replacement between samples. Software must represent this cleaning process as part of the task sequence rather than treating it as an external manual operation.

Calibration management is another important software responsibility. Soil sensors may require periodic calibration against reference materials or known conditions, while mechanical sampling tools need verified depth and position references. Calibration parameters, dates, sensor serial numbers, and validity states should be stored with operational records. The system can prevent measurements when calibration has expired or warn operators that data quality may be reduced.

Adaptive sampling can improve efficiency compared with a completely fixed sampling grid. Initial measurements may reveal regions with rapidly changing soil properties, while other regions remain relatively uniform. Analysis software can use these observations to recommend additional sampling points in high-variation areas. The robot can then update its mission and collect denser information where additional measurements are likely to provide greater value.

This approach creates a closed loop between measurement and mission planning. The robot first observes a subset of the field, the analysis layer estimates spatial variation or uncertainty, and the planner determines where another measurement would reduce uncertainty most effectively. Adaptive sampling can therefore allocate robot time according to information value rather than treating every part of the field as equally uncertain.

Soil measurements become more useful when combined with other agricultural data layers. Sampling results can be associated with crop health observations, yield maps, terrain elevation, irrigation zones, fertilizer history, or remote-sensing information. Consistent georeferencing allows these heterogeneous datasets to be compared within a common spatial framework and supports later decisions about fertilization, irrigation, planting, or field management.

The resulting spatial dataset can be interpolated to estimate soil properties between measured locations. However, software should preserve the distinction between directly measured values and values predicted by spatial models. Measurement density, positioning accuracy, sensor uncertainty, and interpolation assumptions influence map reliability. Storing these quality indicators prevents visually smooth maps from being interpreted as more certain than the underlying observations justify.

Failure recovery is required because field sampling frequently encounters unpredictable physical conditions. A probe may fail to penetrate, a sample may not enter the collection chamber, a sensor may return an invalid reading, or the vehicle may be unable to reach the planned point. Recovery logic can retry the action, select a nearby alternative location, change insertion parameters, skip the point, or request operator assistance depending on mission policy.

Sampling state should therefore be maintained explicitly for every planned location. A waypoint can be marked as pending, reached, sampling, measured, failed, retried, substituted, or completed, together with the reason for any abnormal outcome. This state representation allows interrupted missions to resume without repeating valid samples and provides a clear record of which portions of the field were successfully characterized.

Operational logging should synchronize navigation and scientific measurement data. Robot pose, GNSS-RTK quality, vehicle velocity, probe position, actuator force, sensor readings, calibration information, retries, failure events, and sampling results should share a consistent time reference. Engineers can then determine whether an abnormal soil value originated from the field itself, a positioning problem, sensor instability, or incorrect mechanical operation.

Edge computing allows the robot to execute navigation, probe control, sensor acquisition, quality checks, and basic analysis without continuous network access. This is important in large agricultural areas where wireless connectivity may be intermittent. Cloud or on-premise systems can later aggregate measurements, generate field-scale maps, perform advanced analysis, manage historical records, and coordinate information across multiple robots or growing seasons.

Performance evaluation should include both robotic and scientific criteria. Navigation accuracy, waypoint completion rate, sampling cycle time, probe success, intervention frequency, and energy consumption describe operational performance. Measurement repeatability, missing-data rate, calibration compliance, spatial coverage, sample integrity, and agreement with reference measurements describe whether the robot is producing information of sufficient quality for agricultural decisions.

A soil sampling robot therefore represents more than an autonomous vehicle carrying a sensor. It is an integrated Physical AI measurement platform in which mobility determines where observations are collected, physical interaction determines whether the soil can be sampled correctly, sensing determines what properties are measured, and data management preserves the spatial and scientific meaning of every observation.

When navigation, sampling mechanisms, sensor acquisition, georeferencing, quality control, adaptive planning, and data management operate as one software system, soil analysis becomes a repeatable autonomous workflow. The robot can move from point to point, interact with the ground, evaluate measurement quality, recover from failures, and progressively construct a spatial representation of field conditions that supports more precise agricultural management.

토양 샘플링 로봇(Soil Sampling Robot)은 자율 이동(Autonomous Mobility)과 과학적 측정(Scientific Measurement)을 결합하여 농경지 상태를 공간적으로 참조된 농업 데이터(Spatially Referenced Agricultural Data)로 변환한다. 제한된 위치에서 수작업으로 시료를 채취하는 방식에만 의존하는 대신, 이동 로봇은 사전에 정의되거나 적응적으로 선택된 샘플링 지점으로 주행하고, 탐침 또는 샘플링 메커니즘을 작동시키며, 센서 측정값을 기록하고, 각각의 관측 결과를 정확한 농경지 위치와 연결할 수 있다.

샘플링 임무(Sampling Mission)는 공간 계획(Spatial Planning)에서 시작된다. 농경지 경계는 규칙적인 격자(Grid), 관리 구역(Management Zone), 작물 열(Crop Row) 또는 기존 토양 및 작물 정보를 기반으로 선택된 영역으로 나눌 수 있다. 각각의 목표 위치는 관련 측정 요구사항을 포함하는 샘플링 웨이포인트(Sampling Waypoint)가 된다. 임무 소프트웨어(Mission Software)는 이동 거리, 지형 접근성, 제한 구역, 잔여 에너지, 각 샘플링 작업의 예상 소요 시간을 고려하여 방문 순서를 결정한다.

토양 측정값은 농경지 전체에서 공간적으로 비교할 수 있을 때 활용 가치가 크게 높아지므로 정확한 위치 추정(Localization)이 필수적이다. GNSS-RTK는 적절한 조건에서 센티미터 수준의 전역 좌표(Global Coordinate)를 제공할 수 있으며, 관성측정장치(Inertial Measurement Unit, IMU)와 휠 오도메트리(Wheel Odometry)는 움직임의 연속성을 유지한다. 로봇은 샘플링 위치와 위치 추정 품질(Localization Quality)을 함께 기록하여 이후 분석에서 정확한 측정값과 위치 측정 성능이 저하된 상태에서 수집된 관측값을 구분할 수 있도록 한다.

웨이포인트에 도달했다고 해서 즉시 샘플링을 시작할 수 있는 것은 아니다. 차량은 허용 가능한 위치 오차 범위 내에서 정지하고 측정 메커니즘이 작동할 수 있도록 충분히 안정된 자세를 확보해야 한다. 소프트웨어는 탐침 전개(Probe Deployment)를 허가하기 전에 위치, 방향, 차량 움직임, 지형 상태를 검증할 수 있다. 이를 통해 차량이 움직이는 상태에서 샘플링하거나 적절하지 않은 위치에서 메커니즘을 작동하여 부정확한 시료를 획득하는 것을 방지한다.

물리적 토양 샘플링(Physical Soil Sampling)은 샘플링 메커니즘의 협조 제어(Coordinated Control)를 필요로 한다. 시스템에 따라 탐침(Probe), 오거(Auger), 코어러(Corer), 삽입 도구(Insertion Tool)를 사전에 정의된 깊이까지 지면으로 내려 보낼 수 있다. 제어기는 액추에이터 위치, 삽입 속도, 깊이, 힘, 회수 동작을 관리한다. 토양 다짐, 수분, 돌, 뿌리, 지표 상태에 따라 기계적 저항이 크게 달라질 수 있으므로 단순한 고정 동작 순서보다 피드백 제어(Feedback Control)가 필요하다.

힘, 모터 전류, 위치 또는 토크 피드백(Torque Feedback)을 이용하면 샘플링 도구가 토양을 정상적으로 관통하고 있는지 판단할 수 있다. 예상보다 높은 저항은 돌이나 매우 단단하게 다져진 영역을 의미할 수 있으며, 비정상적으로 낮은 저항은 느슨한 토양 또는 불완전한 접촉을 의미할 수 있다. 소프트웨어는 비정상적인 삽입 동작을 인식하고 재시도, 삽입 매개변수 변경, 샘플링 위치 이동 또는 해당 지점의 실패 처리 여부를 결정해야 한다.

일부 로봇은 이후 실험실 분석(Laboratory Analysis)을 위해 실제 토양 시료를 채취하는 반면, 다른 로봇은 현장에서 직접 현장 측정(In-Situ Measurement)을 수행한다. 센서는 장비 구성에 따라 수분, 온도, 전기전도도(Electrical Conductivity), 산도(pH) 또는 기타 토양 특성을 측정할 수 있다. 소프트웨어 아키텍처는 센서별 데이터 획득 로직(Sensor-Specific Acquisition Logic)을 일반적인 임무 계층(Mission Layer)과 분리하여 전체 자율 시스템을 재설계하지 않고도 서로 다른 측정 장치를 통합할 수 있도록 해야 한다.

센서 측정값이 과학적으로 유용한 정보가 되기 위해서는 상황 정보(Contextual Information)가 필요하다. 각각의 측정값은 타임스탬프(Timestamp), 지리적 위치, 샘플링 깊이, 센서 식별자, 보정 상태(Calibration State), 환경 조건, 로봇 운영 상태와 연결되어야 한다. 실제 시료를 채취하는 경우 시료 식별자(Sample Identifier)를 이용하여 용기 또는 시료와 디지털 기록을 연결해야 한다. 이를 통해 농경지 위치에서 측정 및 이후 실험실 처리까지 이어지는 추적성(Traceability)을 확보할 수 있다.

농업 센서는 오염, 온도, 토양 접촉 상태, 보정 드리프트(Calibration Drift), 이전 시료의 영향을 받을 수 있으므로 측정 품질 관리(Measurement Quality Control)가 특히 중요하다. 로봇은 동일한 위치에서 측정을 반복하고 측정값이 허용 가능한 변동 범위 내에 유지되는지를 평가할 수 있다. 이상치(Outlier)는 자동으로 표시할 수 있으며, 불안정한 측정값이 나타나는 경우 추가 측정 시간을 부여하거나 샘플링 절차를 반복하도록 할 수 있다.

동일한 물리적 도구를 여러 샘플링 지점에서 사용하는 경우 교차 오염(Cross-Contamination)도 고려해야 한다. 한 위치에서 남은 토양이 다음 측정값이나 실제 시료에 영향을 줄 수 있다. 메커니즘에 따라 로봇은 시료 사이에 세척(Cleaning), 흔들기(Shaking), 닦기(Wiping), 퍼징(Purging), 도구 교체(Tool Replacement) 과정을 수행할 수 있다. 소프트웨어는 이러한 세척 과정을 외부의 수동 작업으로 취급하지 않고 전체 작업 순서(Task Sequence)의 일부로 표현해야 한다.

보정 관리(Calibration Management) 역시 중요한 소프트웨어 책임이다. 토양 센서는 기준 물질 또는 알려진 조건을 이용한 주기적인 보정이 필요할 수 있으며, 기계식 샘플링 도구는 검증된 깊이 및 위치 기준이 필요하다. 보정 매개변수, 수행 날짜, 센서 일련번호, 유효 상태를 운영 기록과 함께 저장해야 한다. 시스템은 보정 유효기간이 만료된 경우 측정을 방지하거나 데이터 품질이 저하될 수 있음을 작업자에게 경고할 수 있다.

적응형 샘플링(Adaptive Sampling)은 완전히 고정된 샘플링 격자를 사용하는 방식보다 효율성을 향상시킬 수 있다. 초기 측정 결과 일부 영역에서는 토양 특성이 빠르게 변화하고 다른 영역에서는 상대적으로 균일한 상태가 유지되는 것을 확인할 수 있다. 분석 소프트웨어는 이러한 관측 결과를 이용하여 변화가 큰 영역에 추가적인 샘플링 지점을 추천할 수 있다. 이후 로봇은 임무를 갱신하고 추가 측정이 더 높은 가치를 제공할 가능성이 있는 영역에서 더욱 밀도 높은 정보를 수집할 수 있다.

이러한 방식은 측정(Measurement)과 임무 계획(Mission Planning) 사이에 폐루프(Closed Loop)를 형성한다. 로봇은 먼저 농경지의 일부 영역을 관측하고, 분석 계층(Analysis Layer)은 공간적 변동성 또는 불확실성을 추정하며, 계획기(Planner)는 추가 측정을 통해 불확실성을 가장 효과적으로 줄일 수 있는 위치를 결정한다. 따라서 적응형 샘플링은 농경지의 모든 영역을 동일하게 불확실한 것으로 취급하는 대신 정보 가치(Information Value)에 따라 로봇의 작업 시간을 배분할 수 있다.

토양 측정값은 다른 농업 데이터 계층(Agricultural Data Layer)과 결합될 때 더욱 유용해진다. 샘플링 결과는 작물 건강 관측, 수확량 지도(Yield Map), 지형 고도, 관개 구역, 비료 사용 이력, 원격 센싱(Remote Sensing) 정보와 연결할 수 있다. 일관된 지리참조(Georeferencing)를 적용하면 이러한 이질적인 데이터셋을 공통 공간 프레임워크(Common Spatial Framework)에서 비교할 수 있으며 이후 비료 살포, 관개, 파종 또는 농경지 관리 의사결정을 지원할 수 있다.

생성된 공간 데이터셋(Spatial Dataset)은 측정된 위치 사이의 토양 특성을 추정하기 위해 보간(Interpolation)할 수 있다. 그러나 소프트웨어는 직접 측정된 값과 공간 모델(Spatial Model)이 예측한 값의 차이를 명확하게 유지해야 한다. 측정 밀도, 위치 정확도, 센서 불확실성, 보간 가정은 지도 신뢰성(Map Reliability)에 영향을 준다. 이러한 품질 지표를 함께 저장하면 시각적으로 부드럽게 표현된 지도가 실제 관측값이 보장하는 것보다 더 높은 확실성을 가진 것으로 잘못 해석되는 것을 방지할 수 있다.

현장 샘플링에서는 예측하기 어려운 물리적 조건이 자주 발생하므로 실패 복구(Failure Recovery)가 필요하다. 탐침이 토양을 관통하지 못하거나 시료가 수집 챔버(Collection Chamber)에 들어가지 않거나 센서가 유효하지 않은 측정값을 반환하거나 차량이 계획된 지점에 접근하지 못할 수 있다. 복구 로직(Recovery Logic)은 임무 정책에 따라 작업 재시도, 인접한 대체 위치 선택, 삽입 매개변수 변경, 해당 지점 건너뛰기 또는 작업자 지원 요청을 수행할 수 있다.

따라서 계획된 각각의 위치에 대해 샘플링 상태(Sampling State)를 명시적으로 유지해야 한다. 웨이포인트는 대기(Pending), 도달(Reached), 샘플링 중(Sampling), 측정 완료(Measured), 실패(Failed), 재시도(Retried), 대체(Substituted), 완료(Completed) 등의 상태로 표시할 수 있으며 비정상적인 결과가 발생한 경우 그 원인도 함께 기록할 수 있다. 이러한 상태 표현(State Representation)을 이용하면 중단된 임무를 다시 시작할 때 이미 유효하게 획득한 시료를 반복하지 않고 농경지의 어느 영역이 성공적으로 측정되었는지를 명확하게 파악할 수 있다.

운영 로그(Operational Logging)는 주행 데이터와 과학적 측정 데이터를 동기화하여 기록해야 한다. 로봇 자세, GNSS-RTK 품질, 차량 속도, 탐침 위치, 액추에이터 힘, 센서 측정값, 보정 정보, 재시도, 실패 이벤트, 샘플링 결과가 일관된 시간 기준(Consistent Time Reference)을 공유해야 한다. 이를 통해 엔지니어는 비정상적인 토양 측정값이 실제 농경지 특성에서 발생한 것인지, 위치 추정 문제, 센서 불안정성 또는 잘못된 기계적 동작에서 발생한 것인지를 판단할 수 있다.

엣지 컴퓨팅(Edge Computing)을 사용하면 지속적인 네트워크 연결 없이도 로봇에서 주행, 탐침 제어, 센서 데이터 획득, 품질 검사, 기본 분석을 실행할 수 있다. 이는 무선 연결이 간헐적으로 중단될 수 있는 넓은 농업 지역에서 특히 중요하다. 이후 클라우드(Cloud) 또는 온프레미스(On-Premise) 시스템에서 측정값을 통합하고 농경지 규모의 지도를 생성하며 고급 분석, 이력 기록 관리, 여러 로봇 또는 여러 재배 시즌에 걸친 정보 통합을 수행할 수 있다.

성능 평가(Performance Evaluation)는 로봇 운영 기준과 과학적 측정 기준을 모두 포함해야 한다. 주행 정확도, 웨이포인트 완료율, 샘플링 작업 주기 시간(Sampling Cycle Time), 탐침 작업 성공률, 인간 개입 빈도, 에너지 소비량은 운영 성능을 나타낸다. 측정 반복성(Measurement Repeatability), 결측 데이터 비율, 보정 준수 여부, 공간 커버리지(Spatial Coverage), 시료 무결성(Sample Integrity), 기준 측정값과의 일치도는 로봇이 농업 의사결정에 충분한 품질의 정보를 생성하고 있는지를 나타낸다.

따라서 토양 샘플링 로봇은 단순히 센서를 탑재한 자율주행 차량 이상의 시스템이다. 이는 이동성(Mobility)이 관측 위치를 결정하고, 물리적 상호작용(Physical Interaction)이 토양을 올바르게 샘플링할 수 있는지를 결정하며, 센싱(Sensing)이 어떤 특성을 측정할지를 결정하고, 데이터 관리(Data Management)가 각각의 관측에 포함된 공간적·과학적 의미를 보존하는 통합 피지컬 AI 측정 플랫폼(Integrated Physical AI Measurement Platform)이다.

주행, 샘플링 메커니즘, 센서 데이터 획득, 지리참조, 품질 관리, 적응형 계획(Adaptive Planning), 데이터 관리가 하나의 소프트웨어 시스템으로 동작하면 토양 분석은 반복 가능한 자율 작업 흐름(Autonomous Workflow)으로 발전한다. 로봇은 지점 사이를 이동하고, 지면과 물리적으로 상호작용하며, 측정 품질을 평가하고, 실패에서 복구하면서 농경지 상태의 공간적 표현(Spatial Representation)을 점진적으로 구축할 수 있으며, 이를 통해 더욱 정밀한 농업 관리(Precision Agricultural Management)를 지원할 수 있다.

##  

## 08.07. Greenhouse Autonomous Robot Navigation [w/Code]

![](images/image7.png){width="7.268055555555556in" height="7.268055555555556in"}

Greenhouse autonomous navigation differs from open-field navigation because robots operate inside confined agricultural structures where GNSS reception may be weak or unavailable. Narrow aisles, repetitive crop rows, dense vegetation, irrigation equipment, workers, carts, and changing plant geometry create a semi-structured environment. Reliable navigation therefore depends primarily on onboard sensing, local mapping, localization, and obstacle-aware motion control.

The greenhouse can initially appear easier to navigate than an outdoor field because walls, aisles, and cultivation structures provide stable geometric references. However, many greenhouse sections look visually similar, and crop growth continuously changes the observable environment. Leaves may extend into aisles, harvesting equipment may be moved, and temporary objects may appear. Navigation software must distinguish persistent structural features from dynamic agricultural content.

A greenhouse robot commonly uses LiDAR, cameras, depth sensors, IMU, and wheel odometry to estimate its surroundings and motion. LiDAR provides geometric measurements of walls, racks, poles, and aisle boundaries, while cameras provide visual features and semantic information. Depth sensing supports short-range obstacle detection, and inertial and wheel measurements maintain motion continuity when environmental features temporarily become difficult to observe.

Localization can be based on simultaneous localization and mapping, previously generated maps, visual-inertial methods, LiDAR matching, or combinations of these approaches. The objective is to estimate the robot pose consistently within the greenhouse coordinate system. Because GNSS cannot always provide a reliable global reference indoors, localization quality depends on environmental features, sensor calibration, odometry stability, and the ability to recognize previously mapped locations.

Repetitive greenhouse geometry creates a particular localization challenge. Long parallel aisles can contain nearly identical structural patterns, causing scan matching or visual place recognition to confuse one location with another. Navigation systems can reduce this ambiguity by combining multiple sensing modalities, maintaining motion history, using known aisle topology, or introducing artificial landmarks where natural environmental features are insufficient.

A greenhouse map should represent more than free and occupied space. Operational information can include aisle identifiers, row numbers, docking locations, charging stations, restricted regions, crop-working positions, turning zones, and access points. Semantic mapping allows the mission planner to reason in agricultural terms, such as navigating to a particular crop row or inspection station, instead of relying only on geometric coordinates.

Global path planning determines how the robot should move between distant locations within this mapped structure. The planner considers aisle connectivity, vehicle dimensions, turning constraints, restricted passages, and mission destinations. Since greenhouse routes are often strongly constrained by aisle topology, the global path can be represented as a sequence of corridors and intersections that the robot must traverse before reaching its target working position.

Local planning handles the immediate environment around the moving robot. Workers, carts, hoses, containers, tools, fallen vegetation, or other robots can temporarily block an otherwise valid route. Sensors update the local obstacle representation, and the planner modifies velocity or trajectory while respecting vehicle kinematics. If safe passage is impossible, the robot should stop and wait, replan, or select an alternative route.

Narrow aisles make clearance management especially important. A robot may have only limited space between its body and crop beds, support structures, or protruding vegetation. The navigation stack should consider the complete vehicle footprint rather than treating the robot as a point. Safety margins can be adjusted according to localization uncertainty, vehicle speed, payload condition, and the reliability of nearby obstacle measurements.

Vegetation introduces a difficult distinction between obstacles that must never be contacted and flexible plant material that may extend into the navigation corridor. Treating every leaf as a rigid obstacle can make an aisle appear permanently blocked, while ignoring vegetation can damage crops. Perception software can classify structural obstacles, people, equipment, and vegetation so that navigation behavior reflects the physical and agricultural significance of each object.

Human-aware navigation is necessary because greenhouse workers may share aisles with autonomous robots. People can emerge from crop rows, bend into the robot\'s path, carry containers, or move unpredictably in restricted spaces. The robot should detect people reliably, maintain suitable separation, reduce speed in shared zones, and stop when safe motion cannot be guaranteed. Productivity objectives must remain subordinate to human safety.

Speed planning should adapt to local conditions rather than using one constant velocity throughout the greenhouse. The robot can travel faster in wide, empty corridors and reduce speed near workers, intersections, narrow crop rows, docking stations, or uncertain obstacles. Curvature, stopping distance, localization confidence, payload stability, and sensor visibility can also influence the maximum allowable velocity.

Turning at aisle ends can be challenging for platforms with limited steering geometry. The planner must verify that sufficient free space exists for the vehicle footprint and attached equipment before initiating a turn. Differential-drive robots may rotate within smaller areas, whereas Ackermann-steered platforms require larger trajectories. Agricultural implements or manipulators can further increase the effective turning envelope.

Precise docking and working-position alignment are required when the robot must charge, exchange payloads, inspect plants, or perform manipulation. General navigation may bring the platform near the destination, after which a local alignment procedure uses LiDAR, cameras, fiducial markers, or structural features to achieve greater positional accuracy. Separating coarse navigation from precision alignment improves robustness for task-specific operations.

Wheel slip and surface changes can degrade odometry even inside greenhouses. Wet floors, soil, drainage areas, rails, ramps, and accumulated plant material can alter traction. The localization system should compare predicted and observed motion to detect inconsistencies. When odometry becomes unreliable, greater weight can be placed on external environmental measurements while vehicle speed is reduced until stable localization is restored.

Localization uncertainty should directly influence navigation behavior. A robot that becomes uncertain about its position should not continue at normal speed merely because the planner still contains a valid path. The system can slow down, search for recognizable landmarks, perform local relocalization, return toward a previously reliable pose, or stop safely. This links localization confidence with operational risk rather than treating pose estimation as an isolated subsystem.

Map maintenance is necessary because greenhouse environments evolve over time. Crop growth changes visible geometry, cultivation equipment can be relocated, and temporary obstacles may remain for hours or days. Software should distinguish short-lived local obstacles from structural changes that justify updating the persistent map. Uncontrolled map updates can be equally problematic because temporary vegetation or workers should not become permanent environmental features.

Mission execution coordinates navigation with agricultural work. A robot may be instructed to inspect specific rows, transport materials, monitor crop health, perform harvesting support, or visit sampling locations. The mission manager converts these objectives into navigation goals, monitors progress, records completed locations, and handles interruptions. Navigation is therefore a service within a larger agricultural autonomy workflow rather than an isolated capability.

Recovery behavior is essential when the robot becomes blocked, loses localization, cannot complete a turn, or detects that the planned corridor is no longer traversable. Recovery may include stopping, reversing, rotating, clearing the local plan, relocalizing, choosing another aisle, or requesting assistance. Repeated recovery attempts should be bounded so that the robot does not create unsafe or unproductive motion in confined spaces.

Operational logging should record localization estimates, sensor status, planned and executed trajectories, obstacle detections, velocity commands, safety stops, replanning events, and recovery actions. These synchronized records allow engineers to determine whether a navigation failure originated from mapping, localization, perception, planning, control, mechanical behavior, or an unexpected environmental change.

Performance evaluation should include localization accuracy, path-tracking error, mission completion rate, collision-free operating time, human intervention frequency, obstacle recovery success, docking accuracy, aisle traversal speed, and navigation availability. Testing should also include difficult conditions such as repetitive rows, dense vegetation, moving workers, temporary blockages, low visual texture, changing illumination, and degraded sensor inputs.

Edge computing allows localization, mapping, perception, planning, safety monitoring, and motion control to remain onboard the robot with predictable latency. Greenhouse connectivity can support fleet coordination, remote supervision, data synchronization, and software updates, but immediate navigation should remain functional during network interruption. This separation preserves local safety while allowing higher-level operational intelligence to be shared.

Greenhouse autonomous navigation therefore combines structured infrastructure with the uncertainty of a living agricultural environment. Robust operation emerges from multi-sensor localization, semantic mapping, obstacle-aware planning, human detection, adaptive speed control, precision alignment, map maintenance, and recovery. When these capabilities operate together, the robot can repeatedly navigate between crop rows and working locations while supporting inspection, transport, monitoring, and harvesting tasks.

온실 자율주행(Greenhouse Autonomous Navigation)은 로봇이 GNSS 수신이 약하거나 사용할 수 없는 제한된 농업 시설 내부에서 동작한다는 점에서 노지 주행(Open-Field Navigation)과 다르다. 좁은 통로, 반복적인 작물 열, 밀집된 식생, 관개 장비, 작업자, 운반 카트, 지속적으로 변화하는 식물 형상은 반구조화 환경(Semi-Structured Environment)을 형성한다. 따라서 신뢰성 높은 주행은 주로 온보드 센싱(Onboard Sensing), 지역 지도 작성(Local Mapping), 위치 추정(Localization), 장애물 인식 모션 제어(Obstacle-Aware Motion Control)에 의존한다.

온실은 벽, 통로, 재배 구조물이 안정적인 기하학적 기준(Geometric Reference)을 제공하기 때문에 처음에는 실외 농경지보다 주행하기 쉬운 환경처럼 보일 수 있다. 그러나 온실의 여러 구역은 시각적으로 매우 유사하며 작물이 성장하면서 관측 가능한 환경도 지속적으로 변화한다. 잎이 통로까지 뻗어 나오거나 수확 장비가 이동하고 임시 물체가 나타날 수 있다. 따라서 주행 소프트웨어는 지속적으로 유지되는 구조적 특징(Persistent Structural Feature)과 동적으로 변화하는 농업 환경 요소(Dynamic Agricultural Content)를 구분해야 한다.

온실 로봇(Greenhouse Robot)은 일반적으로 라이다(LiDAR), 카메라(Camera), 깊이 센서(Depth Sensor), 관성측정장치(Inertial Measurement Unit, IMU), 휠 오도메트리(Wheel Odometry)를 사용하여 주변 환경과 자신의 움직임을 추정한다. 라이다는 벽, 랙, 기둥, 통로 경계에 대한 기하학적 측정값을 제공하고 카메라는 시각적 특징과 의미론적 정보를 제공한다. 깊이 센싱(Depth Sensing)은 근거리 장애물 감지를 지원하며, 관성 및 휠 측정값은 환경 특징을 일시적으로 관측하기 어려운 상황에서도 움직임의 연속성을 유지한다.

위치 추정(Localization)은 동시적 위치 추정 및 지도 작성(Simultaneous Localization and Mapping, SLAM), 사전에 생성된 지도, 시각-관성 방식(Visual-Inertial Method), 라이다 정합(LiDAR Matching) 또는 이러한 방법의 조합을 기반으로 수행할 수 있다. 목표는 온실 좌표계(Greenhouse Coordinate System) 내에서 로봇 자세(Robot Pose)를 일관되게 추정하는 것이다. 실내에서는 GNSS가 항상 신뢰할 수 있는 전역 기준을 제공하지 못하기 때문에 위치 추정 품질은 환경 특징, 센서 보정, 오도메트리 안정성, 기존에 지도화된 위치를 다시 인식하는 능력에 좌우된다.

반복적인 온실 기하 구조(Repetitive Greenhouse Geometry)는 특별한 위치 추정 문제를 발생시킨다. 길고 평행한 통로에는 거의 동일한 구조적 패턴이 반복될 수 있어 스캔 정합(Scan Matching)이나 시각적 장소 인식(Visual Place Recognition)이 서로 다른 위치를 동일한 장소로 혼동할 수 있다. 주행 시스템은 여러 센싱 방식의 결합, 이동 이력(Motion History) 유지, 알려진 통로 토폴로지(Aisle Topology) 활용 또는 자연적인 환경 특징이 부족한 구역에 인공 랜드마크(Artificial Landmark)를 추가하여 이러한 모호성을 줄일 수 있다.

온실 지도(Greenhouse Map)는 단순한 자유 공간과 점유 공간 이상의 정보를 표현해야 한다. 운영 정보에는 통로 식별자, 작물 열 번호, 도킹 위치(Docking Location), 충전소(Charging Station), 제한 구역, 작물 작업 위치, 회전 구역, 접근 지점 등이 포함될 수 있다. 의미론적 지도 작성(Semantic Mapping)을 사용하면 임무 계획기(Mission Planner)는 단순한 기하학적 좌표에만 의존하지 않고 특정 작물 열이나 검사 지점으로 이동하는 것과 같은 농업적 의미를 기반으로 판단할 수 있다.

전역 경로 계획(Global Path Planning)은 로봇이 지도화된 구조 내에서 멀리 떨어진 위치 사이를 어떻게 이동해야 하는지를 결정한다. 계획기는 통로 연결성, 차량 크기, 회전 제약조건, 제한된 통로, 임무 목적지를 고려한다. 온실의 이동 경로는 통로 토폴로지에 의해 강하게 제한되는 경우가 많으므로 전역 경로는 로봇이 목표 작업 위치에 도달하기 전에 통과해야 하는 일련의 통로와 교차점으로 표현할 수 있다.

지역 경로 계획(Local Planning)은 이동 중인 로봇 주변의 즉각적인 환경을 처리한다. 작업자, 카트, 호스, 용기, 도구, 떨어진 식생 또는 다른 로봇이 정상적으로 사용할 수 있는 경로를 일시적으로 차단할 수 있다. 센서는 지역 장애물 표현(Local Obstacle Representation)을 갱신하고 계획기는 차량의 운동학적 제약조건을 준수하면서 속도 또는 궤적을 변경한다. 안전한 통과가 불가능하면 로봇은 정지하여 기다리거나 경로를 재계획하거나 대체 경로를 선택해야 한다.

좁은 통로에서는 여유 공간 관리(Clearance Management)가 특히 중요하다. 로봇 차체와 작물 재배대, 지지 구조물 또는 통로로 돌출된 식생 사이의 공간이 매우 제한적일 수 있다. 주행 스택(Navigation Stack)은 로봇을 하나의 점으로 취급하지 않고 차량 전체 형상(Vehicle Footprint)을 고려해야 한다. 안전 여유거리(Safety Margin)는 위치 추정 불확실성, 차량 속도, 적재 상태, 주변 장애물 측정값의 신뢰도에 따라 조정할 수 있다.

식생은 절대로 접촉해서는 안 되는 장애물과 주행 통로로 뻗어 나올 수 있는 유연한 식물 조직을 구분해야 하는 어려운 문제를 발생시킨다. 모든 잎을 단단한 장애물로 처리하면 통로가 항상 차단된 것으로 판단될 수 있지만 식생을 무시하면 작물이 손상될 수 있다. 인지 소프트웨어(Perception Software)는 구조적 장애물, 사람, 장비, 식생을 분류하여 각 객체의 물리적·농업적 중요성에 따라 주행 행동이 달라지도록 할 수 있다.

온실 작업자가 자율 로봇과 동일한 통로를 사용할 수 있기 때문에 인간 인식 주행(Human-Aware Navigation)이 필요하다. 작업자는 작물 열 사이에서 갑자기 나타나거나 로봇의 진행 경로로 몸을 숙이거나 용기를 운반하거나 제한된 공간에서 예측하기 어렵게 움직일 수 있다. 로봇은 사람을 신뢰성 있게 감지하고 적절한 안전거리를 유지하며 공유 구역에서는 속도를 줄이고 안전한 이동을 보장할 수 없는 경우 정지해야 한다. 생산성 목표는 항상 사람의 안전보다 우선해서는 안 된다.

속도 계획(Speed Planning)은 온실 전체에서 하나의 일정한 속도를 사용하는 대신 지역 조건에 따라 적응적으로 수행되어야 한다. 로봇은 넓고 비어 있는 통로에서는 더 빠르게 이동하고 작업자, 교차점, 좁은 작물 열, 도킹 스테이션(Docking Station), 불확실한 장애물 주변에서는 속도를 낮출 수 있다. 곡률, 정지 거리, 위치 추정 신뢰도, 적재물 안정성, 센서 가시성도 최대 허용 속도(Maximum Allowable Velocity)에 영향을 줄 수 있다.

통로 끝에서의 회전은 조향 구조에 제한이 있는 플랫폼에서 어려운 문제가 될 수 있다. 계획기는 회전을 시작하기 전에 차량 전체 형상과 부착 장비가 이동할 수 있는 충분한 자유 공간이 존재하는지를 확인해야 한다. 차동 구동 로봇(Differential-Drive Robot)은 상대적으로 작은 공간에서 회전할 수 있지만 애커먼 조향 플랫폼(Ackermann-Steered Platform)은 더 큰 회전 궤적을 필요로 한다. 농업 작업 장치나 매니퓰레이터가 장착되면 실제 필요한 회전 영역(Turning Envelope)은 더욱 커질 수 있다.

로봇이 충전하거나 적재물을 교환하거나 식물을 검사하거나 조작 작업을 수행해야 하는 경우 정밀 도킹(Precise Docking)과 작업 위치 정렬(Working-Position Alignment)이 필요하다. 일반 주행을 통해 플랫폼을 목적지 근처까지 이동시킨 후, 지역 정렬 절차(Local Alignment Procedure)에서 라이다, 카메라, 기준 마커(Fiducial Marker), 구조적 특징을 이용하여 더 높은 위치 정확도를 확보할 수 있다. 일반적인 주행과 정밀 정렬을 분리하면 작업별 동작(Task-Specific Operation)의 강건성을 향상시킬 수 있다.

온실 내부에서도 바퀴 미끄러짐(Wheel Slip)과 노면 변화가 오도메트리 정확도를 저하시킬 수 있다. 젖은 바닥, 토양, 배수 구역, 레일, 경사로, 쌓여 있는 식물 잔해는 접지력을 변화시킬 수 있다. 위치 추정 시스템은 예측된 움직임과 실제 관측된 움직임을 비교하여 불일치를 감지해야 한다. 오도메트리의 신뢰성이 저하되면 외부 환경 측정값에 더 높은 가중치를 부여하고 안정적인 위치 추정이 복구될 때까지 차량 속도를 낮출 수 있다.

위치 추정 불확실성(Localization Uncertainty)은 주행 행동에 직접적인 영향을 주어야 한다. 계획기에 여전히 유효한 경로가 존재한다는 이유만으로 자신의 위치에 대한 확신이 낮아진 로봇이 정상 속도로 계속 이동해서는 안 된다. 시스템은 감속하거나 인식 가능한 랜드마크를 탐색하고, 지역 재위치 추정(Local Relocalization)을 수행하거나, 이전에 신뢰할 수 있었던 위치로 복귀하거나, 안전하게 정지할 수 있다. 이를 통해 위치 추정 신뢰도와 운영 위험을 연결하고 자세 추정을 독립적인 하위 시스템으로만 취급하지 않도록 한다.

온실 환경은 시간에 따라 변화하기 때문에 지도 유지관리(Map Maintenance)가 필요하다. 작물 성장은 관측 가능한 형상을 변화시키고 재배 장비가 이동할 수 있으며 임시 장애물이 수 시간 또는 수일 동안 유지될 수도 있다. 소프트웨어는 일시적인 지역 장애물과 영구 지도(Persistent Map)의 갱신이 필요한 구조적 변화를 구분해야 한다. 무분별한 지도 갱신 역시 문제가 될 수 있는데, 일시적으로 존재하는 식생이나 작업자가 영구적인 환경 특징으로 등록되어서는 안 되기 때문이다.

임무 실행(Mission Execution)은 주행과 농업 작업을 통합한다. 로봇은 특정 작물 열을 검사하거나 자재를 운반하고 작물 건강을 모니터링하거나 수확 작업을 지원하거나 샘플링 위치를 방문하도록 지시받을 수 있다. 임무 관리자(Mission Manager)는 이러한 목표를 주행 목표로 변환하고 진행 상태를 감시하며 완료된 위치를 기록하고 작업 중단 상황을 처리한다. 따라서 주행은 독립적인 기능이 아니라 더 큰 농업 자율 작업 흐름(Agricultural Autonomy Workflow)을 구성하는 하나의 서비스로 동작한다.

로봇의 경로가 차단되거나 위치 추정을 잃거나 회전을 완료할 수 없거나 계획된 통로를 더 이상 통과할 수 없다고 판단하는 경우 복구 행동(Recovery Behavior)이 필수적이다. 복구 과정에는 정지, 후진, 회전, 지역 경로 초기화, 재위치 추정, 다른 통로 선택 또는 작업자 지원 요청 등이 포함될 수 있다. 제한된 공간에서 로봇이 안전하지 않거나 생산성이 없는 움직임을 반복하지 않도록 복구 시도 횟수에는 명확한 제한을 두어야 한다.

운영 로그(Operational Logging)는 위치 추정값, 센서 상태, 계획 및 실제 실행 궤적, 장애물 감지, 속도 명령, 안전 정지, 경로 재계획 이벤트, 복구 행동을 기록해야 한다. 이러한 데이터를 시간적으로 동기화하여 기록하면 엔지니어는 주행 실패가 지도 작성, 위치 추정, 인지, 계획, 제어, 기계적 동작 또는 예상하지 못한 환경 변화 중 어디에서 발생했는지를 판단할 수 있다.

성능 평가(Performance Evaluation)는 위치 추정 정확도, 경로 추종 오차(Path-Tracking Error), 임무 완료율, 무충돌 운용 시간(Collision-Free Operating Time), 인간 개입 빈도, 장애물 복구 성공률, 도킹 정확도, 통로 주행 속도, 주행 가용성(Navigation Availability)을 포함해야 한다. 또한 반복적인 작물 열, 밀집된 식생, 이동하는 작업자, 일시적인 경로 차단, 낮은 시각적 텍스처(Low Visual Texture), 변화하는 조명, 성능이 저하된 센서 입력과 같은 어려운 조건도 시험에 포함해야 한다.

엣지 컴퓨팅(Edge Computing)을 이용하면 위치 추정, 지도 작성, 인지, 계획, 안전 모니터링, 모션 제어를 예측 가능한 지연시간으로 로봇 내부에서 실행할 수 있다. 온실 네트워크 연결은 플릿 협조(Fleet Coordination), 원격 감독(Remote Supervision), 데이터 동기화, 소프트웨어 업데이트를 지원할 수 있지만 즉각적인 주행 기능은 네트워크가 중단된 상태에서도 계속 동작할 수 있어야 한다. 이러한 분리는 로컬 안전(Local Safety)을 유지하면서 상위 수준의 운영 지능(Operational Intelligence)을 공유할 수 있도록 한다.

따라서 온실 자율주행은 구조화된 기반 시설(Structured Infrastructure)과 살아 있는 농업 환경의 불확실성을 결합하는 문제이다. 강건한 운영(Robust Operation)은 다중 센서 위치 추정(Multi-Sensor Localization), 의미론적 지도 작성(Semantic Mapping), 장애물 인식 경로 계획(Obstacle-Aware Planning), 사람 감지(Human Detection), 적응형 속도 제어(Adaptive Speed Control), 정밀 정렬(Precision Alignment), 지도 유지관리, 복구 기능의 통합을 통해 구현된다. 이러한 기능이 함께 동작하면 로봇은 작물 열과 작업 위치 사이를 반복적으로 자율주행하면서 검사, 운송, 모니터링, 수확 작업을 안정적으로 지원할 수 있다.

##  

## 08.08. Fleet Management for Agricultural AMR [w/Code]

![](images/image8.png){width="7.268055555555556in" height="7.268055555555556in"}

Agricultural fleet management extends autonomy from a single mobile robot to a coordinated group of autonomous mobile robots operating across fields, greenhouses, orchards, storage areas, and supporting facilities. Instead of optimizing one robot independently, fleet software manages missions, resources, traffic, energy, failures, and shared agricultural objectives so that multiple machines operate as a productive system.

A fleet may contain identical robots performing the same task or heterogeneous platforms with different capabilities. Navigation AMRs, spraying robots, harvesting platforms, inspection vehicles, transport robots, and soil-sampling systems can participate in a common operation. Fleet management must therefore maintain a capability model describing what each robot can perform, where it can operate, and which tools, sensors, payloads, or resources it currently possesses.

Mission requests originate from agricultural objectives rather than individual robot commands. A farm operator may request inspection of several crop rows, treatment of a field region, transport of harvested produce, or sampling at predefined locations. The fleet manager decomposes these objectives into executable tasks and assigns them to suitable robots according to capability, location, availability, workload, energy state, and mission priority.

Task allocation becomes a dynamic optimization problem when many robots and jobs are active simultaneously. Assigning the nearest robot is not always optimal because it may have insufficient battery capacity, the wrong implement, a full payload container, or a higher-priority task already scheduled. Fleet software evaluates multiple constraints and can reassign work as robot conditions, field priorities, or environmental conditions change.

Scheduling must also reflect agricultural timing requirements. Spraying may be restricted by wind or weather, harvesting may depend on crop maturity, and transport tasks may become urgent when collection containers are full. Some activities must occur in a particular sequence, while others can execute concurrently. The fleet scheduler therefore manages task dependencies, priorities, deadlines, resource conflicts, and expected completion times.

Spatial coordination is necessary because agricultural robots often share narrow access roads, greenhouse aisles, headlands, charging areas, loading stations, and docking locations. Two robots may individually calculate safe paths that conflict when executed simultaneously. Fleet-level traffic management can reserve critical zones, coordinate intersection access, control direction through narrow passages, and prevent deadlocks between robots competing for limited space.

Traffic management should remain compatible with local robot autonomy. The fleet system can provide routes, reservations, priorities, or movement permissions, while each robot retains responsibility for immediate obstacle avoidance and safety. A worker, animal, unexpected vehicle, or fallen object may require a robot to stop even when the fleet-level route is valid. Local safety decisions must therefore override centralized optimization commands.

Robot state reporting provides the information required for coordination. Each AMR can periodically report pose, velocity, mission state, battery level, payload condition, localization quality, communication status, health indicators, and active faults. The fleet manager converts these updates into an operational view of the complete robotic system and identifies robots that are available, busy, degraded, charging, disconnected, or requiring assistance.

Energy management becomes increasingly important as fleet size grows. Charging every robot only after its battery becomes low can create congestion and reduce mission availability. Fleet software can predict energy requirements from scheduled work and assign charging periods before critical missions begin. Charging stations become shared resources whose occupancy, queue length, charging duration, and robot priority must be coordinated.

Agricultural platforms may also require resources other than electrical energy. Spraying robots need chemical or water refilling, harvesting robots may need empty containers, transport robots can require unloading, and specialized tools may need cleaning or replacement. Fleet management can model these service stations and consumable resources so that robots are dispatched for replenishment before they become unable to complete assigned work.

Communication in agricultural environments cannot be assumed to remain continuously available. Large fields, terrain, vegetation, greenhouse structures, and rural network limitations can create intermittent connectivity. Each robot should therefore maintain enough local autonomy to continue safely during temporary communication loss. The fleet system can synchronize task state and operational data when connectivity returns instead of requiring permanent centralized control.

A distributed architecture can separate time-critical robot functions from fleet-level optimization. Perception, localization, obstacle avoidance, safety monitoring, and motion control remain onboard the robot, while task allocation, traffic coordination, resource scheduling, historical analysis, and multi-robot optimization can operate on an on-premise or remote server. This separation reduces network dependency while preserving system-wide coordination.

Failure handling is a major advantage of fleet-level intelligence. If a robot experiences a sensor fault, mobility problem, depleted battery, blocked route, or failed agricultural implement, the fleet manager can identify affected tasks and redistribute them to other capable robots. The failed unit can be directed to a safe location or maintenance area while the remaining fleet continues the agricultural operation with reduced disruption.

Task reassignment requires explicit knowledge of progress. A replacement robot should not automatically repeat an entire mission when part of the work has already been completed. The system should record completed rows, treated zones, collected samples, harvested locations, transported loads, and unfinished segments. Persistent mission state allows another robot to resume from an appropriate point without duplicating valid agricultural work.

Shared maps and operational information can improve coordination across the fleet. Robots may report blocked paths, temporary hazards, changed field conditions, inaccessible rows, or newly discovered obstacles. The fleet layer can distribute relevant information to other robots so they avoid repeating the same unsuccessful actions. However, temporary observations should be distinguished from persistent map changes before being propagated as long-term environmental knowledge.

Heterogeneous fleets require standardized task and status interfaces. A spraying robot and harvesting robot may use different internal software, but the fleet manager still needs common concepts for mission assignment, execution state, position, health, resource requirements, and completion reporting. Clear interfaces reduce coupling between vehicle-specific control software and the higher-level agricultural operations system.

Fleet monitoring provides operators with a consolidated view of agricultural activity. Instead of supervising each robot independently, operators can observe mission progress, robot locations, delayed tasks, energy status, faults, interventions, and completed work at the system level. Effective supervision should emphasize abnormal conditions and decisions requiring human attention rather than forcing operators to continuously monitor every autonomous action.

Operational data collected from multiple robots creates a foundation for fleet analytics. Mission duration, travel distance, idle time, charging time, intervention frequency, failure patterns, task success, and resource consumption can be compared across robots and locations. These records help identify bottlenecks and determine whether performance problems originate from individual machines, mission planning, field layout, or shared infrastructure.

Fleet optimization should focus on agricultural productivity rather than maximizing robot movement. A system with high vehicle utilization can still perform poorly if robots travel excessive distances, wait for shared resources, or create congestion. Useful objectives include completed agricultural work per hour, treatment coverage, harvested output, sampling coverage, energy consumed per task, intervention rate, and total mission completion time.

Scaling from several robots to dozens or more introduces additional coordination challenges. Centralized algorithms that work well for a small fleet may become computationally expensive or create communication bottlenecks. Hierarchical or distributed coordination can divide operations by field, greenhouse zone, robot group, or task type while maintaining higher-level synchronization of priorities and shared resources.

Security and access control are also important because fleet commands can directly influence physical machines. Robot identities, operator permissions, mission commands, software updates, and communication channels should be authenticated and protected. The system should maintain audit records showing who or what initiated important actions, particularly when commands affect chemical application, vehicle movement, or other safety-relevant agricultural operations.

Performance evaluation should include task completion rate, fleet throughput, robot utilization, idle time, traffic delay, charging congestion, mission reassignment success, communication recovery, human intervention frequency, and overall availability. Evaluation should also examine degraded scenarios in which robots fail, network links disappear, charging stations become unavailable, or important routes are unexpectedly blocked.

Agricultural fleet management therefore forms a collective autonomy layer above individual AMRs. Each robot retains local intelligence for safe perception, navigation, and task execution, while the fleet layer coordinates missions, traffic, energy, resources, failures, and shared information. The result is a distributed robotic system capable of adapting agricultural operations as conditions change across a site.

As agricultural deployments scale, the economic value of autonomy increasingly depends on this coordination layer. A single capable robot demonstrates autonomous functionality, but a managed fleet converts that capability into sustained operational capacity. Effective fleet software enables many agricultural AMRs to behave as a coordinated workforce that shares infrastructure, responds to failures, balances resources, and completes farm-level objectives efficiently.

농업 플릿 관리(Agricultural Fleet Management)는 자율성을 단일 이동 로봇에서 농경지, 온실, 과수원, 저장 구역 및 지원 시설 전반에서 운영되는 자율이동로봇(Autonomous Mobile Robot, AMR) 그룹으로 확장한다. 플릿 소프트웨어(Fleet Software)는 하나의 로봇을 독립적으로 최적화하는 대신 임무, 자원, 교통, 에너지, 장애 및 공동 농업 목표를 관리하여 여러 로봇이 하나의 생산적인 시스템으로 운영될 수 있도록 한다.

플릿(Fleet)은 동일한 작업을 수행하는 동종 로봇으로 구성될 수도 있고 서로 다른 기능을 가진 이기종 플랫폼(Heterogeneous Platform)으로 구성될 수도 있다. 주행 AMR, 정밀 살포 로봇, 수확 플랫폼, 검사 차량, 운송 로봇, 토양 샘플링 시스템 등이 하나의 공동 작업에 참여할 수 있다. 따라서 플릿 관리는 각 로봇이 수행할 수 있는 작업, 운용 가능한 영역, 현재 보유한 도구, 센서, 적재물 또는 자원을 설명하는 기능 모델(Capability Model)을 유지해야 한다.

임무 요청(Mission Request)은 개별 로봇 명령이 아니라 농업 작업 목표에서 시작된다. 농장 운영자는 여러 작물 열의 검사, 특정 농경지 영역의 처리, 수확 농산물 운송 또는 사전에 정의된 위치에서의 샘플링을 요청할 수 있다. 플릿 관리자(Fleet Manager)는 이러한 목표를 실행 가능한 작업으로 분해하고 기능, 위치, 가용성, 작업 부하, 에너지 상태, 임무 우선순위를 기준으로 적절한 로봇에 할당한다.

여러 로봇과 작업이 동시에 활성화되면 작업 할당(Task Allocation)은 동적 최적화 문제(Dynamic Optimization Problem)가 된다. 가장 가까운 로봇을 할당하는 것이 항상 최적인 것은 아니다. 해당 로봇의 배터리가 부족하거나 필요한 작업 장치를 갖추지 않았거나 적재 용기가 가득 차 있거나 이미 더 높은 우선순위의 작업이 예정되어 있을 수 있기 때문이다. 플릿 소프트웨어는 여러 제약조건을 평가하고 로봇 상태, 농경지 우선순위 또는 환경 조건이 변화함에 따라 작업을 재할당할 수 있다.

스케줄링(Scheduling)은 농업 작업의 시간적 요구사항도 반영해야 한다. 살포 작업은 바람이나 기상 조건에 따라 제한될 수 있고, 수확은 작물 성숙도에 따라 달라질 수 있으며, 수집 용기가 가득 차면 운송 작업의 우선순위가 높아질 수 있다. 일부 작업은 특정 순서로 수행되어야 하지만 다른 작업은 동시에 실행할 수 있다. 따라서 플릿 스케줄러(Fleet Scheduler)는 작업 종속성, 우선순위, 마감시간, 자원 충돌 및 예상 완료 시간을 관리한다.

농업 로봇은 좁은 진입로, 온실 통로, 두렁 회전 구역(Headland), 충전 구역, 적재 스테이션 및 도킹 위치를 공유하는 경우가 많으므로 공간적 협조(Spatial Coordination)가 필요하다. 두 로봇이 개별적으로는 안전한 경로를 계산하더라도 동시에 실행하면 서로 충돌할 수 있다. 플릿 수준 교통 관리(Fleet-Level Traffic Management)는 중요 구역을 예약하고, 교차로 접근을 조정하며, 좁은 통로의 진행 방향을 제어하고, 제한된 공간을 두고 경쟁하는 로봇 사이의 교착 상태(Deadlock)를 방지할 수 있다.

교통 관리(Traffic Management)는 로봇의 로컬 자율성(Local Autonomy)과 호환되어야 한다. 플릿 시스템은 경로, 예약, 우선순위 또는 이동 권한을 제공할 수 있지만 즉각적인 장애물 회피와 안전에 대한 책임은 각 로봇이 유지한다. 작업자, 동물, 예상하지 못한 차량 또는 떨어진 물체가 나타나면 플릿 수준의 경로가 유효하더라도 로봇이 정지해야 할 수 있다. 따라서 로컬 안전 판단(Local Safety Decision)은 중앙집중식 최적화 명령보다 우선해야 한다.

로봇 상태 보고(Robot State Reporting)는 협조에 필요한 정보를 제공한다. 각 AMR은 위치와 자세, 속도, 임무 상태, 배터리 수준, 적재 상태, 위치 추정 품질, 통신 상태, 상태 진단 지표 및 활성 장애 정보를 주기적으로 보고할 수 있다. 플릿 관리자는 이러한 업데이트를 전체 로봇 시스템의 운영 상태로 통합하고 사용 가능, 작업 중, 성능 저하, 충전 중, 연결 해제 또는 지원 필요 상태의 로봇을 식별한다.

플릿 규모가 증가할수록 에너지 관리(Energy Management)의 중요성도 커진다. 모든 로봇이 배터리가 부족해진 이후에만 충전을 시작하면 충전 혼잡이 발생하고 임무 가용성이 감소할 수 있다. 플릿 소프트웨어는 예정된 작업으로부터 에너지 요구량을 예측하고 중요한 임무가 시작되기 전에 충전 시간을 할당할 수 있다. 충전소는 점유 상태, 대기열 길이, 충전 시간 및 로봇 우선순위를 조정해야 하는 공유 자원(Shared Resource)이 된다.

농업 플랫폼에는 전기 에너지 이외의 자원도 필요할 수 있다. 살포 로봇은 약제 또는 물 보충이 필요하고, 수확 로봇은 빈 수집 용기가 필요하며, 운송 로봇은 적재물 하역이 필요할 수 있고, 특수 도구는 세척 또는 교체가 필요할 수 있다. 플릿 관리는 이러한 서비스 스테이션(Service Station)과 소모성 자원(Consumable Resource)을 모델링하여 로봇이 할당된 작업을 완료할 수 없는 상태가 되기 전에 보충 작업을 수행하도록 배차할 수 있다.

농업 환경에서는 통신 연결이 지속적으로 유지된다고 가정할 수 없다. 넓은 농경지, 지형, 식생, 온실 구조물, 농촌 지역의 네트워크 한계로 인해 간헐적인 연결 문제가 발생할 수 있다. 따라서 각 로봇은 일시적인 통신 단절 상황에서도 안전하게 작업을 계속할 수 있는 충분한 로컬 자율성을 유지해야 한다. 플릿 시스템은 영구적인 중앙집중식 제어를 요구하는 대신 연결이 복구되었을 때 작업 상태와 운영 데이터를 다시 동기화할 수 있다.

분산 아키텍처(Distributed Architecture)는 시간에 민감한 로봇 기능과 플릿 수준 최적화를 분리할 수 있다. 인지(Perception), 위치 추정(Localization), 장애물 회피, 안전 모니터링, 모션 제어(Motion Control)는 로봇 내부에서 수행하고, 작업 할당, 교통 협조, 자원 스케줄링, 이력 분석 및 다중 로봇 최적화(Multi-Robot Optimization)는 온프레미스(On-Premise) 또는 원격 서버에서 수행할 수 있다. 이러한 분리는 네트워크 의존성을 줄이면서 시스템 전체의 협조를 유지한다.

장애 처리(Failure Handling)는 플릿 수준 지능(Fleet-Level Intelligence)의 중요한 장점이다. 로봇에서 센서 장애, 이동 문제, 배터리 고갈, 경로 차단 또는 농업 작업 장치 고장이 발생하면 플릿 관리자는 영향을 받는 작업을 식별하고 다른 작업 가능한 로봇에 재분배할 수 있다. 장애가 발생한 로봇은 안전한 위치 또는 정비 구역으로 이동시키고 나머지 플릿은 작업 중단을 최소화하면서 농업 작업을 계속 수행할 수 있다.

작업 재할당(Task Reassignment)을 위해서는 진행 상태에 대한 명확한 정보가 필요하다. 기존 작업의 일부가 이미 완료된 경우 대체 로봇이 전체 임무를 처음부터 다시 수행해서는 안 된다. 시스템은 완료된 작물 열, 처리된 구역, 수집된 시료, 수확된 위치, 운송된 적재물, 미완료 구간을 기록해야 한다. 지속적 임무 상태(Persistent Mission State)를 유지하면 다른 로봇이 이미 완료된 농업 작업을 중복하지 않고 적절한 지점에서 작업을 이어갈 수 있다.

공유 지도(Shared Map)와 운영 정보는 플릿 전체의 협조를 향상시킬 수 있다. 로봇은 차단된 경로, 일시적인 위험 요소, 변화된 농경지 상태, 접근할 수 없는 작물 열 또는 새롭게 발견된 장애물을 보고할 수 있다. 플릿 계층(Fleet Layer)은 관련 정보를 다른 로봇에 배포하여 동일한 실패 행동을 반복하지 않도록 할 수 있다. 그러나 장기적인 환경 지식으로 전파하기 전에 일시적인 관측 정보와 영구적인 지도 변화를 구분해야 한다.

이기종 플릿(Heterogeneous Fleet)에는 표준화된 작업 및 상태 인터페이스(Standardized Task and Status Interface)가 필요하다. 살포 로봇과 수확 로봇은 서로 다른 내부 소프트웨어를 사용할 수 있지만 플릿 관리자는 임무 할당, 실행 상태, 위치, 상태 진단, 자원 요구사항 및 완료 보고에 대해 공통된 개념을 필요로 한다. 명확한 인터페이스는 차량별 제어 소프트웨어와 상위 수준 농업 운영 시스템 사이의 결합도(Coupling)를 줄인다.

플릿 모니터링(Fleet Monitoring)은 운영자에게 농업 활동에 대한 통합된 관점을 제공한다. 운영자는 각각의 로봇을 독립적으로 감독하는 대신 시스템 수준에서 임무 진행 상황, 로봇 위치, 지연된 작업, 에너지 상태, 장애, 인간 개입 및 완료된 작업을 확인할 수 있다. 효과적인 감독 시스템은 운영자가 모든 자율 행동을 지속적으로 감시하도록 요구하기보다 비정상적인 상태와 인간의 판단이 필요한 의사결정을 중심으로 정보를 제공해야 한다.

여러 로봇에서 수집된 운영 데이터는 플릿 분석(Fleet Analytics)의 기반을 형성한다. 임무 수행 시간, 이동 거리, 유휴 시간, 충전 시간, 인간 개입 빈도, 장애 패턴, 작업 성공률 및 자원 소비량을 로봇과 작업 위치별로 비교할 수 있다. 이러한 기록은 병목 현상(Bottleneck)을 식별하고 성능 문제가 개별 로봇, 임무 계획, 농경지 배치 또는 공유 인프라 중 어디에서 발생하는지를 판단하는 데 도움을 준다.

플릿 최적화(Fleet Optimization)는 로봇의 이동량을 최대화하는 것이 아니라 농업 생산성을 향상시키는 데 초점을 맞춰야 한다. 차량 활용률이 높더라도 로봇이 과도한 거리를 이동하거나 공유 자원을 기다리거나 교통 혼잡을 발생시키면 전체 성능은 낮을 수 있다. 유용한 최적화 목표에는 시간당 완료된 농업 작업량, 처리 커버리지, 수확량, 샘플링 커버리지, 작업당 에너지 소비량, 인간 개입률 및 전체 임무 완료 시간이 포함된다.

몇 대의 로봇에서 수십 대 이상의 로봇으로 규모를 확장하면 추가적인 협조 문제가 발생한다. 소규모 플릿에서 효과적으로 동작하는 중앙집중식 알고리즘(Centralized Algorithm)은 플릿 규모가 증가하면 계산 비용이 높아지거나 통신 병목 현상을 발생시킬 수 있다. 계층형 또는 분산 협조(Hierarchical or Distributed Coordination)는 농경지, 온실 구역, 로봇 그룹 또는 작업 유형별로 운영을 분할하면서 우선순위와 공유 자원에 대한 상위 수준 동기화를 유지할 수 있다.

플릿 명령은 실제 물리적 기계의 동작에 직접적인 영향을 줄 수 있으므로 보안(Security)과 접근 제어(Access Control) 역시 중요하다. 로봇 식별 정보, 운영자 권한, 임무 명령, 소프트웨어 업데이트, 통신 채널은 인증되고 보호되어야 한다. 특히 명령이 약제 살포, 차량 이동 또는 기타 안전 관련 농업 작업에 영향을 미치는 경우 시스템은 중요한 행동을 누가 또는 무엇이 시작했는지를 확인할 수 있는 감사 기록(Audit Record)을 유지해야 한다.

성능 평가(Performance Evaluation)는 작업 완료율, 플릿 처리량(Fleet Throughput), 로봇 활용률, 유휴 시간, 교통 지연, 충전 혼잡, 임무 재할당 성공률, 통신 복구, 인간 개입 빈도 및 전체 가용성(Overall Availability)을 포함해야 한다. 또한 로봇 장애, 네트워크 연결 상실, 충전소 사용 불가 또는 중요 이동 경로의 예상치 못한 차단과 같은 성능 저하 시나리오(Degraded Scenario)에서도 시스템을 평가해야 한다.

따라서 농업 플릿 관리(Agricultural Fleet Management)는 개별 AMR 상위에 위치하는 집단 자율성 계층(Collective Autonomy Layer)을 형성한다. 각 로봇은 안전한 인지, 주행 및 작업 실행을 위한 로컬 지능(Local Intelligence)을 유지하고, 플릿 계층은 임무, 교통, 에너지, 자원, 장애 및 공유 정보를 조정한다. 그 결과 현장 조건이 변화함에 따라 농업 운영을 적응적으로 조정할 수 있는 분산 로봇 시스템(Distributed Robotic System)이 형성된다.

농업 로봇의 배치 규모가 확대될수록 자율성의 경제적 가치는 이러한 협조 계층(Coordination Layer)에 더욱 크게 의존하게 된다. 하나의 고성능 로봇은 자율 기능을 보여줄 수 있지만 관리되는 플릿(Managed Fleet)은 이러한 기능을 지속 가능한 운영 능력으로 전환한다. 효과적인 플릿 소프트웨어는 다수의 농업 AMR이 인프라를 공유하고, 장애에 대응하며, 자원을 균형 있게 배분하고, 농장 수준 목표(Farm-Level Objective)를 효율적으로 완료하는 협조된 로봇 작업군(Coordinated Robotic Workforce)으로 동작할 수 있도록 한다.

##  

## 08.09. Agricultural Robot Connectivity Rural 4G 5G

![](images/image9.png){width="7.268055555555556in" height="7.268055555555556in"}

Agricultural robots often operate across large rural areas where communication conditions are less predictable than in factories or urban facilities. Fields, orchards, greenhouses, hills, vegetation, and long distances can weaken wireless coverage or create temporary communication loss. Connectivity architecture must therefore support useful remote services without making immediate robot safety or basic autonomy dependent on a continuously available network.

Fourth-generation mobile networks provide a practical communication foundation in many agricultural regions because existing 4G infrastructure can support telemetry, mission updates, monitoring, and moderate-volume data transfer. However, signal quality can vary substantially across a farm. Robot software should continuously observe connection state, signal quality, latency, and data-transfer performance rather than assuming that network availability is uniform throughout the operating area.

Fifth-generation mobile networks can provide greater bandwidth, lower latency, and improved support for large numbers of connected devices when suitable infrastructure is available. These characteristics are useful for multi-robot operations, high-resolution sensor data transfer, remote diagnostics, and coordinated agricultural services. Nevertheless, 5G availability in rural areas may be incomplete, so robot architecture should treat it as an enhanced communication capability rather than a requirement for basic autonomous operation.

A robust agricultural platform can support multiple communication interfaces such as 4G, 5G, Wi-Fi, private cellular networks, and local radio links. Different interfaces can serve different operating zones and data requirements. The communication manager can select an available network according to coverage, bandwidth, latency, cost, and mission policy while preserving the robot\'s application-level communication state during transitions between networks.

The most important architectural principle is to separate safety-critical local control from network-dependent services. Perception, localization, obstacle avoidance, emergency handling, motion control, and essential task execution should remain onboard whenever possible. Remote systems can provide mission planning, fleet coordination, analytics, visualization, software management, and historical data processing without becoming part of the immediate safety control loop.

This edge-first architecture allows a robot to continue operating safely when cellular communication temporarily disappears. Depending on mission policy, the robot may continue its current task, finish a defined segment, reduce operating speed, move toward an area with known coverage, or stop at a safe location. The appropriate response depends on whether communication is merely useful for supervision or mandatory for the specific agricultural operation being performed.

Communication traffic should be classified according to operational importance. Emergency and safety-related status, robot health, mission commands, and compact telemetry generally require higher priority than large sensor files or historical logs. Camera video, LiDAR recordings, diagnostic archives, and model-training data can consume substantial bandwidth and should not prevent critical control information from being delivered when network capacity becomes limited.

Quality of service management can therefore prioritize traffic according to latency and reliability requirements. A small state message may need rapid delivery even when its bandwidth requirement is minimal, whereas a large image dataset may tolerate delayed transmission. Communication software can adjust update frequency, compression, video quality, or upload scheduling according to available network capacity while maintaining essential robot supervision.

Store-and-forward operation is particularly useful in rural environments. When connectivity becomes unavailable, the robot can continue recording telemetry, mission events, sensor results, agricultural measurements, and diagnostic information in local storage. After communication is restored, the system transfers the accumulated records while preserving timestamps and sequence information so that remote databases can reconstruct the complete operational history.

Intermittent connectivity also requires careful command handling. A delayed command should not necessarily be executed after the robot\'s operating context has changed. Commands can include timestamps, expiration conditions, mission identifiers, sequence numbers, and acknowledgement states. The robot verifies whether a received instruction remains valid before execution, reducing the risk that stale network messages produce inappropriate physical actions.

Fleet coordination becomes more difficult when robots experience different network conditions. Some robots may remain connected to the fleet manager while others temporarily operate offline. Each robot should retain its assigned mission state locally, while the fleet system maintains the last confirmed status. When communication returns, synchronization logic reconciles completed tasks, position history, resource usage, and newly assigned work without unnecessarily repeating valid operations.

Private 4G or 5G networks can provide an alternative for large farms, greenhouses, research facilities, or agricultural campuses requiring controlled coverage. Local cellular infrastructure can improve network management, device authentication, and predictable access within the deployment site. Such networks can complement public cellular service, especially where agricultural operations require consistent connectivity across a defined production area.

Network planning should consider the physical characteristics of agricultural environments. Terrain elevation, buildings, greenhouse structures, dense crops, trees, and seasonal vegetation can affect radio propagation. Coverage that is sufficient during one season may change as crops grow or equipment is relocated. Connectivity testing should therefore be performed across actual robot routes and operating heights rather than relying only on theoretical coverage maps.

Remote supervision benefits significantly from reliable connectivity. Operators can observe robot location, mission progress, battery condition, faults, sensor health, and agricultural task results from a central interface. Video or image streams may be requested when additional visual confirmation is required. The system should support supervision without requiring continuous manual driving, preserving autonomy as the normal operating mode.

Remote intervention requires stronger safeguards than passive monitoring. If an operator sends movement or recovery commands through a network, communication delay, packet loss, and disconnection can directly affect physical behavior. The robot should enforce local safety limits regardless of remote commands and automatically stop or transition to a safe state when the communication quality required for a remote-control mode cannot be maintained.

Cybersecurity is essential because wireless communication connects physical agricultural machines to external systems. Devices should authenticate communication partners, protect command and telemetry channels, and restrict access according to operator or service permissions. Software updates, configuration changes, and mission commands require particular protection because unauthorized modification could alter robot behavior or agricultural treatment.

Data security must also account for agricultural operational information. Robot logs can contain field maps, crop conditions, production activity, equipment status, and operational schedules. Communication architecture should protect data both during transmission and when temporarily stored onboard. Audit records can document important remote commands, configuration changes, user access, and software deployment events.

On-premise computing can reduce dependence on distant cloud infrastructure. A local farm server or edge gateway can coordinate robots, store high-volume sensor data, host maps, and provide fleet services over a local network even when the external internet connection is unavailable. Cloud systems can then be used for long-term storage, cross-site analysis, model management, and services that do not require immediate local response.

Bandwidth management becomes especially important when many agricultural robots share the same cellular connection or access infrastructure. Simultaneous video uploads from multiple machines can saturate the network even though basic telemetry requires relatively little capacity. Fleet-level communication policies can schedule large transfers, limit stream quality, prioritize robots with active faults, and postpone nonessential synchronization until network demand decreases.

Connectivity performance should be evaluated using more than nominal network speed. Useful measures include coverage availability, round-trip latency, latency variation, packet loss, reconnection time, effective upload and download throughput, handover behavior, and the percentage of missions completed during communication degradation. Worst-case and percentile measurements are often more informative for robotic operation than average network performance alone.

Testing should intentionally include network failures. Robots should be evaluated during complete disconnection, high latency, reduced bandwidth, packet loss, network switching, server unavailability, and delayed message delivery. These tests verify that local autonomy remains safe, data are preserved, stale commands are rejected, fleet state can be synchronized after recovery, and operators receive understandable information about communication status.

Agricultural connectivity should therefore be designed as a resilient service layer rather than as a permanent control dependency. 4G and 5G networks extend the reach of fleet management, remote supervision, analytics, and data exchange, while onboard intelligence preserves immediate autonomy. This architecture allows communication quality to change without causing the robot\'s fundamental perception, navigation, or safety capabilities to disappear.

As agricultural robot deployments expand, connectivity becomes the information infrastructure connecting individual machines to collective operations. A well-designed system combines 4G, 5G, local networking, edge computing, buffering, synchronization, traffic prioritization, and secure remote services. The result is a connected agricultural robot architecture capable of operating productively across rural environments while remaining resilient to the network limitations inherent in real-world farming.

농업 로봇(Agricultural Robot)은 공장이나 도시 시설보다 통신 환경을 예측하기 어려운 넓은 농촌 지역에서 운용되는 경우가 많다. 농경지, 과수원, 온실, 구릉지, 식생, 긴 통신 거리는 무선 통신 범위(Wireless Coverage)를 약화시키거나 일시적인 통신 단절을 발생시킬 수 있다. 따라서 연결성 아키텍처(Connectivity Architecture)는 지속적인 네트워크 연결에 로봇의 즉각적인 안전이나 기본 자율성을 의존하지 않으면서 유용한 원격 서비스를 지원하도록 설계되어야 한다.

4세대 이동통신망(Fourth-Generation Mobile Network, 4G)은 기존 4G 인프라를 이용하여 텔레메트리(Telemetry), 임무 업데이트, 모니터링, 중간 수준의 데이터 전송을 지원할 수 있기 때문에 많은 농업 지역에서 실용적인 통신 기반을 제공한다. 그러나 신호 품질은 하나의 농장 내부에서도 크게 달라질 수 있다. 로봇 소프트웨어는 전체 작업 구역에서 네트워크 가용성이 동일하다고 가정하지 않고 연결 상태, 신호 품질, 지연시간(Latency), 데이터 전송 성능을 지속적으로 관찰해야 한다.

5세대 이동통신망(Fifth-Generation Mobile Network, 5G)은 적절한 인프라가 구축된 경우 더 높은 대역폭(Bandwidth), 낮은 지연시간, 대규모 연결 장치 지원 능력을 제공할 수 있다. 이러한 특성은 다중 로봇 운영, 고해상도 센서 데이터 전송, 원격 진단(Remote Diagnostics), 협조형 농업 서비스에 유용하다. 그러나 농촌 지역에서는 5G 가용성이 충분하지 않을 수 있으므로 로봇 아키텍처는 이를 기본 자율운영을 위한 필수조건이 아니라 향상된 통신 기능(Enhanced Communication Capability)으로 취급해야 한다.

강건한 농업 플랫폼(Robust Agricultural Platform)은 4G, 5G, 와이파이(Wi-Fi), 사설 셀룰러 네트워크(Private Cellular Network), 로컬 무선 링크(Local Radio Link)와 같은 여러 통신 인터페이스를 지원할 수 있다. 서로 다른 인터페이스는 각각 다른 운영 구역과 데이터 요구사항을 담당할 수 있다. 통신 관리자(Communication Manager)는 네트워크 간 전환 과정에서도 로봇의 애플리케이션 수준 통신 상태를 유지하면서 커버리지, 대역폭, 지연시간, 비용, 임무 정책에 따라 사용 가능한 네트워크를 선택할 수 있다.

가장 중요한 아키텍처 원칙은 안전 필수 로컬 제어(Safety-Critical Local Control)와 네트워크 의존 서비스(Network-Dependent Service)를 분리하는 것이다. 인지(Perception), 위치 추정(Localization), 장애물 회피, 비상 상황 처리, 모션 제어(Motion Control), 필수 작업 실행은 가능한 한 로봇 내부에서 수행되어야 한다. 원격 시스템은 즉각적인 안전 제어 루프(Safety Control Loop)의 일부가 되지 않으면서 임무 계획, 플릿 협조(Fleet Coordination), 분석, 시각화, 소프트웨어 관리, 이력 데이터 처리를 제공할 수 있다.

이러한 엣지 우선 아키텍처(Edge-First Architecture)를 사용하면 셀룰러 통신이 일시적으로 끊어져도 로봇이 안전하게 작업을 계속할 수 있다. 임무 정책에 따라 로봇은 현재 작업을 계속하거나 정의된 구간을 완료하거나 운행 속도를 낮추거나 통신 가능 구역으로 이동하거나 안전한 위치에서 정지할 수 있다. 적절한 대응 방식은 통신이 단순한 감독을 위해 필요한 것인지 또는 특정 농업 작업에 반드시 필요한 것인지에 따라 달라진다.

통신 트래픽(Communication Traffic)은 운영 중요도에 따라 분류해야 한다. 비상 및 안전 관련 상태 정보, 로봇 상태 진단, 임무 명령, 소규모 텔레메트리는 일반적으로 대용량 센서 파일이나 이력 로그보다 높은 우선순위를 가져야 한다. 카메라 영상, 라이다 기록, 진단 아카이브, 모델 학습 데이터는 상당한 대역폭을 소비할 수 있으므로 네트워크 용량이 제한될 때 중요한 제어 정보의 전달을 방해해서는 안 된다.

따라서 서비스 품질 관리(Quality of Service Management, QoS)는 지연시간과 신뢰성 요구사항에 따라 트래픽의 우선순위를 설정할 수 있다. 작은 상태 메시지는 요구 대역폭이 매우 작더라도 빠른 전달이 필요할 수 있지만 대규모 이미지 데이터셋은 지연된 전송을 허용할 수 있다. 통신 소프트웨어는 필수적인 로봇 감독 기능을 유지하면서 사용 가능한 네트워크 용량에 따라 업데이트 주기, 압축, 영상 품질 또는 업로드 일정을 조정할 수 있다.

저장 후 전달(Store-and-Forward) 방식은 농촌 환경에서 특히 유용하다. 연결이 중단되면 로봇은 텔레메트리, 임무 이벤트, 센서 결과, 농업 측정 데이터, 진단 정보를 로컬 저장장치(Local Storage)에 계속 기록할 수 있다. 통신이 복구되면 시스템은 타임스탬프(Timestamp)와 순서 정보를 유지하면서 누적된 기록을 전송하여 원격 데이터베이스가 전체 운영 이력을 재구성할 수 있도록 한다.

간헐적 연결(Intermittent Connectivity)은 명령 처리에서도 세심한 관리가 필요하다. 지연된 명령은 로봇의 운영 상황이 이미 변경된 이후에는 반드시 실행되어야 하는 것이 아니다. 명령에는 타임스탬프, 만료 조건(Expiration Condition), 임무 식별자, 순서 번호, 승인 상태(Acknowledgement State)를 포함할 수 있다. 로봇은 수신된 명령이 여전히 유효한지를 실행 전에 확인하여 오래된 네트워크 메시지가 부적절한 물리적 동작을 발생시키는 위험을 줄인다.

로봇마다 서로 다른 네트워크 상태를 경험하면 플릿 협조가 더욱 어려워진다. 일부 로봇은 플릿 관리자(Fleet Manager)와 연결된 상태를 유지하는 반면 다른 로봇은 일시적으로 오프라인 상태에서 작업할 수 있다. 각 로봇은 할당된 임무 상태를 로컬에 유지하고 플릿 시스템은 마지막으로 확인된 상태를 보존해야 한다. 통신이 복구되면 동기화 로직(Synchronization Logic)이 완료된 작업, 위치 이력, 자원 사용량, 새롭게 할당된 작업을 조정하여 이미 정상적으로 완료된 작업을 불필요하게 반복하지 않도록 한다.

사설 4G 또는 5G 네트워크(Private 4G or 5G Network)는 통제된 통신 범위가 필요한 대규모 농장, 온실, 연구 시설 또는 농업 단지에서 대안이 될 수 있다. 로컬 셀룰러 인프라(Local Cellular Infrastructure)는 배치 현장 내부에서 네트워크 관리, 장치 인증(Device Authentication), 예측 가능한 접속 성능을 향상시킬 수 있다. 이러한 네트워크는 특히 일정한 생산 구역 전체에서 일관된 연결이 필요한 농업 작업에서 공공 셀룰러 서비스를 보완할 수 있다.

네트워크 계획(Network Planning)은 농업 환경의 물리적 특성을 고려해야 한다. 지형 고도, 건물, 온실 구조물, 밀집된 작물, 나무, 계절에 따른 식생 변화는 전파 특성(Radio Propagation)에 영향을 줄 수 있다. 한 계절에 충분했던 통신 범위가 작물이 성장하거나 장비가 이동함에 따라 달라질 수 있다. 따라서 연결성 시험(Connectivity Testing)은 이론적인 커버리지 지도에만 의존하지 않고 실제 로봇 이동 경로와 운용 높이에서 수행해야 한다.

원격 감독(Remote Supervision)은 신뢰성 있는 연결을 통해 상당한 이점을 얻을 수 있다. 운영자는 중앙 인터페이스에서 로봇 위치, 임무 진행 상태, 배터리 상태, 장애, 센서 상태 진단, 농업 작업 결과를 확인할 수 있다. 추가적인 시각적 확인이 필요한 경우 영상 또는 이미지 스트림을 요청할 수 있다. 시스템은 지속적인 수동 운전을 요구하지 않고 원격 감독을 지원해야 하며 자율운영(Autonomous Operation)을 정상적인 운영 방식으로 유지해야 한다.

원격 개입(Remote Intervention)은 수동적인 모니터링보다 강력한 안전장치를 필요로 한다. 운영자가 네트워크를 통해 이동 또는 복구 명령을 전송하면 통신 지연, 패킷 손실(Packet Loss), 연결 단절이 물리적 동작에 직접 영향을 줄 수 있다. 로봇은 원격 명령과 관계없이 로컬 안전 한계(Local Safety Limit)를 강제해야 하며 원격 제어 모드(Remote-Control Mode)에 필요한 통신 품질을 유지할 수 없는 경우 자동으로 정지하거나 안전 상태로 전환해야 한다.

무선 통신은 실제 농업 기계를 외부 시스템과 연결하므로 사이버보안(Cybersecurity)이 필수적이다. 장치는 통신 상대를 인증하고 명령 및 텔레메트리 채널을 보호하며 운영자 또는 서비스 권한에 따라 접근을 제한해야 한다. 소프트웨어 업데이트, 구성 변경(Configuration Change), 임무 명령은 승인되지 않은 변경이 로봇 동작이나 농업 처리 과정에 영향을 줄 수 있으므로 특히 강력하게 보호해야 한다.

데이터 보안(Data Security)은 농업 운영 정보도 고려해야 한다. 로봇 로그에는 농경지 지도, 작물 상태, 생산 활동, 장비 상태, 운영 일정이 포함될 수 있다. 통신 아키텍처는 데이터 전송 중뿐만 아니라 로봇 내부에 임시로 저장되는 동안에도 데이터를 보호해야 한다. 감사 기록(Audit Record)은 중요한 원격 명령, 구성 변경, 사용자 접근, 소프트웨어 배포 이벤트를 기록할 수 있다.

온프레미스 컴퓨팅(On-Premise Computing)은 원격 클라우드 인프라에 대한 의존성을 줄일 수 있다. 로컬 농장 서버(Local Farm Server) 또는 엣지 게이트웨이(Edge Gateway)는 외부 인터넷 연결을 사용할 수 없는 경우에도 로컬 네트워크를 통해 로봇을 조정하고 대용량 센서 데이터를 저장하며 지도와 플릿 서비스를 제공할 수 있다. 클라우드 시스템(Cloud System)은 장기 저장, 사이트 간 분석, 모델 관리, 즉각적인 로컬 응답이 필요하지 않은 서비스를 담당할 수 있다.

여러 농업 로봇이 동일한 셀룰러 연결 또는 네트워크 인프라를 공유하면 대역폭 관리(Bandwidth Management)가 특히 중요해진다. 여러 로봇에서 동시에 영상을 업로드하면 기본적인 텔레메트리에 필요한 용량은 작더라도 전체 네트워크가 포화될 수 있다. 플릿 수준 통신 정책(Fleet-Level Communication Policy)은 대용량 데이터 전송 일정을 조정하고, 스트림 품질을 제한하며, 장애가 발생한 로봇에 우선순위를 부여하고, 네트워크 수요가 감소할 때까지 중요하지 않은 동기화를 연기할 수 있다.

연결 성능(Connectivity Performance)은 명목상의 네트워크 속도만으로 평가해서는 안 된다. 유용한 평가 지표에는 통신 범위 가용성(Coverage Availability), 왕복 지연시간(Round-Trip Latency), 지연시간 변동(Latency Variation), 패킷 손실, 재연결 시간, 실제 업로드 및 다운로드 처리량, 핸드오버 동작(Handover Behavior), 통신 성능 저하 상태에서 완료된 임무 비율 등이 포함된다. 로봇 운영에서는 평균 네트워크 성능만 사용하는 것보다 최악 조건(Worst-Case)과 백분위 기반 측정(Percentile Measurement)이 더 유용한 경우가 많다.

시험 과정에서는 의도적으로 네트워크 장애(Network Failure)를 포함해야 한다. 로봇은 완전한 연결 단절, 높은 지연시간, 제한된 대역폭, 패킷 손실, 네트워크 전환, 서버 사용 불가, 지연된 메시지 전달 조건에서 평가되어야 한다. 이러한 시험을 통해 로컬 자율성이 안전하게 유지되고, 데이터가 보존되며, 오래된 명령이 거부되고, 복구 이후 플릿 상태가 다시 동기화되며, 운영자가 통신 상태를 명확하게 이해할 수 있는지를 검증할 수 있다.

따라서 농업 연결성(Agricultural Connectivity)은 영구적인 제어 의존성(Permanent Control Dependency)이 아니라 복원력 있는 서비스 계층(Resilient Service Layer)으로 설계되어야 한다. 4G와 5G 네트워크는 플릿 관리, 원격 감독, 분석, 데이터 교환의 범위를 확장하고 온보드 지능(Onboard Intelligence)은 즉각적인 자율성을 유지한다. 이러한 아키텍처를 사용하면 통신 품질이 변화하더라도 로봇의 기본적인 인지, 주행 또는 안전 기능이 사라지지 않는다.

농업 로봇 배치 규모가 확대될수록 연결성은 개별 기계를 집단 운영(Collective Operation)과 연결하는 정보 인프라(Information Infrastructure)가 된다. 잘 설계된 시스템은 4G, 5G, 로컬 네트워크(Local Networking), 엣지 컴퓨팅(Edge Computing), 버퍼링(Buffering), 동기화(Synchronization), 트래픽 우선순위 지정(Traffic Prioritization), 안전한 원격 서비스를 통합한다. 그 결과 실제 농업 환경에 존재하는 네트워크 제약에 대한 복원력을 유지하면서 농촌 지역 전반에서 생산적으로 운용할 수 있는 연결형 농업 로봇 아키텍처(Connected Agricultural Robot Architecture)를 구축할 수 있다.

##  

## 08.10. Autonomous Strawberry Harvesting Field Case

![](images/image10.png){width="7.268055555555556in" height="7.268055555555556in"}

An autonomous strawberry harvesting field deployment integrates mobile navigation, crop perception, maturity estimation, manipulation, fruit handling, mission management, and operational monitoring into one continuous agricultural workflow. Unlike laboratory demonstrations focused on a single successful pick, field operation must repeatedly locate harvestable fruit, position the robot, perform delicate harvesting, recover from failures, and maintain useful productivity over extended missions.

The harvesting mission begins with the definition of crop rows, accessible travel corridors, working positions, collection locations, charging points, and restricted areas. The mobile platform receives a sequence of harvesting zones rather than isolated manipulation targets. Navigation software moves the robot through the production area while maintaining sufficient clearance from plants, cultivation structures, workers, irrigation equipment, and other temporary obstacles.

When the robot reaches a harvesting position, perception sensors inspect the surrounding plants. RGB cameras, depth cameras, or stereo vision can detect individual strawberries and estimate their spatial locations. The perception pipeline must distinguish fruit from leaves, stems, flowers, support structures, containers, and background objects while remaining robust to illumination changes, shadows, overlapping fruit, and partial occlusion.

Detected fruit is classified according to harvest suitability. Color, appearance, size, surface condition, and other visual features can contribute to maturity estimation, but the system should preserve uncertainty rather than forcing every observation into a confident decision. Fruit can be categorized as harvestable, immature, damaged, overripe, occluded, or uncertain so that manipulation is attempted only when the expected benefit justifies the risk.

A harvestable strawberry must then be represented in the robot coordinate system. Camera calibration, depth estimation, and camera-to-manipulator transformations convert image observations into three-dimensional target positions. Localization error at this stage directly affects manipulation success because a small positional deviation can cause the end effector to miss the stem, contact neighboring fruit, or apply force to a fragile surface.

Occlusion is one of the dominant difficulties in real strawberry harvesting. Leaves, stems, and nearby fruit can hide part of the target or obstruct the manipulator approach. Instead of immediately rejecting every partially visible fruit, the robot can evaluate alternative viewpoints, move the camera, adjust the mobile base, or select another approach direction. Targets that remain too uncertain can be postponed for later inspection.

Harvest planning determines which visible fruit should be attempted and in what order. The robot can consider maturity, confidence, accessibility, estimated manipulation time, collision risk, and travel required between targets. Selecting the visually nearest fruit is not always optimal because another fruit may be easier to reach or may become inaccessible after surrounding vegetation is disturbed by an earlier harvesting action.

The manipulator then generates a collision-aware approach toward the selected target. Motion planning must consider the robot body, arm links, end effector, crop structures, neighboring fruit, and estimated vegetation geometry. Agricultural manipulation differs from rigid industrial assembly because many obstacles are deformable and imperfectly observed. Conservative planning reduces damage but must still allow practical access through dense plant structures.

The end effector performs the physical harvesting operation using the mechanism provided by the platform. Depending on the design, the fruit or stem may be grasped, cut, suctioned, supported, or detached through a controlled motion. Force, gripper position, motor current, vacuum state, or tactile feedback can be monitored so that the robot does not rely exclusively on an open-loop command for a delicate physical interaction.

Detachment should be treated as a monitored process rather than a single actuator event. Excessive resistance can indicate that the stem was not correctly engaged, while unexpectedly low resistance may indicate a missed target. The controller can modify motion, release the fruit, retry the approach, or terminate the attempt when sensor feedback indicates an abnormal condition. Retry limits prevent repeated actions from damaging the crop.

After the detachment motion, the robot must verify that harvesting actually succeeded. Visual confirmation, gripper state, force change, vacuum feedback, or other sensing can determine whether the strawberry is securely held and has been removed from the plant. Without this verification step, the software may record a successful harvest even though the fruit remains attached, was dropped, or was never acquired.

A successfully harvested strawberry must be transferred to a collection container without introducing unnecessary damage. Motion during transfer should limit impact, compression, and sudden acceleration. The system also tracks container capacity so that harvesting is suspended before storage becomes full. When necessary, the robot can move to an unloading location, exchange containers, or request logistical support before resuming the mission.

The mobile base and manipulator must operate as a coordinated system. The platform should stop at positions that maximize the reachable crop area while minimizing unnecessary repositioning. After accessible fruit around one working pose has been processed, the mission manager determines whether to move slightly along the row, reposition for another viewpoint, or continue to the next harvesting zone. This coordination strongly influences total cycle time.

Field operation inevitably includes failed attempts. A target may disappear from view, depth estimation may become unstable, the manipulator may encounter unexpected vegetation, or detachment may fail. Each failure should produce an explicit state and reason. Recovery logic can reacquire the target, re-estimate its position, choose another approach, retry within defined limits, postpone the fruit, or continue with another target.

The system should maintain persistent harvesting records rather than treating every detection as a new independent event. Target identity, maturity estimate, position, attempt count, failure reason, and final outcome can be associated across repeated observations. This reduces repeated attempts on known inaccessible fruit and prevents already harvested locations from being unnecessarily processed again when the robot revisits the same crop row.

Long-duration operation introduces resource-management requirements beyond individual harvesting actions. Battery energy, collection-container capacity, computing temperature, sensor health, communication status, and actuator condition must be monitored throughout the mission. The robot may schedule charging, unloading, cleaning, inspection, or maintenance actions so that short-term harvesting decisions do not compromise overall operational availability.

Connectivity can support remote monitoring and fleet-level coordination, but immediate harvesting should remain primarily edge autonomous. Perception, target selection, manipulation control, safety monitoring, and local recovery require predictable response times. Remote systems can receive progress information, images, faults, productivity statistics, and diagnostic data while the robot continues operating safely during temporary network degradation.

Operational logging is essential for evaluating a field case. Sensor observations, detections, maturity predictions, target coordinates, manipulator trajectories, force or gripper signals, navigation states, failure events, and harvesting outcomes should share synchronized timestamps. These records allow engineers to trace a failed pick through perception, localization, planning, control, and physical interaction rather than judging only the final result.

Performance evaluation must extend beyond simple harvesting success rate. Useful measures include fruit detection recall, maturity classification accuracy, three-dimensional localization error, successful detachment rate, fruit damage rate, drop rate, average harvesting cycle time, successful picks per hour, human intervention frequency, navigation availability, and the percentage of visible fruit that cannot be reached safely.

Field productivity should also be interpreted together with crop conditions. A robot may perform well when fruit is clearly visible but degrade when foliage becomes dense or fruit clusters overlap. Evaluation should therefore record occlusion level, crop geometry, illumination, maturity distribution, and other relevant conditions. Stratified results reveal which environmental factors limit performance and where engineering improvement provides the greatest value.

Human operators remain part of practical deployment even when harvesting is autonomous. Operators may define missions, resolve exceptional failures, replace containers, perform maintenance, and review uncertain cases. The objective is not merely to remove human participation but to reduce continuous manual harvesting effort while allowing a small number of people to supervise larger autonomous operations efficiently.

An autonomous strawberry harvesting field case therefore represents an end-to-end Physical AI system rather than an isolated vision or manipulation demonstration. Navigation determines where the robot can work, perception identifies harvest opportunities, reasoning selects appropriate targets, manipulation performs physical interaction, verification confirms outcomes, and mission management converts individual picks into sustained agricultural operation.

The decisive transition from prototype to useful agricultural system occurs when these components remain reliable across repeated cycles and changing field conditions. A successful deployment must tolerate imperfect perception, occlusion, variable fruit geometry, navigation disturbances, manipulation failures, resource limits, and communication changes while continuing to produce traceable harvesting results with acceptable productivity and crop damage.

자율 딸기 수확 현장 배치(Autonomous Strawberry Harvesting Field Deployment)는 이동형 주행(Mobile Navigation), 작물 인지(Crop Perception), 성숙도 추정(Maturity Estimation), 조작(Manipulation), 과실 취급(Fruit Handling), 임무 관리(Mission Management), 운영 모니터링(Operational Monitoring)을 하나의 연속적인 농업 작업 흐름으로 통합한다. 단일 수확 성공에 초점을 맞춘 실험실 시연과 달리, 현장 운영에서는 수확 가능한 과실을 반복적으로 탐지하고 로봇의 위치를 조정하며 섬세한 수확 작업을 수행하고 실패에서 복구하면서 장시간 동안 실질적인 생산성을 유지해야 한다.

수확 임무(Harvesting Mission)는 작물 열, 접근 가능한 이동 통로, 작업 위치, 수집 위치, 충전 지점, 제한 구역을 정의하는 것에서 시작된다. 이동 플랫폼(Mobile Platform)은 개별적인 조작 대상이 아니라 일련의 수확 구역(Harvesting Zone)을 전달받는다. 주행 소프트웨어는 식물, 재배 구조물, 작업자, 관개 장비 및 기타 임시 장애물로부터 충분한 여유 공간을 유지하면서 생산 구역을 통해 로봇을 이동시킨다.

로봇이 수확 위치에 도달하면 인지 센서(Perception Sensor)가 주변 식물을 검사한다. RGB 카메라, 깊이 카메라(Depth Camera) 또는 스테레오 비전(Stereo Vision)을 사용하여 개별 딸기를 감지하고 공간적 위치를 추정할 수 있다. 인지 파이프라인(Perception Pipeline)은 조명 변화, 그림자, 서로 겹친 과실, 부분적인 가림(Occlusion)에 강건하게 대응하면서 과실을 잎, 줄기, 꽃, 지지 구조물, 용기 및 배경 객체와 구분해야 한다.

감지된 과실은 수확 적합성(Harvest Suitability)에 따라 분류된다. 색상, 외관, 크기, 표면 상태 및 기타 시각적 특징을 성숙도 추정에 활용할 수 있지만 시스템은 모든 관측값을 강제로 확정적인 결과로 분류하지 않고 불확실성을 유지해야 한다. 과실을 수확 가능, 미성숙, 손상, 과숙, 가림 또는 불확실 상태로 분류하여 예상되는 이점이 위험보다 충분히 큰 경우에만 조작을 시도할 수 있다.

수확 가능한 딸기는 이후 로봇 좌표계(Robot Coordinate System)로 표현되어야 한다. 카메라 보정(Camera Calibration), 깊이 추정(Depth Estimation), 카메라-매니퓰레이터 변환(Camera-to-Manipulator Transformation)을 이용하여 영상 관측 결과를 3차원 목표 위치(Three-Dimensional Target Position)로 변환한다. 이 단계의 위치 오차는 작은 편차만으로도 엔드 이펙터(End Effector)가 줄기를 놓치거나 주변 과실과 접촉하거나 연약한 표면에 힘을 가할 수 있기 때문에 조작 성공률에 직접적인 영향을 준다.

가림(Occlusion)은 실제 딸기 수확에서 가장 중요한 어려움 중 하나이다. 잎, 줄기, 주변 과실이 목표의 일부를 가리거나 매니퓰레이터의 접근 경로를 방해할 수 있다. 로봇은 부분적으로 보이는 모든 과실을 즉시 제외하는 대신 대체 시점(Alternative Viewpoint)을 평가하고 카메라를 이동하거나 이동 베이스(Mobile Base)의 위치를 조정하거나 다른 접근 방향을 선택할 수 있다. 충분한 신뢰도를 확보할 수 없는 목표는 이후 다시 검사하도록 연기할 수 있다.

수확 계획(Harvest Planning)은 관측된 과실 가운데 어떤 대상을 어떤 순서로 수확할지를 결정한다. 로봇은 성숙도, 신뢰도, 접근 가능성, 예상 조작 시간, 충돌 위험, 목표 사이의 이동량을 고려할 수 있다. 시각적으로 가장 가까운 과실을 선택하는 것이 항상 최적인 것은 아니며, 다른 과실이 더 쉽게 접근 가능하거나 이전 수확 동작으로 주변 식생이 움직인 후 접근하기 어려워질 수도 있다.

이후 매니퓰레이터(Manipulator)는 선택된 목표를 향해 충돌 인식 접근 경로(Collision-Aware Approach)를 생성한다. 모션 계획(Motion Planning)은 로봇 차체, 로봇 팔 링크, 엔드 이펙터, 작물 구조물, 주변 과실, 추정된 식생 형상을 고려해야 한다. 농업 조작(Agricultural Manipulation)은 많은 장애물이 변형 가능하고 불완전하게 관측된다는 점에서 강체를 대상으로 하는 산업 조립과 다르다. 보수적인 경로 계획은 손상을 줄이면서도 밀집된 식물 구조 사이로 실질적인 접근이 가능하도록 해야 한다.

엔드 이펙터는 플랫폼에 적용된 메커니즘을 이용하여 실제 수확 동작을 수행한다. 설계에 따라 과실 또는 줄기를 파지(Grasping), 절단(Cutting), 흡착(Suction), 지지(Supporting)하거나 제어된 움직임을 통해 분리(Detachment)할 수 있다. 힘, 그리퍼 위치, 모터 전류, 진공 상태 또는 촉각 피드백(Tactile Feedback)을 모니터링하여 섬세한 물리적 상호작용을 단순한 개루프 명령(Open-Loop Command)에만 의존하지 않도록 할 수 있다.

분리(Detachment)는 하나의 액추에이터 이벤트가 아니라 모니터링되는 과정으로 처리해야 한다. 지나치게 높은 저항은 줄기가 올바르게 결합되지 않았음을 의미할 수 있으며 예상보다 낮은 저항은 목표를 놓쳤음을 의미할 수 있다. 센서 피드백이 비정상 상태를 나타내면 제어기는 움직임을 변경하거나 과실을 놓고 다시 접근하거나 수확 시도를 종료할 수 있다. 재시도 제한(Retry Limit)은 반복적인 동작으로 작물이 손상되는 것을 방지한다.

분리 동작 이후에는 로봇이 실제로 수확에 성공했는지를 검증해야 한다. 시각적 확인(Visual Confirmation), 그리퍼 상태, 힘 변화, 진공 피드백 또는 기타 센싱 정보를 이용하여 딸기가 안정적으로 파지되었고 식물에서 분리되었는지를 판단할 수 있다. 이러한 검증 단계가 없으면 과실이 여전히 식물에 붙어 있거나 떨어졌거나 처음부터 획득되지 않았음에도 소프트웨어가 수확 성공으로 기록할 수 있다.

성공적으로 수확된 딸기는 불필요한 손상을 발생시키지 않으면서 수집 용기(Collection Container)로 이송해야 한다. 이송 과정의 움직임은 충격, 압축, 급격한 가속을 제한해야 한다. 시스템은 수집 용기의 적재 용량도 추적하여 용기가 가득 차기 전에 수확을 중지한다. 필요한 경우 로봇은 하역 위치로 이동하거나 용기를 교환하거나 물류 지원을 요청한 후 임무를 다시 시작할 수 있다.

이동 베이스와 매니퓰레이터는 하나의 협조 시스템(Coordinated System)으로 동작해야 한다. 플랫폼은 불필요한 재배치를 최소화하면서 접근 가능한 작물 영역을 최대화할 수 있는 위치에서 정지해야 한다. 하나의 작업 자세에서 접근 가능한 과실을 처리한 후 임무 관리자(Mission Manager)는 작물 열을 따라 조금 이동할지, 다른 시점을 확보하기 위해 위치를 다시 조정할지 또는 다음 수확 구역으로 이동할지를 결정한다. 이러한 협조는 전체 작업 주기 시간(Total Cycle Time)에 큰 영향을 준다.

현장 운영(Field Operation)에서는 필연적으로 실패한 수확 시도가 발생한다. 목표가 시야에서 사라지거나 깊이 추정이 불안정해지거나 매니퓰레이터가 예상하지 못한 식생과 접촉하거나 분리에 실패할 수 있다. 각각의 실패는 명확한 상태와 원인으로 기록되어야 한다. 복구 로직(Recovery Logic)은 목표를 다시 획득하고 위치를 재추정하거나 다른 접근 경로를 선택하거나 정의된 횟수 내에서 재시도하거나 해당 과실을 연기하고 다른 목표로 진행할 수 있다.

시스템은 모든 감지 결과를 새로운 독립 이벤트로 처리하는 대신 지속적인 수확 기록(Persistent Harvesting Record)을 유지해야 한다. 반복 관측에 걸쳐 목표 식별자, 성숙도 추정값, 위치, 시도 횟수, 실패 원인, 최종 결과를 연결할 수 있다. 이를 통해 접근할 수 없는 것으로 확인된 과실에 대한 반복적인 시도를 줄이고 로봇이 동일한 작물 열을 다시 방문할 때 이미 수확된 위치를 불필요하게 다시 처리하는 것을 방지할 수 있다.

장시간 운영(Long-Duration Operation)에서는 개별 수확 동작 이외에도 자원 관리(Resource Management)가 필요하다. 배터리 에너지, 수집 용기 용량, 컴퓨팅 장치 온도, 센서 상태, 통신 상태, 액추에이터 상태를 임무 전체에 걸쳐 모니터링해야 한다. 로봇은 단기적인 수확 의사결정이 전체 운영 가용성(Operational Availability)을 저하시키지 않도록 충전, 하역, 세척, 검사 또는 유지보수 작업을 계획할 수 있다.

연결성(Connectivity)은 원격 모니터링(Remote Monitoring)과 플릿 수준 협조(Fleet-Level Coordination)를 지원할 수 있지만 즉각적인 수확 작업은 주로 엣지 자율성(Edge Autonomy)을 기반으로 유지되어야 한다. 인지, 목표 선택, 조작 제어, 안전 모니터링, 로컬 복구(Local Recovery)는 예측 가능한 응답시간을 필요로 한다. 원격 시스템은 로봇이 일시적인 네트워크 성능 저하 상황에서도 안전하게 작업을 계속하는 동안 진행 정보, 영상, 장애, 생산성 통계, 진단 데이터를 수신할 수 있다.

현장 사례(Field Case)를 평가하기 위해서는 운영 로그(Operational Logging)가 필수적이다. 센서 관측값, 객체 감지 결과, 성숙도 예측, 목표 좌표, 매니퓰레이터 궤적, 힘 또는 그리퍼 신호, 주행 상태, 실패 이벤트, 수확 결과가 동기화된 타임스탬프(Synchronized Timestamp)를 공유해야 한다. 이러한 기록을 통해 엔지니어는 최종 결과만 판단하는 것이 아니라 실패한 수확을 인지, 위치 추정, 계획, 제어, 물리적 상호작용 단계까지 추적할 수 있다.

성능 평가(Performance Evaluation)는 단순한 수확 성공률을 넘어 확장되어야 한다. 유용한 평가 지표에는 과실 감지 재현율(Fruit Detection Recall), 성숙도 분류 정확도, 3차원 위치 추정 오차, 성공적인 분리율, 과실 손상률, 낙하율, 평균 수확 작업 주기 시간(Average Harvesting Cycle Time), 시간당 성공 수확 개수, 인간 개입 빈도, 주행 가용성(Navigation Availability), 안전하게 접근할 수 없는 가시 과실의 비율 등이 포함된다.

현장 생산성(Field Productivity)은 작물 상태와 함께 해석해야 한다. 과실이 명확하게 보이는 환경에서는 로봇이 높은 성능을 보이지만 잎이 밀집되거나 과실 군집이 서로 겹치는 경우 성능이 저하될 수 있다. 따라서 평가 과정에서는 가림 수준(Occlusion Level), 작물 형상(Crop Geometry), 조명, 성숙도 분포 및 기타 관련 조건을 함께 기록해야 한다. 조건별로 구분된 결과(Stratified Result)를 이용하면 어떤 환경 요인이 성능을 제한하는지와 어느 부분의 공학적 개선이 가장 높은 가치를 제공하는지를 확인할 수 있다.

수확 작업이 자율화되더라도 실제 배치에서는 인간 운영자(Human Operator)가 시스템의 일부로 남는다. 운영자는 임무를 정의하고 예외적인 장애를 해결하며 수집 용기를 교체하고 유지보수를 수행하며 불확실한 사례를 검토할 수 있다. 목표는 단순히 인간의 참여를 제거하는 것이 아니라 지속적인 수작업 수확 노동을 줄이면서 소수의 운영자가 더 큰 규모의 자율 작업을 효율적으로 감독할 수 있도록 하는 것이다.

따라서 자율 딸기 수확 현장 사례(Autonomous Strawberry Harvesting Field Case)는 독립적인 비전 또는 조작 시연이 아니라 종단간 피지컬 AI 시스템(End-to-End Physical AI System)을 의미한다. 주행은 로봇이 작업할 위치를 결정하고, 인지는 수확 기회를 식별하며, 추론(Reasoning)은 적절한 목표를 선택하고, 조작은 물리적 상호작용을 수행하며, 검증(Verification)은 결과를 확인하고, 임무 관리는 개별 수확 동작을 지속 가능한 농업 운영으로 전환한다.

프로토타입(Prototype)에서 실용적인 농업 시스템으로 전환되는 결정적인 단계는 이러한 구성요소들이 반복적인 작업 주기와 변화하는 현장 조건에서도 신뢰성을 유지할 때 이루어진다. 성공적인 현장 배치(Successful Field Deployment)는 불완전한 인지, 가림, 다양한 과실 형상, 주행 교란, 조작 실패, 자원 한계, 통신 상태 변화를 견디면서도 허용 가능한 생산성과 작물 손상 수준을 유지하고 추적 가능한 수확 결과(Traceable Harvesting Result)를 지속적으로 생성할 수 있어야 한다.
