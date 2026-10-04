# src — 본선 코드 스냅샷

팀 저장소 [`KURiver-KMU-auto-contest`](https://github.com/mastic-choi/KURiver-KMU-auto-contest)
`a0ad971` 시점의 코드를 수정 없이 옮긴 것입니다. 주행 로직은 본선 당일(2026-08-25) 코드와 동일합니다
([CREDITS](../CREDITS.md) 참고).

| 패키지 | 내용 |
|---|---|
| `track_drive/` | 메인 ROS2 노드. 인지·상태머신·제어를 한 노드에서 처리 |
| `yolo_ros/` | 코드 없음. YOLO 가중치 보관 폴더(`cone_best_n.onnx`만 포함) |
| `xycar_device/` | 벤더 IMU 드라이버(`xycar_imu`) |

## 빠른 길잡이

| 보고 싶은 것 | 파일 |
|---|---|
| 20Hz 제어 루프, 상태머신 | `track_drive/track_drive/track_drive.py` |
| 모든 튜닝값 | `track_drive/track_drive/config.py` |
| TwinLiteNet+ 추론, da/ll 경로 생성 | `track_drive/track_drive/perception/dl_lane.py` |
| Pure Pursuit | `track_drive/track_drive/controller/pure_pursuit.py` |
| 조향 튜닝 시뮬레이터 | `track_drive/track_drive/pp_tune_gridsearch.py` |
| YOLO 검출기 3종 | `track_drive/track_drive/perception/yolo_*.py` |
| 속도 실측 도구 | `track_drive/track_drive/measure_speed_calibration.py` |

## 실행 전 준비

차선 인식과 방해차량·신호등 가중치는 용량 문제로 포함되어 있지 않습니다.
아래 경로에 받아두어야 합니다.

```
track_drive/track_drive/models/twinlitenetplus_kmu_v1.2.0.onnx (+ .onnx.data)
  ← TwinLiteNet-KMU-finetune v1.2.0
yolo_ros/signal_state_best_n.onnx    ← yolo-V8-KMU-xycar signal_state v1.2.0
yolo_ros/target_vehicle_best.onnx    ← yolo-V8-KMU-xycar target_vehicle v1.2.0
```

```bash
# ~/xycar_ws/src/ 아래에 track_drive, xycar_device, yolo_ros 배치
colcon build --packages-select track_drive xycar_imu
source install/setup.bash
ros2 launch track_drive track_drive.launch.py
```

모터는 ROS2만으로 움직이지 않습니다. Docker(ROS1) 컨테이너와 `ros1_bridge`가 함께 떠 있어야 합니다.
전체 환경 구성은 [`docs/07-hardware-and-dev-env.md`](../docs/07-hardware-and-dev-env.md)를 참고하세요.

`track_drive/track_drive/` 안의 `*_작업기록.md`, `*_proposal.md` 등은 대회 기간에 팀원들이 남긴 작업
메모로, 원본 그대로 두었습니다.
