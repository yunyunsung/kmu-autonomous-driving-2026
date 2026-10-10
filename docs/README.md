# 문서 안내

다음 대회를 준비하는 팀이 이 순서로 읽으면 됩니다.

| 순서 | 문서 | 이런 걸 알 수 있음 |
|---|---|---|
| 1 | [01-competition.md](01-competition.md) | 대회 규정, 벌점, 실격 조건, 트랙 치수 |
| 2 | [02-system-architecture.md](02-system-architecture.md) | 노드 구성, 20Hz 루프, 이중 상태머신 |
| 3 | [03-perception.md](03-perception.md) | 차선(da/ll), YOLO 3종, 라이다 트리거, 파인튜닝 |
| 4 | [04-steering-control.md](04-steering-control.md) | Pure Pursuit, 속도 계획, 튜닝 시뮬레이터와 최종값 |
| 5 | [05-missions.md](05-missions.md) | 신호등, 라바콘, 장애물, 지름길 처리와 변천 |
| 6 | [06-tensorrt-deployment.md](06-tensorrt-deployment.md) | Jetson 이식, TensorRT 함정 |
| 7 | [07-hardware-and-dev-env.md](07-hardware-and-dev-env.md) | 기동 체크리스트, 센서 함정, 원격 접속, 빌드 문제 |
| 8 | [08-calibration.md](08-calibration.md) | 실측값과 설계값, 재측정 방법 |
| 9 | [09-timeline.md](09-timeline.md) | 7월~8월 날짜별 진행 |
| 10 | [10-lessons-learned.md](10-lessons-learned.md) | **설계 일지를 주제별로 재구성한 시행착오** |
| 11 | [11-camera-distance.md](11-camera-distance.md) | YOLO 박스 크기 거리 게이트와 단안 3D 검출 논문의 연결 |
| - | [archive/](archive/) | 압축 전 설계 일지 원문 (2,924줄 / 3,713줄) |

## 시간이 없다면

- 대회 2주 전이라면: **07의 기동 체크리스트**와 **10의 4번(조용한 실패)** 만이라도.
- 조향을 만진다면: 04를 읽고, `config.py`의 `PP_TUNE_ACTIVE_PRESET`부터 확인하세요.
- 새 모델을 Jetson에 올린다면: 06의 NMS와 엔진 캐시 이야기를 먼저.

## 문서 속 값에 대해

모든 수치는 본선 코드(`src/`) 기준입니다. 설계 일지 원문(`archive/`)의 값은 **당시** 값이라 다를 수 있습니다.
값마다 실측인지, 설계값인지, 실차 미검증인지 표시하려고 했습니다. 표시가 없는 튜닝값은 `config.py`의 주석을
확인하세요.
