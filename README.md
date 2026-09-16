[kurs.html](https://github.com/user-attachments/files/32274022/kurs.html)
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Deutsch lernen — 독일어 표현 연습</title>
<style>
  :root{
    --ink:#2B2118;
    --paper:#FAF5EA;
    --surface:#FFFFFF;
    --line:#E8DDC8;
    --amber:#E08A1E;
    --amber-soft:#FDF0DA;
    --good:#2A7A52;
    --warn:#B5761A;
    --bad:#C2452F;
    --muted:#8A7B66;
  }
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:var(--paper);color:var(--ink);
    font-family:"Pretendard","Apple SD Gothic Neo","Malgun Gothic","Noto Sans KR",system-ui,sans-serif;
    font-size:16px;line-height:1.6;-webkit-font-smoothing:antialiased;
  }
  .de{font-family:"Helvetica Neue",Helvetica,Arial,sans-serif;}
  .wrap{max-width:620px;margin:0 auto;padding:18px 16px 56px;}

  header{display:flex;align-items:center;gap:10px;margin-bottom:14px;}
  .mark{width:30px;height:30px;border-radius:10px;background:var(--amber);flex:0 0 auto;
    display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:15px;}
  h1{font-size:19px;font-weight:800;margin:0;letter-spacing:-0.02em;}
  header span{font-size:13px;color:var(--muted);}

  select#unitSel{
    font:inherit;font-size:15px;font-weight:700;padding:9px 12px;width:100%;
    border:2px solid var(--line);border-radius:12px;background:var(--surface);color:var(--ink);
    margin-bottom:12px;
  }
  details.info{font-size:14px;margin-bottom:14px;}
  details.info summary{cursor:pointer;color:var(--amber);font-weight:700;list-style:none;}
  details.info summary::-webkit-details-marker{display:none;}
  details.info summary::before{content:"▸ ";}
  details.info[open] summary::before{content:"▾ ";}
  details.info .body{background:var(--surface);border:2px solid var(--line);border-radius:14px;padding:16px;margin-top:8px;}
  details.info h3{font-size:14px;margin:16px 0 6px;color:var(--amber);}
  details.info h3:first-child{margin-top:0;}
  details.info ul{margin:0;padding-left:18px;}
  table.gram{border-collapse:collapse;width:100%;font-size:13.5px;}
  table.gram th,table.gram td{text-align:left;padding:5px 6px;border-bottom:1px solid var(--line);}
  table.gram th{color:var(--muted);font-weight:700;}
  table.gram td.p{font-weight:700;color:var(--ink);}
  table.gram td.v{color:var(--amber);font-weight:600;}

  nav.tabs{display:flex;gap:6px;overflow-x:auto;padding-bottom:6px;margin-bottom:14px;}
  nav.tabs button{
    flex:0 0 auto;font:inherit;font-size:14px;font-weight:600;background:var(--surface);color:var(--muted);
    border:2px solid var(--line);border-radius:999px;padding:6px 14px;cursor:pointer;white-space:nowrap;
  }
  nav.tabs button[aria-pressed="true"]{background:var(--amber);color:#fff;border-color:var(--amber);}

  .card{background:var(--surface);border:2px solid var(--line);border-radius:20px;overflow:hidden;
    box-shadow:0 2px 0 rgba(43,33,24,.04);}
  .pic{display:block;width:100%;height:auto;background:var(--amber-soft);border-bottom:2px solid var(--line);}
  .body{padding:20px 20px 22px;}

  .counter{display:flex;justify-content:space-between;align-items:center;font-size:12.5px;color:var(--muted);margin-bottom:12px;}
  .track{height:4px;background:var(--line);border-radius:3px;overflow:hidden;flex:1;margin-left:14px;}
  .track i{display:block;height:100%;background:var(--amber);border-radius:3px;transition:width .25s;}

  .phrase{font-size:clamp(24px,5.4vw,33px);font-weight:700;line-height:1.25;margin:0;word-break:keep-all;}
  .phrase span.w{cursor:pointer;border-bottom:2px solid transparent;padding:0 1px;}
  .phrase span.w:hover,.phrase span.w:focus-visible{border-bottom-color:var(--amber);outline:none;}
  .phrase span.w.g{color:var(--good);}
  .phrase span.w.a{color:var(--warn);}
  .phrase span.w.b{color:var(--bad);}
  .kr{margin:10px 0 0;font-size:19px;font-weight:700;color:var(--amber);letter-spacing:-0.01em;}
  .meaning{margin:6px 0 0;font-size:16.5px;}
  .tip{margin:14px 0 0;background:var(--amber-soft);border-radius:12px;padding:12px 14px;font-size:14px;}
  .tip b{color:var(--amber);}
  .hint{margin:8px 0 0;font-size:12.5px;color:var(--muted);}

  .actions{display:flex;gap:8px;margin-top:18px;flex-wrap:wrap;}
  button.act{font:inherit;font-size:15px;font-weight:700;border:2px solid var(--line);border-radius:12px;
    background:var(--surface);color:var(--ink);padding:11px 15px;cursor:pointer;}
  button.act:hover{background:#FCF8F0;}
  button.act.primary{background:var(--amber);border-color:var(--amber);color:#fff;flex:1;min-width:150px;}
  button.act.primary:hover{background:#C97815;}
  button.act.rec{background:var(--bad);border-color:var(--bad);color:#fff;}
  button:focus-visible{outline:3px solid #4A7BD1;outline-offset:2px;}

  .result{margin-top:18px;border-top:2px solid var(--line);padding-top:14px;display:none;}
  .result.on{display:block;}
  .verdict{display:flex;align-items:baseline;gap:10px;}
  .score{font-size:32px;font-weight:800;line-height:1;}
  .score.g{color:var(--good);}.score.a{color:var(--warn);}.score.b{color:var(--bad);}
  .verdict p{margin:0;font-size:14.5px;font-weight:600;}
  .heard{margin:8px 0 0;font-size:13.5px;color:var(--muted);}
  .heard b{color:var(--ink);}
  .again{font:inherit;font-size:13px;background:none;border:1.5px solid var(--line);border-radius:8px;
    padding:3px 9px;margin-top:8px;cursor:pointer;}

  .pager{display:flex;justify-content:space-between;gap:8px;margin-top:14px;}
  .pager button{font:inherit;font-size:15px;font-weight:700;background:none;border:none;color:var(--ink);padding:8px 2px;cursor:pointer;}
  .pager button:disabled{color:var(--line);cursor:default;}
  .dots{display:flex;gap:5px;margin-top:12px;flex-wrap:wrap;}
  .dots i{width:9px;height:9px;border-radius:50%;background:var(--line);display:block;}
  .dots i.done{background:var(--good);}
  .dots i.retry{background:var(--bad);}
  .dots i.now{box-shadow:0 0 0 3px rgba(224,138,30,.3);}

  .notice{margin-top:16px;font-size:13px;color:var(--muted);border:2px dashed var(--line);border-radius:12px;padding:11px 14px;}
  .notice b{color:var(--ink);}
  @media (prefers-reduced-motion:reduce){*{transition:none!important;}}
</style>
</head>
<body>
<div class="wrap">

  <header>
    <span class="mark de">D</span>
    <h1 class="de">Deutsch lernen</h1>
    <span>듣고 · 따라 말하기</span>
  </header>

  <select id="unitSel" aria-label="단원 선택"></select>

  <details class="info">
    <summary>단원 정보 보기</summary>
    <div class="body" id="unitInfoBody"></div>
  </details>

  <nav class="tabs" id="tabs" aria-label="파트"></nav>

  <div class="card">
    <svg class="pic" id="pic" viewBox="0 0 320 180" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="표현 그림"></svg>
    <div class="body">
      <div class="counter">
        <span id="count"></span>
        <span class="track"><i id="bar" style="width:0%"></i></span>
      </div>

      <p class="phrase de" id="phrase"></p>
      <p class="kr" id="kr"></p>
      <p class="meaning" id="meaning"></p>
      <div class="tip" id="tip"></div>
      <p class="hint">문장의 단어를 누르면 그 단어만 들을 수 있어요.</p>

      <div class="actions">
        <button class="act" id="play">▶ 듣기</button>
        <button class="act" id="slow">🐢 천천히</button>
        <button class="act primary" id="rec">🎤 따라 말하기</button>
      </div>

      <div class="result" id="result" aria-live="polite">
        <div class="verdict">
          <span class="score" id="score">—</span>
          <p id="verdictText"></p>
        </div>
        <p class="heard" id="heard"></p>
        <div id="coach"></div>
      </div>

      <div class="pager">
        <button id="prev">← 이전</button>
        <button id="next">다음 →</button>
      </div>

      <div class="dots" id="dots"></div>
    </div>
  </div>

  <p class="notice" id="notice">
    <b>마이크가 안 될 때</b> — 크롬이나 엣지에서 열고, 주소창 자물쇠 아이콘에서 마이크를 허용해 주세요.
    연결이 불안정하면 듣기와 따라 읽기만으로도 연습할 수 있습니다.
  </p>

</div>

<script>
"use strict";

/* 장면 그림 — 320x180 */
const SCENES = {

morgen:`<rect width="320" height="180" fill="#FFE2B0"/>
<g stroke="#F3A31E" stroke-width="6" stroke-linecap="round">
<line x1="160" y1="44" x2="160" y2="24"/><line x1="104" y1="64" x2="91" y2="51"/>
<line x1="216" y1="64" x2="229" y2="51"/><line x1="80" y1="118" x2="60" y2="118"/>
<line x1="240" y1="118" x2="260" y2="118"/></g>
<circle cx="160" cy="118" r="40" fill="#F3A31E"/>
<path d="M0 124 q60 -20 110 4 q50 24 100 -2 q60 -30 110 2 V180 H0 Z" fill="#8CBE68"/>`,

tag:`<rect width="320" height="180" fill="#BCE2F6"/>
<circle cx="252" cy="44" r="26" fill="#FFD23F"/>
<g fill="#FFFFFF" opacity=".85"><ellipse cx="90" cy="54" rx="34" ry="17"/><ellipse cx="116" cy="46" rx="24" ry="15"/></g>
<rect y="126" width="320" height="54" fill="#8CBE68"/>
<rect x="118" y="78" width="84" height="48" fill="#F2E6D2"/>
<path d="M110 78 L160 46 L210 78 Z" fill="#C25A3A"/>
<rect x="148" y="98" width="24" height="28" fill="#A9703F"/>`,

abend:`<rect width="320" height="180" fill="#F6AE63"/>
<rect width="320" height="70" fill="#E8834B"/>
<circle cx="160" cy="122" r="34" fill="#E2552A"/>
<path d="M0 128 q70 -16 120 2 q60 22 110 -4 q50 -22 90 4 V180 H0 Z" fill="#4E6B4A"/>`,

nacht:`<rect width="320" height="180" fill="#2B3A61"/>
<g fill="#FFFFFF"><circle cx="60" cy="42" r="2.5"/><circle cx="106" cy="70" r="2"/><circle cx="148" cy="34" r="2.5"/>
<circle cx="196" cy="62" r="2"/><circle cx="276" cy="90" r="2.5"/><circle cx="38" cy="96" r="2"/></g>
<circle cx="234" cy="52" r="28" fill="#FFE9A8"/><circle cx="222" cy="44" r="25" fill="#2B3A61"/>
<path d="M0 132 q80 -24 140 0 q70 26 180 -6 V180 H0 Z" fill="#1C2748"/>`,

hallo:`<rect width="320" height="180" fill="#FFF0DA"/>
<g><circle cx="112" cy="66" r="24" fill="#F3C9A2"/><path d="M90 60 a22 22 0 0 1 44 0 z" fill="#5A3C2B"/>
<rect x="88" y="94" width="48" height="70" rx="20" fill="#E4813C"/>
<rect x="128" y="72" width="13" height="40" rx="6.5" fill="#F3C9A2" transform="rotate(30 134 92)"/>
<circle cx="152" cy="66" r="9" fill="#F3C9A2"/></g>
<g><circle cx="216" cy="66" r="24" fill="#F0BE95"/><path d="M194 62 a22 22 0 0 1 44 0 l0 10 a30 30 0 0 0 -44 0z" fill="#3E2B20"/>
<rect x="192" y="94" width="48" height="70" rx="20" fill="#4E8FBF"/>
<rect x="187" y="72" width="13" height="40" rx="6.5" fill="#F0BE95" transform="rotate(-30 193 92)"/>
<circle cx="176" cy="66" r="9" fill="#F0BE95"/></g>`,

handschlag:`<rect width="320" height="180" fill="#EFF4F8"/>
<g><circle cx="98" cy="58" r="22" fill="#F3C9A2"/><path d="M78 54 a20 20 0 0 1 40 0 z" fill="#6B4A32"/>
<rect x="76" y="84" width="44" height="80" rx="18" fill="#3F5A80"/></g>
<g><circle cx="222" cy="58" r="22" fill="#EFBE98"/><path d="M202 54 a20 20 0 0 1 40 0 z" fill="#8C6239"/>
<rect x="200" y="84" width="44" height="80" rx="18" fill="#7E6BA8"/></g>
<rect x="114" y="104" width="46" height="14" rx="7" fill="#F3C9A2"/>
<rect x="160" y="104" width="46" height="14" rx="7" fill="#EFBE98"/>
<rect x="144" y="98" width="32" height="26" rx="10" fill="#E9B183"/>`,

abschied:`<rect width="320" height="180" fill="#E7F1E4"/>
<g><circle cx="88" cy="70" r="23" fill="#F3C9A2"/><path d="M66 66 a22 22 0 0 1 44 0 z" fill="#4A3122"/>
<rect x="65" y="96" width="46" height="68" rx="19" fill="#D8624F"/>
<rect x="104" y="76" width="13" height="38" rx="6.5" fill="#F3C9A2" transform="rotate(32 110 95)"/>
<circle cx="127" cy="70" r="9" fill="#F3C9A2"/></g>
<g opacity=".9"><circle cx="232" cy="78" r="19" fill="#EFBE98"/><path d="M214 74 a18 18 0 0 1 36 0 z" fill="#2F2118"/>
<rect x="213" y="100" width="38" height="60" rx="16" fill="#5E8C6A"/>
<rect x="247" y="104" width="12" height="34" rx="6" fill="#EFBE98"/></g>
<g stroke="#9BB59B" stroke-width="4" stroke-linecap="round" opacity=".8">
<line x1="272" y1="60" x2="292" y2="52"/><line x1="276" y1="76" x2="298" y2="74"/></g>`,

frage:`<rect width="320" height="180" fill="#FFF0DA"/>
<g><circle cx="86" cy="76" r="24" fill="#F3C9A2"/><path d="M64 72 a22 22 0 0 1 44 0 z" fill="#5A3C2B"/>
<rect x="62" y="104" width="48" height="60" rx="20" fill="#E4813C"/></g>
<path d="M140 40 h140 a14 14 0 0 1 14 14 v56 a14 14 0 0 1 -14 14 h-108 l-22 20 v-20 h-10 a14 14 0 0 1 -14 -14 v-56 a14 14 0 0 1 14 -14z" fill="#FFFFFF" stroke="#E2C9A0" stroke-width="2"/>
<text x="210" y="100" font-family="Helvetica,Arial,sans-serif" font-size="58" font-weight="700" fill="#E08A1E" text-anchor="middle">?</text>`,

sprechen:`<rect width="320" height="180" fill="#F3EEF8"/>
<path d="M28 34 h130 a14 14 0 0 1 14 14 v44 a14 14 0 0 1 -14 14 h-92 l-20 18 v-18 h-18 a14 14 0 0 1 -14 -14 v-44 a14 14 0 0 1 14 -14z" fill="#FFFFFF" stroke="#D9CBE8" stroke-width="2"/>
<g fill="#C9B7DE"><rect x="48" y="54" width="86" height="8" rx="4"/><rect x="48" y="72" width="60" height="8" rx="4"/></g>
<path d="M162 82 h130 a14 14 0 0 1 14 14 v44 a14 14 0 0 1 -14 14 h-110 l-20 18 v-18 a14 14 0 0 1 -14 -14 v-44 a14 14 0 0 1 14 -14z" fill="#E08A1E"/>
<g fill="#FFFFFF" opacity=".9"><rect x="182" y="102" width="86" height="8" rx="4"/><rect x="182" y="120" width="56" height="8" rx="4"/></g>`,

namensschild:`<rect width="320" height="180" fill="#EFF4F8"/>
<rect x="62" y="34" width="196" height="118" rx="14" fill="#FFFFFF" stroke="#CBD8E4" stroke-width="2"/>
<rect x="62" y="34" width="196" height="30" rx="14" fill="#E08A1E"/><rect x="62" y="52" width="196" height="12" fill="#E08A1E"/>
<circle cx="102" cy="100" r="20" fill="#F3C9A2"/><path d="M82 96 a20 20 0 0 1 40 0 z" fill="#5A3C2B"/>
<path d="M78 136 a24 24 0 0 1 48 0 z" fill="#4E8FBF"/>
<g fill="#D7DEE6"><rect x="140" y="88" width="96" height="10" rx="5"/><rect x="140" y="110" width="66" height="10" rx="5"/></g>`,

gesicht_gut:`<rect width="320" height="180" fill="#FFF4D6"/>
<circle cx="160" cy="90" r="62" fill="#FFCE3A"/>
<circle cx="138" cy="78" r="7" fill="#4A3722"/><circle cx="182" cy="78" r="7" fill="#4A3722"/>
<path d="M132 108 q28 22 56 0" stroke="#4A3722" stroke-width="7" fill="none" stroke-linecap="round"/>`,

gesicht_sehrgut:`<rect width="320" height="180" fill="#FFF0D0"/>
<circle cx="160" cy="92" r="62" fill="#FFC020"/>
<path d="M128 74 q10 -12 20 0" stroke="#4A3722" stroke-width="7" fill="none" stroke-linecap="round"/>
<path d="M172 74 q10 -12 20 0" stroke="#4A3722" stroke-width="7" fill="none" stroke-linecap="round"/>
<path d="M124 100 q36 38 72 0 z" fill="#4A3722"/>
<g fill="#F3A31E"><path d="M52 40 l6 14 14 6 -14 6 -6 14 -6 -14 -14 -6 14 -6z"/>
<path d="M266 52 l5 11 11 5 -11 5 -5 11 -5 -11 -11 -5 11 -5z"/></g>`,

gesicht_soso:`<rect width="320" height="180" fill="#F1F0EA"/>
<circle cx="160" cy="90" r="62" fill="#E7C95C"/>
<circle cx="138" cy="78" r="7" fill="#4A3722"/><circle cx="182" cy="78" r="7" fill="#4A3722"/>
<path d="M130 114 q15 -10 30 0 q15 10 30 0" stroke="#4A3722" stroke-width="7" fill="none" stroke-linecap="round"/>`,

gesicht_nichtgut:`<rect width="320" height="180" fill="#EDEFF3"/>
<circle cx="160" cy="90" r="62" fill="#C9CEDA"/>
<path d="M128 72 l22 8" stroke="#4A3722" stroke-width="7" stroke-linecap="round"/>
<path d="M192 72 l-22 8" stroke="#4A3722" stroke-width="7" stroke-linecap="round"/>
<circle cx="140" cy="88" r="6" fill="#4A3722"/><circle cx="180" cy="88" r="6" fill="#4A3722"/>
<path d="M134 122 q26 -20 52 0" stroke="#4A3722" stroke-width="7" fill="none" stroke-linecap="round"/>`,

schueler:`<rect width="320" height="180" fill="#E9F3EC"/>
<g><circle cx="128" cy="62" r="24" fill="#F3C9A2"/><path d="M106 58 a22 22 0 0 1 44 0 z" fill="#2F2118"/>
<rect x="104" y="90" width="50" height="74" rx="20" fill="#4E8FBF"/></g>
<rect x="150" y="96" width="44" height="54" rx="10" fill="#D8624F"/>
<rect x="150" y="110" width="44" height="10" fill="#B94C3C"/>
<g transform="rotate(-8 240 110)"><rect x="206" y="84" width="72" height="52" rx="6" fill="#FFFFFF" stroke="#C3D2C8" stroke-width="2"/>
<line x1="242" y1="84" x2="242" y2="136" stroke="#C3D2C8" stroke-width="2"/>
<g fill="#D9E3DC"><rect x="216" y="98" width="18" height="6" rx="3"/><rect x="216" y="112" width="18" height="6" rx="3"/>
<rect x="250" y="98" width="18" height="6" rx="3"/><rect x="250" y="112" width="18" height="6" rx="3"/></g></g>`,

haus:`<rect width="320" height="180" fill="#E8F1F6"/>
<rect y="140" width="320" height="40" fill="#8CBE68"/>
<rect x="96" y="82" width="128" height="58" fill="#F6ECDA"/>
<path d="M84 84 L160 30 L236 84 Z" fill="#C25A3A"/>
<rect x="146" y="102" width="28" height="38" fill="#A9703F"/>
<rect x="110" y="96" width="24" height="24" fill="#8FC7E0" stroke="#F6ECDA" stroke-width="3"/>
<rect x="186" y="96" width="24" height="24" fill="#8FC7E0" stroke="#F6ECDA" stroke-width="3"/>
<circle cx="168" cy="122" r="3" fill="#F6ECDA"/>`,

stadt:`<rect width="320" height="180" fill="#DCEBF5"/>
<rect y="146" width="320" height="34" fill="#B9CDBA"/>
<rect x="34" y="80" width="46" height="66" fill="#8AA6C0"/>
<rect x="88" y="54" width="52" height="92" fill="#6F8CA8"/>
<rect x="148" y="94" width="44" height="52" fill="#9DB6CC"/>
<rect x="200" y="66" width="56" height="80" fill="#7E9BB6"/>
<g fill="#E9F3FA" opacity=".85"><rect x="44" y="90" width="10" height="12"/><rect x="60" y="90" width="10" height="12"/>
<rect x="98" y="66" width="12" height="14"/><rect x="118" y="66" width="12" height="14"/><rect x="98" y="92" width="12" height="14"/>
<rect x="118" y="92" width="12" height="14"/><rect x="210" y="80" width="12" height="14"/><rect x="232" y="80" width="12" height="14"/>
<rect x="210" y="104" width="12" height="14"/><rect x="232" y="104" width="12" height="14"/></g>
<path d="M276 42 a22 22 0 0 1 44 0 c0 18 -22 44 -22 44 s-22 -26 -22 -44z" fill="#D8624F" transform="translate(-24,0)"/>
<circle cx="274" cy="64" r="8" fill="#FFF0DA"/>`,

welt:`<rect width="320" height="180" fill="#E4F1F7"/>
<circle cx="150" cy="92" r="60" fill="#5B9BD5"/>
<path d="M112 56 q26 10 22 30 q-4 20 -30 18 q-16 -2 -18 -18 q-2 -22 26 -30z" fill="#8CBE68"/>
<path d="M156 74 q34 -6 40 16 q6 22 -18 30 q-26 8 -30 -14 q-4 -24 8 -32z" fill="#8CBE68"/>
<path d="M132 138 q20 6 34 -4" stroke="#8CBE68" stroke-width="10" fill="none" stroke-linecap="round"/>
<path d="M62 132 q70 -76 176 -92" stroke="#E08A1E" stroke-width="4" fill="none" stroke-dasharray="8 8" stroke-linecap="round"/>
<path d="M232 22 l24 14 -24 14 4 -14z" fill="#E08A1E"/>`,

flagge_de:`<rect width="320" height="180" fill="#F4F1EA"/><rect x="77" y="40" width="166" height="33.3" fill="#1A1A1A"/><rect x="77" y="73.3" width="166" height="33.4" fill="#DD0000"/><rect x="77" y="106.7" width="166" height="33.3" fill="#FFCE00"/><rect x="77" y="40" width="166" height="100" fill="none" stroke="#D8D2C4" stroke-width="2"/>`,

flagge_at:`<rect width="320" height="180" fill="#F4F1EA"/><rect x="85" y="40" width="150" height="33.3" fill="#ED2939"/><rect x="85" y="73.3" width="150" height="33.4" fill="#FFFFFF"/><rect x="85" y="106.7" width="150" height="33.3" fill="#ED2939"/><rect x="85" y="40" width="150" height="100" fill="none" stroke="#D8D2C4" stroke-width="2"/>`,

flagge_ch:`<rect width="320" height="180" fill="#F4F1EA"/><rect x="110" y="40" width="100" height="100" fill="#FF0000"/><rect x="150.62" y="58.75" width="18.75" height="62.50" fill="#FFFFFF"/><rect x="128.75" y="80.62" width="62.50" height="18.75" fill="#FFFFFF"/><rect x="110" y="40" width="100" height="100" fill="none" stroke="#D8D2C4" stroke-width="2"/>`,

flagge_kr:`<rect width="320" height="180" fill="#F4F1EA"/><rect x="85" y="40" width="150" height="100" fill="#FFFFFF"/><g transform="rotate(-33.69 160 90)"><circle cx="160" cy="90" r="25.0" fill="#CD2E3A"/><path d="M135.0 90 A25.0 25.0 0 0 0 185.0 90 A12.5 12.5 0 0 0 160 90 A12.5 12.5 0 0 1 135.0 90 Z" fill="#0047A0"/></g><g fill="#1A1A1A"><g transform="rotate(-33.69 120.0615858717835 63.374390581189004)"><rect x="107.0615858717835" y="54.47" width="26" height="4.2"/><rect x="107.0615858717835" y="61.27" width="26" height="4.2"/><rect x="107.0615858717835" y="68.07" width="26" height="4.2"/></g><g transform="rotate(33.69 199.9384141282165 63.374390581189004)"><rect x="186.9384141282165" y="54.47" width="10.80" height="4.2"/><rect x="202.14" y="54.47" width="10.80" height="4.2"/><rect x="186.9384141282165" y="61.27" width="26" height="4.2"/><rect x="186.9384141282165" y="68.07" width="10.80" height="4.2"/><rect x="202.14" y="68.07" width="10.80" height="4.2"/></g><g transform="rotate(33.69 120.0615858717835 116.625609418811)"><rect x="107.0615858717835" y="107.73" width="26" height="4.2"/><rect x="107.0615858717835" y="114.53" width="10.80" height="4.2"/><rect x="122.26" y="114.53" width="10.80" height="4.2"/><rect x="107.0615858717835" y="121.33" width="26" height="4.2"/></g><g transform="rotate(-33.69 199.9384141282165 116.625609418811)"><rect x="186.9384141282165" y="107.73" width="10.80" height="4.2"/><rect x="202.14" y="107.73" width="10.80" height="4.2"/><rect x="186.9384141282165" y="114.53" width="10.80" height="4.2"/><rect x="202.14" y="114.53" width="10.80" height="4.2"/><rect x="186.9384141282165" y="121.33" width="10.80" height="4.2"/><rect x="202.14" y="121.33" width="10.80" height="4.2"/></g></g><rect x="85" y="40" width="150" height="100" fill="none" stroke="#D8D2C4" stroke-width="2"/>`,

flagge_tr:`<rect width="320" height="180" fill="#F4F1EA"/><rect x="85" y="40" width="150" height="100" fill="#E30A17"/><circle cx="135.0" cy="90" r="25.0" fill="#FFFFFF"/><circle cx="141.25" cy="90" r="20.0" fill="#E30A17"/><polygon points="154.6,90.0 163.2,87.2 163.2,78.1 168.6,85.5 177.2,82.7 171.9,90.0 177.2,97.3 168.6,94.5 163.2,101.9 163.2,92.8" fill="#FFFFFF"/><rect x="85" y="40" width="150" height="100" fill="none" stroke="#D8D2C4" stroke-width="2"/>`,

flagge_us:`<rect width="320" height="180" fill="#F4F1EA"/><rect x="65" y="40" width="190" height="100" fill="#FFFFFF"/><rect x="65" y="40.00" width="190" height="7.69" fill="#B31942"/><rect x="65" y="55.38" width="190" height="7.69" fill="#B31942"/><rect x="65" y="70.77" width="190" height="7.69" fill="#B31942"/><rect x="65" y="86.15" width="190" height="7.69" fill="#B31942"/><rect x="65" y="101.54" width="190" height="7.69" fill="#B31942"/><rect x="65" y="116.92" width="190" height="7.69" fill="#B31942"/><rect x="65" y="132.31" width="190" height="7.69" fill="#B31942"/><rect x="65" y="40" width="76.00" height="53.85" fill="#0A3161"/><defs><polygon id="usst" points="0.0,-2.9 0.7,-0.9 2.8,-0.9 1.1,0.3 1.7,2.3 0.0,1.1 -1.7,2.3 -1.1,0.3 -2.8,-0.9 -0.7,-0.9" fill="#FFFFFF"/></defs><use href="#usst" x="71.3" y="45.4"/><use href="#usst" x="84.0" y="45.4"/><use href="#usst" x="96.7" y="45.4"/><use href="#usst" x="109.3" y="45.4"/><use href="#usst" x="122.0" y="45.4"/><use href="#usst" x="134.7" y="45.4"/><use href="#usst" x="77.7" y="50.8"/><use href="#usst" x="90.3" y="50.8"/><use href="#usst" x="103.0" y="50.8"/><use href="#usst" x="115.7" y="50.8"/><use href="#usst" x="128.3" y="50.8"/><use href="#usst" x="71.3" y="56.2"/><use href="#usst" x="84.0" y="56.2"/><use href="#usst" x="96.7" y="56.2"/><use href="#usst" x="109.3" y="56.2"/><use href="#usst" x="122.0" y="56.2"/><use href="#usst" x="134.7" y="56.2"/><use href="#usst" x="77.7" y="61.5"/><use href="#usst" x="90.3" y="61.5"/><use href="#usst" x="103.0" y="61.5"/><use href="#usst" x="115.7" y="61.5"/><use href="#usst" x="128.3" y="61.5"/><use href="#usst" x="71.3" y="66.9"/><use href="#usst" x="84.0" y="66.9"/><use href="#usst" x="96.7" y="66.9"/><use href="#usst" x="109.3" y="66.9"/><use href="#usst" x="122.0" y="66.9"/><use href="#usst" x="134.7" y="66.9"/><use href="#usst" x="77.7" y="72.3"/><use href="#usst" x="90.3" y="72.3"/><use href="#usst" x="103.0" y="72.3"/><use href="#usst" x="115.7" y="72.3"/><use href="#usst" x="128.3" y="72.3"/><use href="#usst" x="71.3" y="77.7"/><use href="#usst" x="84.0" y="77.7"/><use href="#usst" x="96.7" y="77.7"/><use href="#usst" x="109.3" y="77.7"/><use href="#usst" x="122.0" y="77.7"/><use href="#usst" x="134.7" y="77.7"/><use href="#usst" x="77.7" y="83.1"/><use href="#usst" x="90.3" y="83.1"/><use href="#usst" x="103.0" y="83.1"/><use href="#usst" x="115.7" y="83.1"/><use href="#usst" x="128.3" y="83.1"/><use href="#usst" x="71.3" y="88.5"/><use href="#usst" x="84.0" y="88.5"/><use href="#usst" x="96.7" y="88.5"/><use href="#usst" x="109.3" y="88.5"/><use href="#usst" x="122.0" y="88.5"/><use href="#usst" x="134.7" y="88.5"/><rect x="65" y="40" width="190" height="100" fill="none" stroke="#D8D2C4" stroke-width="2"/>`
};

/* =========================================================
   단원 데이터 — 새 단원은 UNITS 배열에 같은 형식으로 덧붙이면 됩니다.
   items: { de 독일어, kr 한글 발음, ko 뜻, tip 발음 요령, img 그림 이름 }
   img 에 쓸 수 있는 그림 이름은 위 SCENES 목록에 있습니다.
   ========================================================= */
const UNITS = [
{
  id:"K2",
  title:"Lektion 2. Guten Tag!",
  goals:[
    "만나고 헤어질 때 독일어로 인사할 수 있다.",
    "안부를 묻고 답할 수 있다.",
    "자기소개를 할 수 있다."
  ],
  notes:[
    "du는 친구·가족에게, Sie는 처음 만난 사람이나 격식을 차리는 자리에서 씁니다. 존칭 Sie는 언제나 첫 글자를 대문자로 씁니다.",
    "대부분의 나라 이름은 관사 없이 aus만 붙입니다. 여성·남성·복수 국명은 관사가 붙습니다. aus der Schweiz, aus dem Iran, aus den USA."
  ],
  conj:{
    heads:["","sein (~이다)","heißen (이름이 ~이다)","kommen (오다)","wohnen (살다)"],
    rows:[
      ["ich","bin","heiße","komme","wohne"],
      ["du","bist","heißt","kommst","wohnst"],
      ["er/sie/es","ist","heißt","kommt","wohnt"],
      ["wir","sind","heißen","kommen","wohnen"],
      ["ihr","seid","heißt","kommt","wohnt"],
      ["sie/Sie","sind","heißen","kommen","wohnen"]
    ]
  },
  sections:[
  {
    name:"A. 하루의 때",
    items:[
      { de:"Morgen", kr:"모르겐", ko:"아침", tip:"r은 혀를 굴리지 않고 목젖에서 냅니다. '모어겐'에 가깝게 들려요.", img:"morgen" },
      { de:"Tag", kr:"타크", ko:"낮, 하루", tip:"끝의 g는 [k] 소리로 바뀝니다. '타그'가 아니라 '타크'.", img:"tag" },
      { de:"Abend", kr:"아벤트", ko:"저녁", tip:"a를 길게 끌고, 끝의 d는 [t]로 발음합니다.", img:"abend" },
      { de:"Nacht", kr:"나흐트", ko:"밤", tip:"ch는 목 안쪽에서 긁어내는 소리입니다. 'ㅋ'보다 부드럽게.", img:"nacht" }
    ]
  },
  {
    name:"B. 인사하기",
    items:[
      { de:"Hallo!", kr:"할로", ko:"안녕!", tip:"h를 숨 내쉬듯 확실히 내고 뒤의 o를 길게 끕니다.", img:"hallo" },
      { de:"Guten Morgen!", kr:"구텐 모르겐", ko:"안녕하세요! (아침 인사)", tip:"아침에 일어나서 오전 10시쯤까지 씁니다.", img:"morgen" },
      { de:"Guten Tag!", kr:"구텐 타크", ko:"안녕하세요! (낮 인사)", tip:"낮부터 오후 5~6시 전까지 쓰는 인사입니다.", img:"handschlag" },
      { de:"Guten Abend!", kr:"구텐 아벤트", ko:"안녕하세요! (저녁 인사)", tip:"저녁에 만났을 때 쓰는 인사입니다.", img:"abend" },
      { de:"Gute Nacht!", kr:"구테 나흐트", ko:"잘 자!", tip:"Gute에 n이 없습니다. 자러 갈 때만 씁니다.", img:"nacht" },
      { de:"Tschüs!", kr:"츄스", ko:"잘 가!", tip:"tsch를 한 덩어리 [츄]로. ü는 입술을 동그랗게 모은 채 '이'.", img:"abschied" },
      { de:"Auf Wiedersehen!", kr:"아우프 비더제엔", ko:"안녕히 가세요.", tip:"W는 [v], -sehen의 s는 성대가 울리는 [z] 소리입니다.", img:"abschied" },
      { de:"Ciao!", kr:"챠오", ko:"안녕! (헤어질 때)", tip:"이탈리아어에서 온 말로 젊은 사람들이 즐겨 씁니다.", img:"hallo" }
    ]
  },
  {
    name:"C. 안부 묻고 답하기",
    items:[
      { de:"Wie geht es dir?", kr:"비 게트 에스 디어", ko:"어떻게 지내? (친구에게)", tip:"w는 [v]. '위'가 아니라 '비'로 시작합니다. dir의 r은 약한 '어'.", img:"frage" },
      { de:"Wie geht es Ihnen?", kr:"비 게트 에스 이넨", ko:"어떻게 지내세요? (존댓말)", tip:"Ihnen의 h는 소리 내지 않고 앞의 i를 길게 늘입니다.", img:"handschlag" },
      { de:"Es geht mir gut.", kr:"에스 게트 미어 구트", ko:"잘 지내.", tip:"mir는 '나에게'라는 뜻입니다. u를 길게 끌어 '구－트'.", img:"gesicht_gut" },
      { de:"Es geht mir sehr gut.", kr:"에스 게트 미어 제어 구트", ko:"아주 잘 지내.", tip:"sehr의 s는 [z], h는 소리 없이 e를 길게 늘입니다.", img:"gesicht_sehrgut" },
      { de:"Es geht mir nicht gut.", kr:"에스 게트 미어 니히트 구트", ko:"잘 못 지내.", tip:"nicht의 ch는 목이 아니라 혀 앞쪽에서 나는 바람 소리입니다.", img:"gesicht_nichtgut" },
      { de:"Es geht mir soso.", kr:"에스 게트 미어 조조", ko:"그냥 그래.", tip:"단어 첫머리의 s는 [z]. '소소'가 아니라 '조조'.", img:"gesicht_soso" },
      { de:"Mir geht es gut. Und dir?", kr:"미어 게트 에스 구트. 운트 디어?", ko:"난 잘 지내. 너는?", tip:"Und dir? 는 끝을 올려 물어봅니다.", img:"sprechen" },
      { de:"Sehr gut. Danke.", kr:"제어 구트. 당케.", ko:"아주 좋아. 고마워.", tip:"Danke의 a는 짧게 끊습니다.", img:"gesicht_sehrgut" }
    ]
  },
  {
    name:"D. 이름 말하기",
    items:[
      { de:"Hallo, ich bin Mia.", kr:"할로, 이히 빈 미아.", ko:"안녕, 나는 미아야.", tip:"ich의 ch는 '이크'가 아닙니다. 혀 앞쪽에서 내는 'ㅎ' 바람 소리예요.", img:"hallo" },
      { de:"Mein Name ist Leo.", kr:"마인 나메 이스트 레오.", ko:"내 이름은 레오야.", tip:"ei는 언제나 '아이'. '메인'이 아니라 '마인'.", img:"namensschild" },
      { de:"Ich heiße Mia Fischer.", kr:"이히 하이세 미아 피셔.", ko:"저는 미아 피셔입니다.", tip:"ß는 [s] 하나입니다. Fischer의 sch는 [슈].", img:"namensschild" },
      { de:"Wie heißt du?", kr:"비 하이스트 두?", ko:"이름이 뭐야?", tip:"du는 입술을 모아 '두－'. 끝을 올려 물어봅니다.", img:"frage" },
      { de:"Wie heißen Sie?", kr:"비 하이센 지?", ko:"성함이 어떻게 되십니까?", tip:"Sie의 s는 [z]. '시'가 아니라 '지'로 들립니다.", img:"handschlag" },
      { de:"Ich bin Schüler.", kr:"이히 빈 슐러", ko:"나는 (남)학생이야.", tip:"sch는 [슈], ü는 입술을 오므린 '이'. 끝의 -er는 약한 '어'.", img:"schueler" },
      { de:"Ich bin Schülerin.", kr:"이히 빈 슐러린", ko:"나는 (여)학생이야.", tip:"여학생은 뒤에 -in을 붙입니다.", img:"schueler" }
    ]
  },
  {
    name:"E. 출신지와 거주지",
    items:[
      { de:"Woher kommst du?", kr:"보헤어 콤스트 두?", ko:"너는 어디에서 왔니?", tip:"Woher는 뒤쪽에 힘을 줍니다. '보헤－어'.", img:"welt" },
      { de:"Woher kommen Sie?", kr:"보헤어 코멘 지?", ko:"어디서 오셨습니까?", tip:"존댓말 형태입니다. 끝의 -en은 약하게 흘립니다.", img:"welt" },
      { de:"Ich komme aus Korea.", kr:"이히 코메 아우스 코레아.", ko:"저는 한국에서 왔습니다.", tip:"Korea는 가운데에 힘을 줍니다. 코-레－아.", img:"flagge_kr" },
      { de:"Ich komme aus Deutschland.", kr:"이히 코메 아우스 도이츄란트.", ko:"저는 독일에서 왔습니다.", tip:"eu는 '오이', 끝의 d는 [t]. '도이츄란트'.", img:"flagge_de" },
      { de:"Ich komme aus Österreich.", kr:"이히 코메 아우스 외스터라이히.", ko:"저는 오스트리아에서 왔습니다.", tip:"ö는 '에' 입 모양에서 입술만 동그랗게 오므려 냅니다.", img:"flagge_at" },
      { de:"Ich komme aus der Schweiz.", kr:"이히 코메 아우스 데어 슈바이츠.", ko:"저는 스위스에서 왔습니다.", tip:"스위스는 여성 국명이라 aus 뒤에 der가 붙습니다.", img:"flagge_ch" },
      { de:"Wo wohnst du?", kr:"보 본스트 두?", ko:"너는 어디에 사니?", tip:"w가 두 번 나옵니다. 둘 다 [v]. '보 본스트'.", img:"stadt" },
      { de:"Ich wohne in Seoul.", kr:"이히 보네 인 제올.", ko:"저는 서울에 삽니다.", tip:"wohne의 h는 소리 없이 o를 길게 늘입니다.", img:"haus" },
      { de:"Ich wohne hier in Frankfurt.", kr:"이히 보네 히어 인 프랑크푸르트.", ko:"저는 여기 프랑크푸르트에 삽니다.", tip:"hier는 '히어'. Frankfurt의 r 두 개는 목젖에서 냅니다.", img:"haus" }
    ]
  },
  {
    name:"F. 나라 이름",
    items:[
      { de:"Deutschland", kr:"도이츄란트", ko:"독일", tip:"eu는 '오이', tsch는 [츄], 끝의 d는 [t].", img:"flagge_de" },
      { de:"Österreich", kr:"외스터라이히", ko:"오스트리아", tip:"끝의 ch는 ich의 ch와 같은 혀 앞쪽 바람 소리입니다.", img:"flagge_at" },
      { de:"die Schweiz", kr:"디 슈바이츠", ko:"스위스", tip:"sch는 [슈], w는 [v], z는 [ts]. 여성 국명이라 die가 붙습니다.", img:"flagge_ch" },
      { de:"Korea", kr:"코레아", ko:"한국", tip:"가운데 음절에 힘을 줍니다. 코-레－아.", img:"flagge_kr" },
      { de:"die Türkei", kr:"디 튀르카이", ko:"튀르키예", tip:"ü는 입술을 오므린 '이', ei는 '아이'.", img:"flagge_tr" },
      { de:"die USA", kr:"디 우-에스-아", ko:"미국", tip:"알파벳을 하나씩 읽습니다. 우-에스-아. 복수라 die가 붙습니다.", img:"flagge_us" }
    ]
  }
  ]
}
];

/* ================= 상태 ================= */
let ui=0, si=0, pi=0;
const rec={};
const $=(id)=>document.getElementById(id);
const unit=()=>UNITS[ui];
const sect=()=>unit().sections[si];
const item=()=>sect().items[pi];
function store(){ return rec[unit().id] || (rec[unit().id]={}); }
function esc(s){ return String(s).replace(/[&<>]/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;"}[c])); }

/* ================= 음성 출력 ================= */
let deVoice=null;
function pickVoice(){
  const vs=window.speechSynthesis?speechSynthesis.getVoices():[];
  deVoice=vs.find(v=>/^de/i.test(v.lang))||null;
  if(!deVoice && vs.length){
    $("notice").innerHTML="<b>독일어 음성이 없습니다</b> — 이 기기에 독일어 읽어주기 음성이 없어요. 크롬이나 엣지에서 열면 대부분 해결됩니다.";
  }
}
if(window.speechSynthesis){ pickVoice(); speechSynthesis.onvoiceschanged=pickVoice; }
function say(text, rate){
  if(!window.speechSynthesis) return;
  speechSynthesis.cancel();
  const u=new SpeechSynthesisUtterance(text);
  u.lang="de-DE"; u.rate=rate||0.95;
  if(deVoice) u.voice=deVoice;
  speechSynthesis.speak(u);
}

/* ================= 채점 ================= */
function norm(s){
  let t=s.toLowerCase()
    .replace(/[’'´`]/g,"")
    .replace(/ß/g,"ss")
    .replace(/[^\p{L}\p{N}\s]/gu," ")
    .replace(/\s+/g," ").trim();
  t=t.replace(/\bgeht es\b/g,"gehts").replace(/\bwie gehts\b/g,"wie geht es");
  return t.replace(/ss/g,"s");
}
function lev(a,b){
  const n=a.length,m=b.length;
  if(!n) return m;
  if(!m) return n;
  let prev=Array.from({length:m+1},(_,j)=>j), cur=new Array(m+1);
  for(let i=1;i<=n;i++){
    cur[0]=i;
    for(let j=1;j<=m;j++) cur[j]=Math.min(prev[j]+1,cur[j-1]+1,prev[j-1]+(a[i-1]===b[j-1]?0:1));
    const t=prev; prev=cur; cur=t;
  }
  return prev[m];
}
function fold(s){ return s.replace(/ä/g,"a").replace(/ö/g,"o").replace(/ü/g,"u"); }
function wordSim(a,b){
  if(a===b) return 1;
  const d=lev(a,b);
  let sim=Math.max(0,1-d/Math.max(a.length,b.length));
  if(sim>0.7 && fold(a)===fold(b)) sim=0.7;
  return sim;
}
function align(T,H){
  const n=T.length,m=H.length;
  const D=Array.from({length:n+1},()=>new Array(m+1).fill(0));
  const P=Array.from({length:n+1},()=>new Array(m+1).fill(null));
  for(let i=1;i<=n;i++){ D[i][0]=i; P[i][0]="del"; }
  for(let j=1;j<=m;j++){ D[0][j]=j; P[0][j]="ins"; }
  for(let i=1;i<=n;i++) for(let j=1;j<=m;j++){
    const sub=D[i-1][j-1]+(1-wordSim(T[i-1],H[j-1]));
    const del=D[i-1][j]+1, ins=D[i][j-1]+1;
    const best=Math.min(sub,del,ins);
    D[i][j]=best;
    P[i][j]= best===sub?"sub":(best===del?"del":"ins");
  }
  const sims=new Array(n).fill(0);
  let i=n,j=m;
  while(i>0||j>0){
    const p=P[i][j];
    if(p==="sub"){ sims[i-1]=wordSim(T[i-1],H[j-1]); i--; j--; }
    else if(p==="del"){ sims[i-1]=0; i--; }
    else { j--; }
  }
  return sims;
}
function grade(target,heard){
  const T=norm(target).split(" ").filter(Boolean);
  const H=norm(heard).split(" ").filter(Boolean);
  const sims=align(T,H);
  let num=0,den=0;
  T.forEach((w,k)=>{ num+=sims[k]*w.length; den+=w.length; });
  return { score: den?Math.round(100*num/den):0, sims:sims, words:T };
}

/* ================= 화면 ================= */
function drawUnits(){
  const sel=$("unitSel"); sel.innerHTML="";
  UNITS.forEach((u,k)=>{
    const o=document.createElement("option");
    o.value=k; o.textContent=u.title; sel.appendChild(o);
  });
  sel.value=ui;
  sel.onchange=()=>{ ui=+sel.value; si=0; pi=0; drawInfo(); drawTabs(); draw(); };
}
function drawInfo(){
  const u=unit();
  let h="<h3>학습 목표</h3><ul>"+u.goals.map(g=>"<li>"+esc(g)+"</li>").join("")+"</ul>";
  if(u.conj){
    h+="<h3>동사의 어미 변화</h3><table class='gram'><tr>"+
       u.conj.heads.map(x=>"<th class='de'>"+esc(x)+"</th>").join("")+"</tr>";
    u.conj.rows.forEach(r=>{
      h+="<tr><td class='p de'>"+esc(r[0])+"</td>"+
         r.slice(1).map(x=>"<td class='v de'>"+esc(x)+"</td>").join("")+"</tr>";
    });
    h+="</table>";
  }
  if(u.notes && u.notes.length){
    h+="<h3>알아두기</h3><ul>"+u.notes.map(n=>"<li>"+esc(n)+"</li>").join("")+"</ul>";
  }
  $("unitInfoBody").innerHTML=h;
}
function drawTabs(){
  const nav=$("tabs"); nav.innerHTML="";
  unit().sections.forEach((s,k)=>{
    const b=document.createElement("button");
    b.textContent=s.name;
    b.setAttribute("aria-pressed",k===si?"true":"false");
    b.onclick=()=>{ si=k; pi=0; drawTabs(); draw(); };
    nav.appendChild(b);
  });
}
function drawPic(){
  const key=item().img;
  $("pic").innerHTML = SCENES[key] || SCENES.sprechen;
  $("pic").setAttribute("aria-label", item().ko+" 그림");
}
function drawPhrase(sims){
  const p=$("phrase"); p.innerHTML="";
  const raw=item().de.split(" ");
  const clean=norm(item().de).split(" ").filter(Boolean);
  raw.forEach((w,k)=>{
    const s=document.createElement("span");
    s.className="w"; s.textContent=w; s.tabIndex=0; s.title="이 단어만 듣기";
    s.onclick=()=>say(w.replace(/[?!.,]/g,""),0.8);
    s.onkeydown=(e)=>{ if(e.key==="Enter"||e.key===" "){ e.preventDefault(); s.click(); } };
    if(sims && k<clean.length) s.classList.add(sims[k]>=0.8?"g":sims[k]>=0.5?"a":"b");
    p.appendChild(s);
    if(k<raw.length-1) p.appendChild(document.createTextNode(" "));
  });
}
function drawDots(){
  const d=$("dots"); d.innerHTML="";
  sect().items.forEach((_,k)=>{
    const i=document.createElement("i");
    const r=store()[si+"-"+k];
    if(r) i.classList.add(r.b>=70?"done":"retry");
    if(k===pi) i.classList.add("now");
    d.appendChild(i);
  });
}
function draw(){
  const it=item();
  drawPic();
  drawPhrase(null);
  $("kr").textContent=it.kr;
  $("meaning").textContent=it.ko;
  $("tip").innerHTML="<b>발음</b> "+esc(it.tip);
  $("count").textContent=sect().name+" · "+(pi+1)+" / "+sect().items.length;
  $("bar").style.width=Math.round(100*(pi+1)/sect().items.length)+"%";
  $("result").classList.remove("on");
  $("prev").disabled=pi===0;
  $("next").disabled=pi===sect().items.length-1;
  drawDots();
}
function showResult(best){
  const it=item();
  const g=grade(it.de,best);
  drawPhrase(g.sims);
  const tier=g.score>=88?"g":g.score>=70?"a":"b";
  $("score").textContent=g.score;
  $("score").className="score "+tier;
  $("verdictText").textContent =
      g.score>=88 ? "아주 좋아요. 독일 사람이 알아들을 발음이에요."
    : g.score>=70 ? "잘했어요. 몇 군데만 다듬으면 됩니다."
    : g.score>=45 ? "조금만 더. 천천히 한 번 듣고 다시 해볼까요."
    :               "다시 해봅시다. 천천히 듣기부터 시작하세요.";
  $("heard").innerHTML="들린 문장: <b>"+esc(best||"(소리가 잡히지 않았어요)")+"</b>";
  let worst=-1, low=1;
  g.sims.forEach((s,k)=>{ if(s<low){ low=s; worst=k; } });
  $("coach").innerHTML="";
  if(worst>=0 && low<0.8){
    const b=document.createElement("button");
    b.className="again";
    b.textContent="‘"+g.words[worst]+"’ 다시 듣기";
    b.onclick=()=>say(g.words[worst],0.75);
    $("coach").appendChild(b);
  }
  const s=store(), k=si+"-"+pi, old=s[k];
  s[k]={ b: old?Math.max(old.b,g.score):g.score, t:(old?old.t:0)+1 };
  drawDots();
  $("result").classList.add("on");
}

/* ================= 음성 인식 ================= */
const SR=window.SpeechRecognition||window.webkitSpeechRecognition;
let listening=false, timer=null;
function listen(){
  if(!SR){
    $("notice").innerHTML="<b>이 브라우저는 음성인식을 지원하지 않습니다</b> — 크롬이나 엣지에서 열어 주세요. 그전까지는 듣기 기능으로 따라 읽으며 연습할 수 있어요.";
    return;
  }
  if(listening) return;
  if(window.speechSynthesis) speechSynthesis.cancel();
  const r=new SR();
  r.lang="de-DE"; r.interimResults=false; r.maxAlternatives=5;
  const btn=$("rec");
  listening=true; btn.classList.add("rec"); btn.textContent="● 듣는 중… 지금 말하세요";
  const reset=()=>{ listening=false; btn.classList.remove("rec"); btn.textContent="🎤 따라 말하기"; clearTimeout(timer); };
  r.onresult=(e)=>{
    const alts=e.results[0];
    let best="", bestScore=-1;
    for(let k=0;k<alts.length;k++){
      const t=alts[k].transcript, s=grade(item().de,t).score;
      if(s>bestScore){ bestScore=s; best=t; }
    }
    reset(); showResult(best.trim());
  };
  r.onerror=(e)=>{
    reset();
    const msg={
      "not-allowed":"마이크 권한이 꺼져 있습니다. 주소창의 자물쇠 아이콘에서 마이크를 허용해 주세요.",
      "service-not-allowed":"이 화면에서는 마이크를 쓸 수 없습니다. 파일을 인터넷 주소로 열면 동작합니다.",
      "no-speech":"소리가 잡히지 않았어요. 마이크에 조금 더 가까이서 다시 말해 보세요.",
      "audio-capture":"마이크를 찾지 못했습니다. 기기에 마이크가 연결되어 있는지 확인해 주세요.",
      "network":"음성인식 서버에 연결하지 못했습니다. 인터넷 연결을 확인해 주세요."
    }[e.error]||("음성인식이 중단되었습니다. ("+e.error+") 다시 시도해 주세요.");
    $("notice").innerHTML="<b>안내</b> — "+msg;
  };
  r.onend=reset;
  try{ r.start(); }catch(err){ reset(); }
  timer=setTimeout(()=>{ try{ r.stop(); }catch(err){} },8000);
}

/* ================= 이벤트 ================= */
$("play").onclick=()=>say(item().de,0.95);
$("slow").onclick=()=>say(item().de,0.6);
$("rec").onclick=listen;
$("prev").onclick=()=>{ if(pi>0){ pi--; draw(); } };
$("next").onclick=()=>{ if(pi<sect().items.length-1){ pi++; draw(); } };
document.addEventListener("keydown",(e)=>{
  const tag=e.target.tagName;
  if(tag==="INPUT"||tag==="TEXTAREA"||tag==="SELECT") return;
  if(e.key==="ArrowRight") $("next").click();
  else if(e.key==="ArrowLeft") $("prev").click();
  else if(e.key==="Enter"){ e.preventDefault(); listen(); }
});

drawUnits(); drawInfo(); drawTabs(); draw();
</script>
</body>
</html>
