# 수원시 도로 위험도 예측 대시보드
### Suwon Road Risk Prediction Dashboard

> XGBoost 기반 사고 예측 모델과 인터랙티브 지도 시각화를 결합한 오픈소스 교통안전 분석 도구

![License: MIT](https://img.shields.io/badge/License-MIT-purple.svg)
![HTML](https://img.shields.io/badge/HTML-100%25-orange)
![Leaflet](https://img.shields.io/badge/Leaflet-1.9.4-green)

---

## Overview

수원시 전체 도로 네트워크를 대상으로 **XGBoost 모델이 예측한 구간별 사고 위험도**를 인터랙티브 지도 위에 시각화합니다. 교통 계획가, 도로 안전 연구자, 지자체 담당자가 데이터 기반 의사결정을 내릴 수 있도록 설계되었습니다.

한국에서 공개된 도로 위험도 시각화 오픈소스 도구는 극히 드물며, 이 프로젝트는 그 공백을 채우기 위해 제작되었습니다.

---

## Features

- **5단계 위험도 시각화** — 예측 사고 건수 기반 보라색 그라데이션 (매우낮음 ~ 매우높음)
- **실측 vs 예측 비교** — 도로별 실제 사고 건수와 XGBoost 예측값 대조
- **도로 상세 정보** — 차로수, 제한속도, 길이, 도로 종류, 일 교통량
- **주변 시설 정보** — 버스정류장·횡단보도까지의 거리
- **행정구 필터 + 도로명 검색** — 수원시 8개 행정구 단위 필터링
- **KPI 대시보드** — 위험도 분포 도넛 차트, 상위 10개 위험 도로 목록
- **모바일 반응형** — 데스크탑 사이드바 / 모바일 바텀시트 자동 전환
- **다크 테마 + 글래스모피즘 UI**

---

## Demo

브라우저에서 `dashboard.html`을 열거나, GitHub Pages로 바로 확인:

```
[GitHub Pages 링크 추가 예정]
```

---

## Tech Stack

| 분류 | 기술 |
|------|------|
| 지도 | Leaflet.js 1.9.4 |
| 차트 | Chart.js |
| ML 모델 | XGBoost (Python, 별도 학습) |
| 공간 데이터 | GeoJSON (WGS84, 수원시 도로망) |
| 스타일 | Vanilla CSS (다크 테마, CSS Custom Properties) |
| 런타임 | 순수 Vanilla JS — 프레임워크 없음, 의존성 최소화 |

---

## Data

- `suwon_wgs84.geojson` — 수원시 도로 구간 공간 데이터 (WGS84 좌표계)
  - 포함 속성: 도로명, 행정구, 차로수, 제한속도, 일교통량, 예측/실측 사고건수, 주변시설 거리 등

---

## Risk Classification

| 등급 | 예측 사고 건수 | 색상 |
|------|--------------|------|
| 매우낮음 | 0 ~ 2 | `#3d1a6e` |
| 낮음 | 2 ~ 5 | `#6d2fcf` |
| 중간 | 5 ~ 10 | `#9d5cf6` |
| 높음 | 10 ~ 15 | `#c99cf2` |
| 매우높음 | 15+ | `#ecdeff` |

---

## Getting Started

별도 설치 필요 없음. 정적 HTML 파일입니다.

```bash
git clone https://github.com/dnwls012233-cpu/suwon-risk-dashboard.git
cd suwon-risk-dashboard
# dashboard.html을 브라우저로 열기
open dashboard.html
```

---

## Roadmap

- [ ] GitHub Pages 배포
- [ ] VDS 실시간 교통량 연동
- [ ] LLM 기반 자연어 도로 위험도 질의 (OpenAI API 활용 예정)
- [ ] 타 도시 확장 (수원 → 전국)
- [ ] SUMO 시뮬레이션 출력 연동

---

## License

MIT License

---
