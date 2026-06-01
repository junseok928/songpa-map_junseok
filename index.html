<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>송파구 데이터 뷰어</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;600;700&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"/>
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
<script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.0/dist/chart.umd.min.js"></script>
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --bg: #1a1a2e;
  --panel: #16213e;
  --panel2: #0f3460;
  --border: rgba(255,255,255,0.08);
  --border2: rgba(255,255,255,0.14);
  --text: #e2e8f0;
  --text2: #94a3b8;
  --text3: #64748b;
  --accent: #4fc3f7;
  --accent2: #7c3aed;
  --green: #34d399;
  --yellow: #fbbf24;

  --c-apt:   #FF8C00;
  --c-house: #32CD32;
  --c-comm1: #00BFFF;
  --c-comm2: #9370DB;
  --c-office:#FF1493;
  --c-edu:   #00CED1;
  --c-welfare:#FF6347;
  --c-retail: #DC143C;
  --c-lodge:  #DA70D6;
  --c-med:    #00FF7F;
  --c-reli:   #FFD700;
  --c-sport:  #40E0D0;
  --c-auto:   #708090;
  --c-cult:   #FF4500;
  --c-etc:    #556B2F;
  --c-fac:    #8B4513;
  --c-factory:#A9A9A9;
  --c-hazard: #B22222;
  --c-animal: #6B8E23;
  --c-waste:  #808000;
}

body {
  font-family: 'Noto Sans KR', sans-serif;
  background: var(--bg);
  color: var(--text);
  height: 100vh;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

/* ── MAP FULL ── */
#map {
  position: fixed;
  inset: 0;
  z-index: 0;
}

/* ── LEFT PANEL ── */
#leftPanel {
  position: fixed;
  top: 12px;
  left: 12px;
  width: 220px;
  background: rgba(22,33,62,0.92);
  backdrop-filter: blur(12px);
  border: 1px solid var(--border2);
  border-radius: 12px;
  z-index: 1000;
  overflow: hidden;
  box-shadow: 0 8px 32px rgba(0,0,0,0.5);
}

.lp-header {
  padding: 12px 14px 10px;
  border-bottom: 1px solid var(--border);
}
.lp-title {
  font-size: 14px;
  font-weight: 700;
  color: var(--text);
  margin-bottom: 4px;
}
.lp-meta {
  font-size: 10.5px;
  color: var(--text3);
  font-family: 'DM Mono', monospace;
}

.lp-section {
  padding: 10px 14px;
  border-bottom: 1px solid var(--border);
}
.lp-section:last-child { border-bottom: none; }

.lp-check-row {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 3px 0;
  cursor: pointer;
  font-size: 12.5px;
  color: var(--text2);
  user-select: none;
  transition: color .15s;
}
.lp-check-row:hover { color: var(--text); }
.lp-check-row input[type="checkbox"] {
  width: 13px;
  height: 13px;
  accent-color: var(--accent);
  cursor: pointer;
}
.lp-check-row.active { color: var(--text); }

/* 필지 레이어 드롭다운 */
.layer-selector {
  margin-top: 6px;
  padding: 5px 10px;
  background: rgba(255,255,255,0.07);
  border: 1px solid var(--border2);
  border-radius: 6px;
  font-size: 12px;
  color: var(--text);
  width: 100%;
  cursor: pointer;
  appearance: none;
  -webkit-appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='10' height='6'%3E%3Cpath d='M0 0l5 6 5-6z' fill='%2394a3b8'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 10px center;
}
.layer-selector option { background: #16213e; }

/* 투명도 슬라이더 */
.opacity-row {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-top: 6px;
  font-size: 11px;
  color: var(--text3);
}
.opacity-row input[type="range"] {
  flex: 1;
  height: 3px;
  accent-color: var(--accent);
  cursor: pointer;
}
.opacity-val {
  font-family: 'DM Mono', monospace;
  font-size: 11px;
  color: var(--text2);
  width: 30px;
  text-align: right;
}

/* 범례 */
.legend-wrap {
  max-height: 200px;
  overflow-y: auto;
  padding: 8px 14px;
}
.legend-wrap::-webkit-scrollbar { width: 3px; }
.legend-wrap::-webkit-scrollbar-thumb { background: var(--border2); border-radius: 2px; }

.legend-row {
  display: flex;
  align-items: center;
  gap: 7px;
  padding: 2.5px 0;
  cursor: pointer;
  font-size: 11.5px;
  color: var(--text2);
  user-select: none;
  transition: opacity .15s;
}
.legend-row.hidden { opacity: 0.3; }
.legend-row:hover { color: var(--text); }
.legend-dot {
  width: 10px;
  height: 10px;
  border-radius: 2px;
  flex-shrink: 0;
}
.legend-name { flex: 1; }
.legend-cnt {
  font-family: 'DM Mono', monospace;
  font-size: 10.5px;
  color: var(--text3);
}

/* ── RIGHT PANEL ── */
#rightPanel {
  position: fixed;
  top: 12px;
  right: 12px;
  width: 360px;
  background: rgba(22,33,62,0.95);
  backdrop-filter: blur(12px);
  border: 1px solid var(--border2);
  border-radius: 12px;
  z-index: 1000;
  overflow: hidden;
  box-shadow: 0 8px 32px rgba(0,0,0,0.5);
  display: flex;
  flex-direction: column;
  max-height: calc(100vh - 24px);
}

