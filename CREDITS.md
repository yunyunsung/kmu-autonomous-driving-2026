# CREDITS

이 저장소는 **제9회 국민대학교 자율주행 경진대회** 본선에 출전한 팀의 작업을, 팀원 중 한 명인
최윤성이 개인 포트폴리오 및 인수인계 목적으로 다시 정리한 것입니다.

## 원본 저장소

- 팀 실차 배포 저장소: [mastic-choi/KURiver-KMU-auto-contest](https://github.com/mastic-choi/KURiver-KMU-auto-contest)
- 차선/주행가능영역 파인튜닝: [mastic-choi/TwinLiteNet-KMU-finetune](https://github.com/mastic-choi/TwinLiteNet-KMU-finetune)
- 방해차량·신호등 YOLO 파인튜닝: [mastic-choi/yolo-V8-KMU-xycar](https://github.com/mastic-choi/yolo-V8-KMU-xycar)

## 무엇을 가져왔나

| 경로 | 출처 | 비고 |
|---|---|---|
| `src/` | 원본 저장소 `a0ad971` (2026-08-31) | 코드는 수정하지 않은 스냅샷 |
| `media/` | 원본 저장소 `docs/` | 완주 주행 GIF, 대회 포스터 |
| `docs/archive/` | 원본 저장소 git 히스토리 | 압축 전 내부 설계 일지 원문 |
| `docs/*.md`, `README.md` | 이 저장소에서 새로 작성 | 설계 일지·커밋 기록을 재구성 |

`src/`의 스냅샷은 대회 이후 주석 정리와 미사용 모듈 삭제만 거친 버전입니다.
본선 당일(2026-08-25) 마지막 커밋 `6742cd7`과 남아 있는 모든 `.py` 파일의 AST(주석·docstring 제외)를
비교해 **주행 로직이 동일함**을 확인했습니다.

## 팀

KURiver 팀원들이 함께 개발했습니다.
실차 한 대를 여러 명이 공유하며 작업해 커밋 계정(`xycar` 공용 계정 포함)이 실제 작업자와 일치하지
않는 경우가 많습니다. 그래서 이 저장소는 커밋 수로 기여도를 나누지 않습니다.

## 라이선스

원본 저장소에 라이선스가 명시되어 있지 않아, 이 저장소의 코드도 별도 라이선스 없이 원작자들의 권리가
유지됩니다. 재사용이 필요하면 원본 저장소 팀원들에게 먼저 문의해 주세요.
`src/xycar_device/xycar_imu`는 자체 `LICENSE` 파일을 따르는 벤더 드라이버입니다.
