cj 대한통운 미래기술챌린지 2025 물류센터 오더 피킹 프로세스 최적화 모델
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
<과제 설명>

본 과제는 물류센터 내 오더 피킹(Order Picking) 프로세스를 최적화하는 알고리즘 개발을 목표로 합니다.

참가자는 아래 세 가지 대표적인 조합 최적화 문제(Combinatorial Optimization Problem)를 해결해야 하며, 문제별로 독립적으로 또는 통합적으로 접근할 수 있습니다.

저장 위치 할당 문제 (Storage Location Assignment Problem, SLAP)

물류센터 내 제품(SKU)들을 어떤 위치(Rack, Shelf 등)에 배치할지 결정하는 문제입니다.

주문 배치 및 시퀀싱 문제 (Order Batching and Sequencing Problem, OBSP)

여러 고객 주문(Order)를 적절히 묶어(Batching) 처리하고, 그 수행 순서(Sequencing)을 결정하는 문제입니다.

피커 라우팅 문제 (Picker Routing Problem, PRP)

하나의 피커(Picker) 또는 피킹카트가 할당된 주문을 가장 효율적으로 처리하기 위한 경로(Routing)을 결정하는 문제입니다.

세 문제는 독립적으로 해결할 수도 있으며, 통합된 하나의 모델로 해결할 수도 있습니다.

Rule-based: 규칙 기반 접근법 (ex: SKU빈도별 정렬, 고빈도 SKU 우선 카트 할당 등)
Mixed-Integer Programming (MIP): 수학적 최적화 모델을 통한 해법
Heuristic Algorithm: 문제를 빠르게 근사적으로 해결하는 기법
Meta-heuristic Algorithm: 유전 알고리즘(GA), 시뮬레이티드 어닐링(SA), GRASP 등 고급 휴리스틱 기법
Hybrid: 위 방법들을 혼합하여 최적화 성능 강화
제출된 솔루션은 대표적인 이산 사건 시뮬레이션(Discrete-event Simulation , DES) 모델을 통해 정량적 지표로 평가됩니다.

평가 지표는 총 작업완료시간 Minimize 입니다.

※ 실제 물류센터 운영과 유사한 시나리오 및 다양한 난이도의 테스트 케이스가 제공됩니다.

문제 설명
Storage Location Assignment Problem (SLAP)

SLAP는 SKU(Stock Keeping Unit)를 창고 내 특정 위치에 효율적으로 할당하여, 작업자의 총 이동 거리(Picking Travel Distance)를 최소화하고, 피킹 효율성(Picking Productivity)을 극대화하는 문제입니다.

주요 고려 사항

고빈도 SKU 우선 배치
- 주문 빈도가 높은 SKU를 입출고 지점(I/O Depot) 가까운 위치에 배치하여 이동 거리를 줄입니다.
SKU 간 연관성 고려
- 동시 주문 가능성이 높은 SKU들(Co-picking Probability가 높은 SKU)을 서로 인접한 위치에 배치하여 한 번에 여러 SKU를 효율적으로 수집할 수 있도록 합니다.

Order Batching and Sequencing Problem (OBSP)

OBSP는 다수의 고객 주문(Order)을 적절히 묶어(Batching) 하여 처리하고, 각 배치(Batch)의 작업 순서(Sequencing)를 결정함으로써 작업자의 총 이동 거리 및 작업 시간을 최소화하고 피킹 라인 내 병목 현상(Blocking)을 방지하는 문제입니다.

주요 고려 사항

주문 그룹화 (Batching)
- 주문들을 어떻게 그룹으로 묶을지 결정합니다.
- 목표: 한 번의 작업(Picking Trip) 동안 효율적으로 많은 SKU를 수집하고 이동 거리를 줄입니다.
배치 순서 결정 (Sequencing)
- 생성된 각 배치들의 피킹 순서를 결정합니다.
- 목표: 특정 통로(Aisle)에서의 혼잡도(Congestion) 최소화 및 Blocking 방지.

Picker Routing Problem (PRP)

PRP는 하나의 배치로 그룹화된 주문(SKU 리스트)에 대해피커(Picker)의 이동 경로(Routing)와 방문 순서(Sequence) 를 최적화하여, 총 이동 거리 또는 총 피킹 시간을 최소화하는 문제입니다.

주요 고려 사항

