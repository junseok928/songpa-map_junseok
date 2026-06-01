# 🗺 송파구 토지이용 분석 시스템

가천대학교 스마트시티학과 국토 데이터분석 실습 (Lecture 6)

## 📌 개요

서울특별시 송파구의 토지이용 현황을 시각화·분석하는 웹 기반 시스템입니다.  
실제 공공데이터를 활용하여 필지 단위 건축물 주용도, 용도지역, 집계구별 인구·가구 현황을 표출합니다.

## 🔍 주요 기능

| 기능 | 설명 |
|------|------|
| **주용도 레이어** | 건축물 주용도별 색상 구분 표시 (15개 분류) |
| **용도지역 레이어** | 법정 용도지역별 색상 표시 |
| **인구밀도 레이어** | 행정동별 인구 규모 원형 표시 |
| **통계 개요** | 전체 필지수·건물수·인구·가구 현황 및 파이차트 |
| **건축물 용도 테이블** | 용도별 필지수·면적·비율 테이블 |
| **인구 현황 테이블** | 행정동별 인구·가구수 상세 |

## 📂 데이터 출처

| 데이터 | 출처 | 기준 |
|--------|------|------|
| 건축물대장 | [건축HUB](https://www.hub.go.kr) | 2026.06 |
| 용도지역 | [Vworld](https://www.vworld.kr) | 2026.05 |
| 집계구 인구·가구 | [SGIS 포털](https://sgis.mods.go.kr) | 2024년 기준 |
| 베이스맵 | Vworld WMTS | - |

## 🚀 실행 방법

### GitHub Pages 배포
1. 이 레포지토리를 Fork 또는 Clone
2. GitHub Settings → Pages → Source: `main` 브랜치 / `root` 폴더
3. `https://{username}.github.io/{repo-name}` 접속

### 로컬 실행
```bash
# Python 3
python -m http.server 8080

# Node.js
npx serve .
```
> ⚠️ `index.html`을 브라우저에서 직접 열면 CORS 오류가 발생합니다. 반드시 로컬 서버를 사용하세요.

## 🗂 프로젝트 구조

```
songpa-web/
├── index.html          # 메인 웹 페이지
├── data/
│   ├── parcels.json        # 필지별 건축물 정보 (20,870건)
│   ├── usage_stats.json    # 주용도별 통계
│   ├── dong_stats.json     # 법정동별 통계
│   ├── population.json     # 집계구별 인구·가구
│   └── dong_population.json # 행정동별 인구·가구 합계
└── README.md
```

## 🛠 사용 기술

- **지도**: [Leaflet.js](https://leafletjs.com/) 1.9.4
- **차트**: [Chart.js](https://www.chartjs.org/) 4.4.0
- **베이스맵**: Vworld WMTS
- **데이터 처리**: Python (Pandas, GeoPandas)
- **언어**: HTML / CSS / Vanilla JavaScript (프레임워크 없음)

## 📊 데이터 가공 과정

```
건축물대장 CSV (24,211건)
  → 필지별 대표 주용도 추출 (법정동+번+지 기준)
  → 20,870개 필지 데이터 생성

SGIS 집계구 통계 CSV
  → 송파구(11240) 필터링
  → 1,278개 집계구 × 인구·가구 조인
  → 행정동별 합계 집계

용도지역 Shapefile
  → GeoPandas로 속성 추출
```

---

*가천대학교 스마트시티학과 · 국토 데이터분석 실습 과제*