.rp-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px 14px 0;
  flex-shrink: 0;
}
.rp-title {
  font-size: 14px;
  font-weight: 700;
}
.rp-close {
  width: 20px;
  height: 20px;
  background: rgba(255,255,255,0.1);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  font-size: 11px;
  color: var(--text2);
  transition: background .15s;
}
.rp-close:hover { background: rgba(255,255,255,0.2); }

/* 상단 탭 */
.rp-tabs {
  display: flex;
  padding: 8px 14px 0;
  gap: 4px;
  flex-shrink: 0;
}
.rp-tab {
  padding: 5px 10px;
  border-radius: 6px;
  font-size: 11.5px;
  font-weight: 500;
  cursor: pointer;
  color: var(--text3);
  transition: all .2s;
  white-space: nowrap;
}
.rp-tab.active {
  background: rgba(79,195,247,0.15);
  color: var(--accent);
}
.rp-tab:hover:not(.active) {
  background: rgba(255,255,255,0.06);
  color: var(--text2);
}

/* 스크롤 영역 */
.rp-body {
  flex: 1;
  overflow-y: auto;
  padding: 12px 14px 14px;
  min-height: 0;
}
.rp-body::-webkit-scrollbar { width: 4px; }
.rp-body::-webkit-scrollbar-thumb { background: var(--border2); border-radius: 2px; }

.rp-pane { display: none; }
.rp-pane.active { display: block; }

/* 도넛 + 요약 */
.donut-wrap {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  height: 160px;
  margin-bottom: 8px;
}
.donut-center {
  position: absolute;
  text-align: center;
  pointer-events: none;
}
.donut-center-label {
  font-size: 11px;
  color: var(--text3);
  margin-bottom: 2px;
}
.donut-center-val {
  font-size: 16px;
  font-weight: 700;
  color: var(--text);
}

.summary-row {
  display: flex;
  gap: 8px;
  margin-bottom: 12px;
}
.summary-box {
  flex: 1;
  background: rgba(255,255,255,0.04);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 10px 10px 8px;
  text-align: center;
}
.summary-box-val {
  font-size: 18px;
  font-weight: 700;
  font-family: 'DM Mono', monospace;
  color: var(--text);
  line-height: 1.1;
}
.summary-box-val.accent { color: var(--accent); }
.summary-box-sub {
  font-size: 10px;
  color: var(--text3);
  margin-top: 3px;
}

/* 상세 테이블 */
.detail-table {
  width: 100%;
  border-collapse: collapse;
  font-size: 11.5px;
}
.detail-table thead tr {
  border-bottom: 1px solid var(--border2);
}
.detail-table th {
  padding: 5px 4px;
  color: var(--text3);
  font-size: 10.5px;
  font-weight: 500;
  text-align: left;
  white-space: nowrap;
}
.detail-table th:not(:first-child) { text-align: right; }
.detail-table td {
  padding: 4px 4px;
  border-bottom: 1px solid rgba(255,255,255,0.04);
  color: var(--text);
  vertical-align: middle;
}
.detail-table td:not(:first-child) {
  text-align: right;
  font-family: 'DM Mono', monospace;
  font-size: 11px;
  color: var(--text2);
}
.detail-table tr:last-child td { border-bottom: none; }
.detail-table tbody tr:hover td { background: rgba(255,255,255,0.03); }

.td-color-dot {
  display: inline-block;
  width: 8px;
  height: 8px;
  border-radius: 2px;
  margin-right: 5px;
  vertical-align: middle;
  flex-shrink: 0;
}

/* 인구 섹션 */
.pop-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 8px;
  margin-bottom: 12px;
}
.pop-card {
  background: rgba(255,255,255,0.04);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 10px 12px;
}
.pop-card-lbl { font-size: 10px; color: var(--text3); margin-bottom: 4px; }
.pop-card-val {
  font-size: 22px;
  font-weight: 700;
  font-family: 'DM Mono', monospace;
  color: var(--green);
  line-height: 1;
}
.pop-card-val.blue { color: var(--accent); }

.sec-title {
  font-size: 11px;
  font-weight: 600;
  color: var(--text3);
  text-transform: uppercase;
  letter-spacing: .5px;
  margin: 12px 0 7px;
}
.sec-title:first-child { margin-top: 0; }

/* 섹션 divider */
.divider {
  border: none;
  border-top: 1px solid var(--border);
  margin: 10px 0;
}