이동 경로 최적화
- 피커가 창고 내 위치한 여러 Rack들을 어떤 순서로 방문할지 결정합니다.
- 목표: 전체 이동 거리(또는 이동 시간)를 최소화.
창고 레이아웃 반영
- 창고의 통로(Aisle), 랙(Rack) 구조, 일방통행(One-way) 통로 등을 고려해야 할 수 있습니다.

Layout

제공 레이아웃과 실제 평가 레이아웃 차이

- 참가자에게 제공되는 레이아웃은 실제 평가에 사용되는 레이아웃과 규모 및 구조가 다릅니다.
- 제공 레이아웃은 상대적으로 소규모로, 참가자가 문제를 이해하고 알고리즘을 개발하는 데 참고용으로 활용할 수 있습니다.
- 평가 시에는 보다 대규모이고 복잡한 레이아웃이 사용될 예정입니다.

O/D Matrix (Origin/Destination Matrix) 정보

참가자는 레이아웃을 직접 시각화 하지 않고도 O/D Matrix를 통해 공간 구조 및 거리 정보를 추정해야 합니다.
O/D Matrix의 정의
- 시뮬레이션 모델 내 Rack 객체들 간 모든 조합에 대해 측정한 이동거리(Distance)를 저장한 n x n 크기의 대칭행렬(Symmetric Matrix)입니다.
- 각 행(Row)과 열(Column)은 Rack의 이름을 나타냅니다 (Start, end = I/O).
- 각 셀의 값(Value)은 두 Rack 간 최단 이동 거리(예: 미터 단위)를 의미합니다.

실제 평가용 레이아웃은 더 큰 규모이며, 이동 거리 패턴(예: 특정 존 간 긴 거리, 좁은 통로 등)이 제공 레이아웃과 다를 수 있습니다.
따라서 일반화 가능한 알고리즘을 설계하는 것이 매우 중요합니다.

검증용 시뮬레이션 모델은 SIEMENS의 Plant Simulation를 통해 개발되었습니다.

평가용 데이터는 제공된 입력 데이터보다 규모가 더 큽니다(주문수↑, SKU수↑, 물류센터 크기↑).

최적화 모델은 평가 시스템에서 Time Limit 300초 안에 현재까지 도출된 가장 좋은 해(Current Best Solution)를 반환할 수 있도록 설계되어야 합니다.

참가자들은 개발한 알고리즘 내 main()함수에서 InputData, OD_Matrix, Parameter를 arguments 받을 수 있도록 구현이 꼭 필요하며, 제공된 Output 형태로 다시 Retuen하여야 합니다.

def main(INPUT: pd.DataFrame, PARAMETER: pd.DataFrame, OD_MATRIX: pd.DataFrame) -> pd.DataFrame:
soution = Solver(INPUT, PARAMETER, OD_MATRIX)
return soution

시뮬레이션 모델은 작업 시간이 확률적(Stochastic)으로 변하는 환경입니다.

최적화 모델에서 이론적 최적해(Optimal Solution)가 나오더라도, 시뮬레이션 모델 내의 확률적 환경에서 항상 최적성을 보장하지 않습니다.

즉, 불확실성(Uncertainty)이 존재하는 환경에서도 좋은 성능을 유지할 수 있는지 평가됩니다.

각 제출된 솔루션은 총 30회의 시뮬레이션 반복 실행 후 평균값으로 성능을 평가합니다.

모든 참가자에게는 매 실행마다 동일한 랜덤 시드(Random Seed)가 적용됩니다.

참가자의 목표는 총 소요시간(Completion Time)을 최소화(Minimize)하는 것입니다.

Score = Completion Time

제출파일
(과제명) 물류센터 오더 피킹 프로세스 최적화 모델
솔루션은 Python 3.13으로 개발하는 것을 권장합니다. (해당 과제 평가 시스템은 3.13.2 64bit)

제출물에는 반드시 소스 코드(.py)와 함께 사용된 라이브러리를 명시한 requirements.txt 파일 포함되어야 합니다.

(Gurobi, CPLEX와 같은 상용 라이선스가 필요한 Solver 사용은 제한)

평가시 Solver.py 실행하면 평가 주문 데이터, 평가용 파라미터, 평가용 OD Matrix를 입력으로 읽어,결과 파일을 지정 포맷에 맞춰 Return해야 합니다.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