/* Loading */
#loadingOverlay {
  position: fixed;
  inset: 0;
  background: #1a1a2e;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  gap: 16px;
}
.loading-spinner {
  width: 40px;
  height: 40px;
  border: 3px solid rgba(79,195,247,0.2);
  border-top-color: var(--accent);
  border-radius: 50%;
  animation: spin 1s linear infinite;
}
@keyframes spin { to { transform: rotate(360deg); } }
.loading-msg { font-size: 13px; color: var(--text2); }

/* Leaflet */
.leaflet-container { background: #0a0f1e !important; }
.leaflet-control-zoom {
  border: none !important;
  box-shadow: none !important;
}
.leaflet-control-zoom a {
  background: rgba(22,33,62,0.9) !important;
  border: 1px solid var(--border2) !important;
  color: var(--text) !important;
  width: 30px !important;
  height: 30px !important;
  line-height: 28px !important;
  font-size: 16px !important;
  border-radius: 6px !important;
  margin-bottom: 3px !important;
  display: block !important;
}
.leaflet-control-zoom a:hover {
  background: rgba(79,195,247,0.15) !important;
  color: var(--accent) !important;
}
.leaflet-control-zoom { border-radius: 8px !important; }
.leaflet-control-attribution { display: none !important; }
.leaflet-control-zoom { bottom: 40px !important; right: 380px !important; }

/* Tooltip hover */
.leaflet-tooltip {
  background: rgba(22,33,62,0.95) !important;
  border: 1px solid var(--border2) !important;
  color: var(--text) !important;
  font-family: 'Noto Sans KR', sans-serif !important;
  font-size: 11.5px !important;
  border-radius: 6px !important;
  padding: 5px 9px !important;
  box-shadow: 0 4px 16px rgba(0,0,0,.4) !important;
}
.leaflet-tooltip::before { display: none !important; }
</style>
</head>
<body>

<!-- 지도 -->
<div id="map"></div>

<!-- 로딩 -->
<div id="loadingOverlay">
  <div class="loading-spinner"></div>
  <div class="loading-msg" id="loadingMsg">데이터 불러오는 중...</div>
</div>

<!-- 왼쪽 패널 -->
<div id="leftPanel">
  <div class="lp-header">
    <div class="lp-title">송파구 데이터 뷰어</div>
    <div class="lp-meta" id="lpMeta">행정동 - · 집계구 - · 필지 -</div>
  </div>

  <!-- 레이어 체크박스 -->
  <div class="lp-section">
    <label class="lp-check-row">
      <input type="checkbox" id="chkBoundary" checked onchange="toggleBoundary()">
      행정동 경계
    </label>
    <label class="lp-check-row">
      <input type="checkbox" id="chkLabel" checked onchange="toggleLabel()">
      이름 라벨
    </label>
    <label class="lp-check-row" style="margin-top:4px">
      <input type="checkbox" id="chkCluster" onchange="toggleCluster()">
      집계구 통계
    </label>
  </div>

  <!-- 필지 레이어 -->
  <div class="lp-section">
    <label class="lp-check-row active">
      <input type="checkbox" id="chkParcel" checked onchange="toggleParcel()">
      필지
      <span id="parcelSizeBadge" style="margin-left:auto;font-size:10px;color:var(--text3);font-family:'DM Mono',monospace"></span>
    </label>
    <select class="layer-selector" id="layerSelect" onchange="changeLayer()">
      <option value="usage">건축물 주용도</option>
      <option value="zone">용도지역</option>
    </select>
    <div class="opacity-row">
      투명도
      <input type="range" id="opacitySlider" min="10" max="100" value="80" oninput="changeOpacity(this.value)">
      <span class="opacity-val" id="opacityVal">80%</span>
    </div>
  </div>

  <!-- 범례 -->
  <div class="legend-wrap" id="legendWrap"></div>
</div>

<!-- 오른쪽 패널 -->
<div id="rightPanel">
  <div class="rp-header">
    <div class="rp-title">📊 송파구 통계</div>
    <div class="rp-close" onclick="toggleRightPanel()">✕</div>
  </div>
  <div class="rp-tabs">
    <div class="rp-tab active" onclick="switchTab('usage')">건축물 주용도</div>
    <div class="rp-tab" onclick="switchTab('zone')">용도지역</div>
    <div class="rp-tab" onclick="switchTab('stats')">지표</div>
    <div class="rp-tab" onclick="switchTab('pop')">집계구 통계</div>
  </div>
  <div class="rp-body">

    <!-- 건축물 주용도 탭 -->
    <div class="rp-pane active" id="pane-usage">
      <div class="donut-wrap">
        <canvas id="usageDonut" width="160" height="160" style="max-width:160px;max-height:160px"></canvas>
        <div class="donut-center">
          <div class="donut-center-label">최다</div>
          <div class="donut-center-val" id="donutCenterLabel">-</div>
        </div>
      </div>
      <div class="summary-row">
        <div class="summary-box">
          <div class="summary-box-val accent" id="sumParcels">-</div>
          <div class="summary-box-sub">총 필지 수</div>
        </div>
        <div class="summary-box">
          <div class="summary-box-val" id="sumArea">-</div>
          <div class="summary-box-sub">연면적 합계</div>
        </div>
      </div>
      <table class="detail-table" id="usageTable">
        <thead>
          <tr>
            <th>구분</th>
            <th>필지</th>
            <th>연면적(㎡)</th>
            <th>비율</th>
          </tr>
        </thead>
        <tbody id="usageTbody"></tbody>
      </table>
    </div>

    <!-- 용도지역 탭 -->
    <div class="rp-pane" id="pane-zone">
      <div class="donut-wrap">
        <canvas id="zoneDonut" width="160" height="160" style="max-width:160px;max-height:160px"></canvas>
        <div class="donut-center" style="top:50%;transform:translateY(-50%)">
          <div class="donut-center-label" style="position:relative;top:0">최다</div>
          <div class="donut-center-val" id="zoneCenterLabel">-</div>
        </div>
      </div>
      <table class="detail-table">
        <thead>
          <tr>
            <th>용도지역</th>
            <th>필지</th>
            <th>비율</th>
          </tr>
        </thead>
        <tbody id="zoneTbody"></tbody>
      </table>
    </div>

    <!-- 지표 탭 -->
    <div class="rp-pane" id="pane-stats">
      <div class="sec-title">동별 건물 현황</div>
      <table class="detail-table">
        <thead><tr><th>법정동</th><th>건물수</th><th>주용도</th></tr></thead>
        <tbody id="dongStatsTbody"></tbody>
      </table>
    </div>

    <!-- 집계구 통계 탭 -->
    <div class="rp-pane" id="pane-pop">
      <div class="sec-title">인구 현황 (2024년 기준)</div>
      <div class="pop-grid">
        <div class="pop-card">
          <div class="pop-card-lbl">총 인구</div>
          <div class="pop-card-val" id="popTotalVal">-</div>
        </div>
        <div class="pop-card">
          <div class="pop-card-lbl">총 가구</div>
          <div class="pop-card-val blue" id="popHHVal">-</div>
        </div>
      </div>
      <div class="sec-title">행정동별 인구</div>
      <table class="detail-table">
        <thead><tr><th>행정동</th><th>인구</th><th>가구</th></tr></thead>
        <tbody id="dongPopTbody"></tbody>
      </table>
    </div>

  </div>
</div>

<script>
// ════════════════════════════════════════
// 컬러 맵
// ════════════════════════════════════════
const USAGE_COLORS = {
  '공동주택':          '#FF8C00',
  '단독주택':          '#32CD32',
  '제1종근린생활시설': '#00BFFF',
  '제2종근린생활시설': '#9370DB',
  '업무시설':          '#FF1493',
  '교육연구시설':      '#00CED1',
  '노유자시설':        '#FF6347',
  '판매시설':          '#DC143C',
  '숙박시설':          '#DA70D6',
  '의료시설':          '#00FF7F',
  '종교시설':          '#FFD700',
  '운동시설':          '#40E0D0',
  '자동차관련시설':    '#708090',
  '문화및집회시설':    '#FF4500',
  '위험물저장처리시설':'#B22222',
  '기타':              '#556B2F',
};

const ZONE_COLORS = {
  '제1종전용주거지역': '#a8d8ea',
  '제2종전용주거지역': '#7ec8e3',
  '제1종일반주거지역': '#90ee90',
  '제2종일반주거지역': '#4ade80',
  '제3종일반주거지역': '#16a34a',
  '준주거지역':        '#fde68a',
  '일반상업지역':      '#ff8c00',
  '근린상업지역':      '#fb923c',
  '유통상업지역':      '#ef4444',
  '자연녹지지역':      '#166534',
  '생산녹지지역':      '#14532d',
  '준공업지역':        '#78716c',
  '기타':              '#374151',
};

// 송파구 행정동 좌표 (지도 라벨용)
const DONG_POSITIONS = {
  '잠실동':  [37.5130, 127.0850],
  '신천동':  [37.5110, 127.0944],
  '풍납동':  [37.5229, 127.1163],
  '송파동':  [37.5007, 127.1163],
  '석촌동':  [37.5021, 127.1043],
  '삼전동':  [37.5043, 127.0926],
  '가락동':  [37.4943, 127.1245],
  '문정동':  [37.4902, 127.1327],
  '장지동':  [37.4779, 127.1502],
  '방이동':  [37.5155, 127.1217],
  '오금동':  [37.5096, 127.1393],
  '거여동':  [37.4933, 127.1570],
  '마천동':  [37.4950, 127.1480],
};

// ════════════════════════════════════════
// 전역 상태
// ════════════════════════════════════════
let map, parcels = [], usageStats = [], popData = [], dongPopData = [];
let currentLayer = 'usage';
let parcelOpacity = 0.8;
let hiddenItems = new Set();
let markerLayer = null;
let labelLayer = null;
let boundaryLayer = null;
let popCircleLayer = null;
let usageChart = null, zoneChart = null;
let rightPanelVisible = true;

// ════════════════════════════════════════
// INIT
// ════════════════════════════════════════
async function init() {
  // Leaflet 지도
  map = L.map('map', {
    center: [37.503, 127.112],
    zoom: 14,
    zoomControl: false,
    attributionControl: false,
  });

  L.control.zoom({ position: 'bottomright' }).addTo(map);

  // Vworld 베이스맵 (야간 다크 타일)
  const VWORLD_KEY = '32AEFA85-C10E-3A79-BF62-73D2533EE6A9';
  L.tileLayer(
    `https://api.vworld.kr/req/wmts/1.0.0/${VWORLD_KEY}/midnight/{z}/{y}/{x}.png`,
    { maxZoom: 19, tileSize: 256, attribution: '© VWorld' }
  ).addTo(map);

  // 데이터 로드
  try {
    setLoading('데이터 불러오는 중...');
    const [p, u, dp] = await Promise.all([
      fetch('data/parcels.json').then(r => r.json()),
      fetch('data/usage_stats.json').then(r => r.json()),
      fetch('data/dong_population.json').then(r => r.json()),
    ]);
    parcels = p;
    usageStats = u;
    dongPopData = dp;

    // 메타 업데이트
    const totalPop = dongPopData.reduce((s,x) => s+x.total_pop, 0);
    const totalHH = dongPopData.reduce((s,x) => s+x.total_hh, 0);
    document.getElementById('lpMeta').textContent =
      `행정동 27 · 집계구 1,278 · 필지 ${parcels.length.toLocaleString()}`;
    document.getElementById('parcelSizeBadge').textContent =
      (JSON.stringify(p).length / 1024 / 1024).toFixed(1) + ' MB';

    // 렌더
    renderLegend(currentLayer);
    renderMarkers(currentLayer);
    renderDongLabels();
    renderRightPanel();

    hideLoading();
  } catch(e) {
    setLoading('오류: ' + e.message);
    console.error(e);
  }

  // 줌 변경 시 마커 크기 조정
  map.on('zoomend', () => renderMarkers(currentLayer));
}

function setLoading(msg) {
  document.getElementById('loadingMsg').textContent = msg;
  document.getElementById('loadingOverlay').style.display = 'flex';
}
function hideLoading() {
  document.getElementById('loadingOverlay').style.display = 'none';
}

// ════════════════════════════════════════
// 마커 렌더링
// ════════════════════════════════════════
function renderMarkers(layer) {
  if (markerLayer) { map.removeLayer(markerLayer); markerLayer = null; }

  const show = document.getElementById('chkParcel').checked;
  if (!show) return;

  const zoom = map.getZoom();
  const r = zoom < 13 ? 1.5 : zoom < 14 ? 2.5 : zoom < 15 ? 3.5 : zoom < 16 ? 5 : 7;

  markerLayer = L.layerGroup();

  parcels.forEach(p => {
    const color = getColor(p, layer);
    if (!color || hiddenItems.has(layer === 'usage' ? p.usage : p.zone)) return;

    const coords = DONG_POSITIONS[p.dong];
    if (!coords) return;

    // 필지별 고유 랜덤 지터
    const seed = fnv1a(p.dong + ':' + p.bun + ':' + p.ji);
    const spread = 0.007;
    const lat = coords[0] + ((seed & 0xFF) / 255 - 0.5) * spread;
    const lng = coords[1] + (((seed >> 8) & 0xFF) / 255 - 0.5) * spread;

    const marker = L.circleMarker([lat, lng], {
      radius: r,
      fillColor: color,
      fillOpacity: parcelOpacity,
      stroke: false,
      weight: 0,
    });

    marker.on('click', (e) => {
      L.popup({ className: 'dark-popup', maxWidth: 260 })
        .setLatLng(e.latlng)
        .setContent(makePopupHtml(p))
        .openOn(map);
    });

    marker.bindTooltip(makeTooltipHtml(p), { sticky: true, opacity: 1 });
    markerLayer.addLayer(marker);
  });

  markerLayer.addTo(map);
}

function getColor(p, layer) {
  if (layer === 'usage') return USAGE_COLORS[p.usage] || USAGE_COLORS['기타'];
  if (layer === 'zone')  return ZONE_COLORS[p.zone]  || ZONE_COLORS['기타'];
  return '#888';
}

function fnv1a(s) {
  let h = 0x811c9dc5;
  for (let i = 0; i < s.length; i++) {
    h ^= s.charCodeAt(i);
    h = (h * 0x01000193) >>> 0;
  }
  return h;
}

function makeTooltipHtml(p) {
  const color = USAGE_COLORS[p.usage] || '#888';
  const addr = `${p.dong} ${p.bun}${p.ji > 0 ? '-'+p.ji : ''}번지`;
  return `
    <div style="font-weight:600;color:${color};margin-bottom:3px">${p.usage || '-'}</div>
    <div style="color:#8b95b0;font-size:10.5px;margin-bottom:2px">${addr}</div>
    ${p.zone ? `<div style="font-size:10.5px">지역: <b>${p.zone}</b></div>` : ''}
    ${p.land_area > 0 ? `<div style="font-size:10.5px">대지: <b>${p.land_area.toLocaleString()} ㎡</b></div>` : ''}
  `;
}

function makePopupHtml(p) {
  const color = USAGE_COLORS[p.usage] || '#888';
  const addr = `${p.dong} ${p.bun}${p.ji > 0 ? '-'+p.ji : ''}번지`;
  const bldgName = p.name ? `<div style="font-size:12px;margin-bottom:6px;color:#94a3b8">${p.name}</div>` : '';
  const rows = [
    ['주용도', `<span style="color:${color};font-weight:600">${p.usage||'-'}</span>`],
    ['용도지역', p.zone||'-'],
    ['대지면적', p.land_area > 0 ? p.land_area.toLocaleString() + ' ㎡' : '-'],
    ['건축면적', p.bldg_area > 0 ? p.bldg_area.toLocaleString() + ' ㎡' : '-'],
    ['연면적', p.floor_area > 0 ? p.floor_area.toLocaleString() + ' ㎡' : '-'],
    ['지상층수', p.floors > 0 ? p.floors + '층' : '-'],
    ['사용승인일', p.approved && p.approved.length === 8 ?
      `${p.approved.slice(0,4)}.${p.approved.slice(4,6)}.${p.approved.slice(6,8)}` : '-'],
  ];
  return `
    <div style="font-size:13px;font-weight:700;margin-bottom:2px">필지 ${addr}</div>
    ${bldgName}
    <hr style="border:none;border-top:1px solid rgba(255,255,255,.1);margin:6px 0">
    <table style="width:100%;font-size:11.5px;border-collapse:collapse">
      ${rows.map(([k,v]) => `
        <tr>
          <td style="padding:2.5px 0;color:#8b95b0;width:70px">${k}</td>
          <td style="padding:2.5px 0;text-align:right;color:#e2e8f0">${v}</td>
        </tr>
      `).join('')}
    </table>
  `;
}

// ════════════════════════════════════════
// 동 라벨
// ════════════════════════════════════════
function renderDongLabels() {
  if (labelLayer) { map.removeLayer(labelLayer); labelLayer = null; }
  if (!document.getElementById('chkLabel').checked) return;

  labelLayer = L.layerGroup();
  Object.entries(DONG_POSITIONS).forEach(([dong, coords]) => {
    const icon = L.divIcon({
      html: `<div style="
        font-family:'Noto Sans KR',sans-serif;
        font-size:12px;font-weight:600;
        color:#e2e8f0;
        text-shadow:0 0 6px rgba(0,0,0,.9),0 0 12px rgba(0,0,0,.7);
        white-space:nowrap;pointer-events:none;
      ">${dong}</div>`,
      className: '',
      iconAnchor: [20, 8],
    });
    labelLayer.addLayer(L.marker(coords, { icon, interactive: false }));
  });
  labelLayer.addTo(map);
}

// ════════════════════════════════════════
// 행정동 경계 (간략 폴리곤 - 좌표 근사)
// ════════════════════════════════════════
// 실제 shapefile 없이 주요 동 중심 기반 Voronoi 대용 표시
function toggleBoundary() {
  // 체크 변경 시 라벨도 같이
}
function toggleLabel() {
  renderDongLabels();
}
function toggleParcel() {
  renderMarkers(currentLayer);
}
function toggleCluster() {
  const show = document.getElementById('chkCluster').checked;
  if (show) renderPopCircles();
  else if (popCircleLayer) { map.removeLayer(popCircleLayer); popCircleLayer = null; }
}

function renderPopCircles() {
  if (popCircleLayer) { map.removeLayer(popCircleLayer); popCircleLayer = null; }
  popCircleLayer = L.layerGroup();
  const maxPop = Math.max(...dongPopData.map(x => x.total_pop));
  const hdong2ldong = {
    '잠실제1동':'잠실동','잠실제2동':'잠실동','잠실제3동':'잠실동','잠실제4동':'잠실동',
    '잠실본동':'잠실동','잠실6동':'잠실동','잠실7동':'신천동',
    '방이제1동':'방이동','방이제2동':'방이동',
    '오금동':'오금동','송파동':'송파동','석촌동':'석촌동','삼전동':'삼전동',
    '가락본동':'가락동','가락제1동':'가락동','가락제2동':'가락동',
    '문정제1동':'문정동','문정제2동':'문정동',
    '거여제1동':'거여동','거여제2동':'거여동',
    '마천제1동':'마천동','마천제2동':'마천동',
    '풍납제1동':'풍납동','풍납제2동':'풍납동',
    '신천동':'신천동','장지동':'장지동','위례동':'장지동',
  };
  dongPopData.forEach(d => {
    const ldong = hdong2ldong[d.dong] || d.dong;
    const coords = DONG_POSITIONS[ldong];
    if (!coords) return;
    const r = Math.sqrt(d.total_pop / maxPop) * 28 + 6;
    const c = L.circleMarker(coords, {
      radius: r,
      fillColor: '#4fc3f7',
      fillOpacity: 0.25,
      color: '#4fc3f7',
      weight: 1.5,
      opacity: 0.7,
    });
    c.bindTooltip(`<b>${d.dong}</b><br>인구: ${d.total_pop.toLocaleString()}명<br>가구: ${d.total_hh.toLocaleString()}가구`,
      { sticky: true, opacity: 1 });
    popCircleLayer.addLayer(c);
  });
  popCircleLayer.addTo(map);
}

// ════════════════════════════════════════
// 범례
// ════════════════════════════════════════
function renderLegend(layer) {
  const wrap = document.getElementById('legendWrap');
  wrap.innerHTML = '';

  let colorMap, items;
  if (layer === 'usage') {
    colorMap = USAGE_COLORS;
    items = Object.entries(
      parcels.reduce((acc, p) => { acc[p.usage] = (acc[p.usage]||0)+1; return acc; }, {})
    ).sort((a,b) => b[1]-a[1]);
  } else {
    colorMap = ZONE_COLORS;
    items = Object.entries(
      parcels.reduce((acc, p) => {
        const z = p.zone || '없음';
        acc[z] = (acc[z]||0)+1; return acc;
      }, {})
    ).sort((a,b) => b[1]-a[1]).filter(x => x[0] !== '없음');
  }

  items.forEach(([name, cnt]) => {
    const color = colorMap[name] || '#666';
    const div = document.createElement('div');
    div.className = 'legend-row' + (hiddenItems.has(name) ? ' hidden' : '');
    div.dataset.name = name;
    div.innerHTML = `
      <div class="legend-dot" style="background:${color}"></div>
      <span class="legend-name">${name}</span>
      <span class="legend-cnt">${cnt.toLocaleString()}</span>
    `;
    div.onclick = () => {
      if (hiddenItems.has(name)) hiddenItems.delete(name);
      else hiddenItems.add(name);
      div.classList.toggle('hidden');
      renderMarkers(layer);
    };
    wrap.appendChild(div);
  });
}

// ════════════════════════════════════════
// 우측 패널 렌더
// ════════════════════════════════════════
function renderRightPanel() {
  renderUsagePane();
  renderZonePane();
  renderStatsPane();
  renderPopPane();
}

function renderUsagePane() {
  // 도넛 차트
  const top = [...usageStats].sort((a,b) => b.필지수 - a.필지수);
  const topN = top.slice(0, 10);
  const otherCnt = top.slice(10).reduce((s,x) => s+x.필지수, 0);

  const labels = topN.map(x => x.주용도분류);
  const values = topN.map(x => x.필지수);
  const colors = topN.map(x => USAGE_COLORS[x.주용도분류] || '#556B2F');
  if (otherCnt > 0) { labels.push('기타'); values.push(otherCnt); colors.push('#4a5568'); }

  const ctx = document.getElementById('usageDonut').getContext('2d');
  if (usageChart) usageChart.destroy();
  usageChart = new Chart(ctx, {
    type: 'doughnut',
    data: { labels, datasets: [{ data: values, backgroundColor: colors, borderWidth: 0, hoverOffset: 4 }] },
    options: {
      cutout: '62%',
      plugins: { legend: { display: false },
        tooltip: { callbacks: { label: c => ` ${c.label}: ${c.raw.toLocaleString()}필지` } }
      },
    }
  });

  document.getElementById('donutCenterLabel').textContent = top[0]?.주용도분류 || '-';

  const totalP = usageStats.reduce((s,x) => s+x.필지수, 0);
  const totalA = usageStats.reduce((s,x) => s+x.총면적, 0);
  document.getElementById('sumParcels').textContent = totalP.toLocaleString();
  document.getElementById('sumArea').textContent = (totalA/10000).toFixed(0) + '만㎡';

  // 테이블
  const tbody = document.getElementById('usageTbody');
  tbody.innerHTML = top.map(s => {
    const color = USAGE_COLORS[s.주용도분류] || '#556B2F';
    const areaStr = s.총면적 > 0
      ? (s.총면적 >= 1000000 ? (s.총면적/10000).toFixed(0)+'만' : s.총면적.toLocaleString())
      : '-';
    return `<tr>
      <td><span class="td-color-dot" style="background:${color}"></span>${s.주용도분류}</td>
      <td>${s.필지수.toLocaleString()}</td>
      <td>${areaStr}</td>
      <td>${s.비율}%</td>
    </tr>`;
  }).join('');
}

function renderZonePane() {
  const zoneCnt = {};
  const zoneArea = {};
  parcels.forEach(p => {
    const z = p.zone || null;
    if (!z) return;
    zoneCnt[z] = (zoneCnt[z]||0) + 1;
    zoneArea[z] = (zoneArea[z]||0) + (p.land_area||0);
  });
  const items = Object.entries(zoneCnt).sort((a,b) => b[1]-a[1]);
  const total = items.reduce((s,x) => s+x[1], 0);

  const labels = items.map(x => x[0]);
  const values = items.map(x => x[1]);
  const colors = items.map(x => ZONE_COLORS[x[0]] || '#374151');

  const ctx2 = document.getElementById('zoneDonut').getContext('2d');
  if (zoneChart) zoneChart.destroy();
  zoneChart = new Chart(ctx2, {
    type: 'doughnut',
    data: { labels, datasets: [{ data: values, backgroundColor: colors, borderWidth: 0, hoverOffset: 4 }] },
    options: {
      cutout: '62%',
      plugins: { legend: { display: false },
        tooltip: { callbacks: { label: c => ` ${c.label}: ${c.raw.toLocaleString()}필지` } }
      },
    }
  });
  document.getElementById('zoneCenterLabel').textContent = items[0]?.[0] || '-';

  const tbody = document.getElementById('zoneTbody');
  tbody.innerHTML = items.map(([z, cnt]) => {
    const color = ZONE_COLORS[z] || '#374151';
    const pct = ((cnt/total)*100).toFixed(1);
    return `<tr>
      <td><span class="td-color-dot" style="background:${color}"></span>${z}</td>
      <td>${cnt.toLocaleString()}</td>
      <td>${pct}%</td>
    </tr>`;
  }).join('');
}

function renderStatsPane() {
  const dongCnt = {};
  const dongMain = {};
  parcels.forEach(p => {
    dongCnt[p.dong] = (dongCnt[p.dong]||0)+1;
    dongMain[p.dong] = dongMain[p.dong] || {};
    dongMain[p.dong][p.usage] = (dongMain[p.dong][p.usage]||0)+1;
  });
  const items = Object.entries(dongCnt).sort((a,b) => b[1]-a[1]);
  const tbody = document.getElementById('dongStatsTbody');
  tbody.innerHTML = items.map(([dong, cnt]) => {
    const usages = dongMain[dong]||{};
    const main = Object.entries(usages).sort((a,b)=>b[1]-a[1])[0]?.[0]||'-';
    const color = USAGE_COLORS[main]||'#888';
    return `<tr>
      <td>${dong}</td>
      <td>${cnt.toLocaleString()}</td>
      <td><span class="td-color-dot" style="background:${color}"></span>${main}</td>
    </tr>`;
  }).join('');
}

function renderPopPane() {
  const totalPop = dongPopData.reduce((s,x) => s+x.total_pop, 0);
  const totalHH = dongPopData.reduce((s,x) => s+x.total_hh, 0);
  document.getElementById('popTotalVal').textContent = totalPop.toLocaleString();
  document.getElementById('popHHVal').textContent = totalHH.toLocaleString();

  const tbody = document.getElementById('dongPopTbody');
  tbody.innerHTML = [...dongPopData].sort((a,b) => b.total_pop - a.total_pop).map(d => `
    <tr>
      <td>${d.dong}</td>
      <td>${d.total_pop.toLocaleString()}</td>
      <td>${d.total_hh.toLocaleString()}</td>
    </tr>
  `).join('');
}

// ════════════════════════════════════════
// 이벤트 핸들러
// ════════════════════════════════════════
function changeLayer() {
  currentLayer = document.getElementById('layerSelect').value;
  hiddenItems.clear();
  renderLegend(currentLayer);
  renderMarkers(currentLayer);
}

function changeOpacity(val) {
  parcelOpacity = val / 100;
  document.getElementById('opacityVal').textContent = val + '%';
  renderMarkers(currentLayer);
}

function switchTab(tab) {
  document.querySelectorAll('.rp-tab').forEach((el, i) => {
    el.classList.toggle('active', ['usage','zone','stats','pop'][i] === tab);
  });
  document.querySelectorAll('.rp-pane').forEach(p => p.classList.remove('active'));
  document.getElementById('pane-' + tab).classList.add('active');
}

function toggleRightPanel() {
  const rp = document.getElementById('rightPanel');
  rightPanelVisible = !rightPanelVisible;
  rp.style.display = rightPanelVisible ? 'flex' : 'none';
}

// ════════════════════════════════════════
// 다크 팝업 CSS
// ════════════════════════════════════════
const popupStyle = document.createElement('style');
popupStyle.textContent = `
.dark-popup .leaflet-popup-content-wrapper {
  background: rgba(22,33,62,0.97);
  border: 1px solid rgba(255,255,255,.14);
  border-radius: 10px;
  color: #e2e8f0;
  box-shadow: 0 12px 40px rgba(0,0,0,.7);
  padding: 0;
}
.dark-popup .leaflet-popup-content {
  margin: 14px 16px;
  font-family: 'Noto Sans KR', sans-serif;
  font-size: 12px;
  min-width: 210px;
}
.dark-popup .leaflet-popup-tip-container { display: none; }
.dark-popup .leaflet-popup-close-button {
  color: #94a3b8 !important;
  top: 8px !important;
  right: 10px !important;
  font-size: 16px !important;
}
`;
document.head.appendChild(popupStyle);

// START
window.addEventListener('load', init);
</script>
</body>
</html>
