# 6주차 실습 가이드

<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>교육 자료 · 6회차</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Nanum+Gothic:wght@400;700;800&family=Nanum+Gothic+Coding:wght@400;700&display=swap">
<style>
:root{
  --ground:#ffffff;
  --surface:#f6f8fb;
  --surface-2:#eceff4;
  --line:#dde1e8;
  --ink:#141c28;
  --ink-soft:#5c6675;
  --accent:#1b3252;
  --accent-deep:#0e1f38;
  --accent-soft:#e5eaf2;
  --mark-ink:#8a5206;
  --mark-bg:#fdf1dd;
  --mark-line:#e8c691;
  --ok:#1a6b48;
  --radius:14px;
  --step:1;
}
@media (prefers-color-scheme: dark){
  :root:not([data-theme="light"]){
    --ground:#12161d;--surface:#1a2029;--surface-2:#222a35;--line:#333d4b;
    --ink:#e8ecf2;--ink-soft:#a3aec0;--accent:#3d6aa3;--accent-deep:#5c8bc4;
    --accent-soft:#232f42;--mark-ink:#f2c684;--mark-bg:#3a2c14;--mark-line:#6b5124;--ok:#5cbd91;
  }
}
*{box-sizing:border-box}
body{
  margin:0;background:var(--ground);color:var(--ink);
  font-family:"Pretendard Variable","Pretendard","Nanum Gothic","Apple SD Gothic Neo","Malgun Gothic",sans-serif;
  font-size:calc(17px * var(--step));line-height:1.75;-webkit-text-size-adjust:100%;
}
.wrap{max-width:840px;margin:0 auto;padding:0 20px 80px}
.masthead{padding:44px 0 26px;border-bottom:2px solid var(--line)}
.eyebrow{font-size:.82em;font-weight:700;letter-spacing:.14em;color:var(--accent);margin:0 0 10px}
h1{font-size:2.1em;font-weight:800;line-height:1.25;margin:0 0 12px;letter-spacing:-.01em}
.lede{margin:0;color:var(--ink-soft);font-size:1.02em}
.lede strong{color:var(--ink)}
.toolbar{position:sticky;top:0;z-index:20;background:var(--ground);border-bottom:1px solid var(--line);padding:10px 0;margin-bottom:8px}
.toolbar-inner{max-width:840px;margin:0 auto;padding:0 20px;display:flex;flex-wrap:wrap;gap:10px;align-items:center}
.jump{display:flex;gap:6px;flex-wrap:nowrap;flex:1 1 0;min-width:0;overflow-x:auto;scrollbar-width:none}
.jump::-webkit-scrollbar{display:none}
.toolbar-inner{flex-wrap:nowrap}
.jump a{flex:0 0 auto;padding:7px 13px;border-radius:999px;background:var(--surface);color:var(--ink-soft);text-decoration:none;font-size:.86em;font-weight:700;border:1px solid transparent;white-space:nowrap}
.jump a:hover,.jump a:focus-visible{background:var(--accent-soft);color:var(--accent-deep);border-color:var(--accent)}
.sizer{display:flex;align-items:center;gap:7px;flex:0 0 auto}
.sizer span{font-size:.82em;color:var(--ink-soft);font-weight:700}
.sizer button{width:38px;height:38px;border-radius:9px;border:1px solid var(--line);background:var(--surface);color:var(--ink);font-family:inherit;font-weight:800;cursor:pointer;font-size:1em;line-height:1}
section{margin-top:52px;scroll-margin-top:76px}
.sec-head{display:flex;align-items:baseline;gap:12px;margin-bottom:6px}
.sec-num{font-family:"Nanum Gothic Coding",monospace;font-size:1.5em;font-weight:700;color:var(--accent)}
h2{font-size:1.5em;font-weight:800;margin:0;letter-spacing:-.01em}
.sec-note{margin:0 0 22px;color:var(--ink-soft)}
.sub{font-size:1.18em;font-weight:800;margin:34px 0 12px;color:var(--accent-deep)}
.card{background:var(--surface);border:1px solid var(--line);border-radius:var(--radius);padding:22px 22px 20px;margin-bottom:18px}
.card h3{font-size:1.14em;font-weight:800;margin:0 0 8px}
.card p{margin:0 0 14px;color:var(--ink-soft)}
.card strong{color:var(--ink)}
pre{
  margin:0 0 14px;
  background:#1a2029 !important;
  color:#e8ecf2 !important;
  border:1px solid #333d4b;
  border-radius:10px;
  padding:18px;
  font-family:"Nanum Gothic Coding","D2Coding",monospace;
  font-size:.98em;
  line-height:1.85;
  white-space:pre-wrap;
  word-break:break-word;
  overflow-x:auto;
}
.ph{color:var(--mark-ink);font-weight:700;background:var(--mark-bg);box-shadow:inset 0 0 0 1px var(--mark-line);border-radius:4px;padding:1px 4px}
pre .ph{color:#f2c684;background:#3a2c14;box-shadow:inset 0 0 0 1px #6b5124}
button.copy{display:flex;align-items:center;justify-content:center;gap:9px;width:100%;min-height:58px;border:none;border-radius:10px;background:var(--accent);color:#fff;font-family:inherit;font-size:1.05em;font-weight:800;cursor:pointer}
button.copy:hover{background:var(--accent-deep)}
button.copy.done{background:var(--ok)}
button.copy .ico{font-family:"Nanum Gothic Coding",monospace;font-weight:700}
.chips{display:grid;gap:10px}
@media(min-width:620px){.chips{grid-template-columns:1fr 1fr}}
.chips.one{grid-template-columns:1fr}
button.chip{display:flex;align-items:center;justify-content:space-between;gap:10px;min-height:56px;padding:12px 16px;border:1px solid var(--line);border-radius:10px;background:var(--ground);color:var(--ink);font-family:"Nanum Gothic Coding",monospace;font-size:.96em;font-weight:700;text-align:left;cursor:pointer}
button.chip:hover{border-color:var(--accent);background:var(--accent-soft)}
button.chip.done{background:var(--ok);color:#fff;border-color:var(--ok)}
button.chip .tag{font-family:inherit;font-size:.82em;font-weight:700;opacity:.65;flex:0 0 auto}
.note{display:flex;gap:11px;background:var(--surface-2);border-radius:10px;padding:13px 15px;font-size:.94em;color:var(--ink-soft);margin-top:14px}
.note b{flex:0 0 auto;font-weight:800;color:var(--accent-deep)}
.note p{margin:0;color:inherit}
ol.steps{margin:0;padding:0;list-style:none;counter-reset:s}
ol.steps li{counter-increment:s;display:flex;gap:14px;align-items:flex-start;padding:11px 0;border-bottom:1px solid var(--line)}
ol.steps li:last-child{border-bottom:none}
ol.steps li::before{content:counter(s);flex:0 0 auto;width:30px;height:30px;border-radius:50%;background:var(--accent);color:#fff;font-family:"Nanum Gothic Coding",monospace;font-weight:700;display:flex;align-items:center;justify-content:center;font-size:.9em;margin-top:2px}
ol.steps b{font-weight:800}
.mlabel{display:block;font-weight:800;font-size:.9em;color:var(--accent-deep);margin:0 0 6px}
details.more{margin-top:16px;background:var(--ground);border:1px solid var(--line);border-radius:10px;overflow:hidden}
details.more summary{padding:15px 18px;font-weight:800;cursor:pointer;list-style:none;display:flex;justify-content:space-between;align-items:center}
details.more summary::-webkit-details-marker{display:none}
details.more summary::after{content:'＋';font-weight:800;color:var(--accent)}
details.more[open] summary{border-bottom:1px solid var(--line)}
details.more[open] summary::after{content:'－'}
.more-body{padding:16px 18px 18px}
.linkbtn{display:flex;align-items:center;justify-content:center;min-height:58px;border-radius:10px;margin:0 0 16px;background:var(--accent);color:#fff;font-weight:800;font-size:1.05em;text-decoration:none;text-align:center;padding:8px 14px}
.linkbtn:hover{background:var(--accent-deep)}
.banner{display:flex;flex-wrap:wrap;gap:8px 16px;align-items:center;background:var(--surface-2);border-radius:var(--radius);padding:16px 20px;margin-top:24px}
.banner .label{font-weight:800;font-size:.9em;color:var(--accent-deep)}
.banner .addr{font-family:"Nanum Gothic Coding",monospace;font-weight:700;font-size:1.08em}
/* 표 */
.tbl{width:100%;border-collapse:collapse;font-size:.95em;background:var(--ground);border-radius:10px;overflow:hidden}
.tbl th,.tbl td{border-bottom:1px solid var(--line);padding:10px 12px;text-align:left;vertical-align:top}
.tbl th{background:var(--accent-soft);color:var(--accent-deep);font-weight:800}
.tbl tr:last-child td{border-bottom:none}
.tbl td:first-child{font-weight:800;white-space:nowrap}
.tbl-wrap{overflow-x:auto;border:1px solid var(--line);border-radius:10px}
/* 퇴고: 이렇게 말하면 → 이렇게 */
.swap{display:grid;gap:6px;margin-bottom:12px}
.swap .before{font-size:.92em;color:var(--ink-soft);font-weight:700}
.swap .before s{opacity:.8}
/* 체크리스트 */
ul.check{list-style:none;margin:0;padding:0}
ul.check li{display:flex;gap:12px;align-items:flex-start;padding:10px 0;border-bottom:1px solid var(--line)}
ul.check li:last-child{border-bottom:none}
ul.check input{width:22px;height:22px;margin-top:4px;flex:0 0 auto;accent-color:var(--ok)}
ul.check label{cursor:pointer}
/* QR */
.qr-row{display:flex;flex-wrap:wrap;gap:10px}
.qr-row input{flex:1 1 240px;min-height:52px;padding:12px;border:1px solid var(--line);border-radius:10px;background:var(--ground);color:var(--ink);font-family:inherit;font-size:1em}
.qr-row button{min-height:52px;padding:0 20px;border:none;border-radius:10px;background:var(--accent);color:#fff;font-family:inherit;font-weight:800;font-size:1em;cursor:pointer}
#qrcode{margin-top:18px}
#qrcode img,#qrcode canvas{background:#fff;padding:10px;border-radius:8px}
footer{margin-top:60px;padding-top:22px;border-top:1px solid var(--line);color:var(--ink-soft);font-size:.9em}
@media (prefers-reduced-motion: no-preference){
  button.copy,button.chip{transition:background .15s ease,border-color .15s ease}
}
/* ── 6회차 추가 ── */
.flow{display:flex;flex-wrap:wrap;gap:6px;margin:0 0 18px;padding:0;list-style:none}
.flow li{padding:6px 12px;border-radius:999px;background:var(--surface-2);color:var(--ink-soft);font-weight:800;font-size:.86em}
.flow li.on{background:var(--accent);color:#fff}
.answer{display:flex;gap:11px;background:var(--mark-bg);border:1px solid var(--mark-line);border-radius:10px;padding:13px 15px;font-size:.94em;margin-top:14px}
.answer b{flex:0 0 auto;font-weight:800;color:var(--mark-ink)}
.answer p{margin:0;color:var(--ink)}
.answer strong{color:var(--mark-ink)}
.qa{margin:0 0 12px}
.qa dt{font-weight:800;margin-top:12px}
.qa dd{margin:4px 0 0;color:var(--ink-soft)}
</style>
</head>
<body>


<div class="toolbar">
  <div class="toolbar-inner">
    <nav class="jump" aria-label="바로가기">
      <a href="#s0">0 시작하기</a>
      <a href="#s1">1 데이터 분석</a>
      <a href="#s2">2 AI 윤리</a>
      <a href="#s3">3 주제·마스코트</a>
      <a href="#s4">4 만들기 코스</a>
      <a href="#s5">5 점검·공유</a>
    </nav>
    <div class="sizer">
      <span>글자</span>
      <button type="button" id="smaller" aria-label="글자 작게">－</button>
      <button type="button" id="bigger" aria-label="글자 크게">＋</button>
    </div>
  </div>
</div>

<div class="wrap">

<header class="masthead">
  <p class="eyebrow">교육 프로그램 · 6회차 (마지막 시간)</p>
  <h1>AI와 일상, AI와 업무</h1>
  <p class="lede">오늘 쓸 프롬프트가 순서대로 담겨 있습니다. <strong>복사하기 버튼</strong>을 누르면 문장이 복사되고, <span class="ph">[노란 칸]</span>만 내 이야기로 바꾸면 됩니다.</p>
</header>

<!-- ───────────── 0. 시작하기 ───────────── -->
<section id="s0">
  <div class="sec-head"><span class="sec-num">0</span><h2>시작하기</h2></div>
  <p class="sec-note">프롬프트 쓰는 방법과 오늘 실습에서 계속 쓰는 질문 4가지입니다.</p>

  <div class="card">
    <h3>프롬프트 쓰는 순서</h3>
    <ol class="steps">
      <li><span><b>복사하기</b> 버튼을 누릅니다.</span></li>
      <li><span>AI 대화창(Gemini)을 누르고 <b>Ctrl + V</b>로 붙여넣습니다.</span></li>
      <li><span><b>[대괄호]</b> 안의 글자를 지우고 내 내용을 씁니다. 대괄호 기호도 함께 지웁니다.</span></li>
      <li><span><b>엔터</b>를 누르고 AI의 답을 기다립니다.</span></li>
    </ol>
    <div class="note"><b>TIP</b><p>타자가 힘들 때는 대화창의 마이크 모양 버튼을 눌러 말로 입력해 보세요.</p></div>
  </div>

  <div class="card">
    <h3>데이터에 던지는 질문 4가지</h3>
    <p><strong>데이터</strong>는 기록해 둔 사실과 숫자, <strong>분석</strong>은 그 기록에 질문을 던져 답을 찾는 것입니다.</p>
    <div class="tbl-wrap">
      <table class="tbl">
        <tr><th>질문</th><th>예시</th><th>어울리는 그래프</th></tr>
        <tr><td>① 얼마나?</td><td>"이번 달 총 얼마 썼지?" (합계·평균)</td><td>숫자 하나</td></tr>
        <tr><td>② 무엇이 제일?</td><td>"어떤 메뉴가 제일 잘 팔렸지?" (순위)</td><td>막대그래프</td></tr>
        <tr><td>③ 어떻게 변했나?</td><td>"몇 달 사이 늘었나, 줄었나?" (추이)</td><td>꺾은선그래프</td></tr>
        <tr><td>④ 무엇과 다른가?</td><td>"주말과 평일은 다를까?" (비교)</td><td>막대그래프</td></tr>
      </table>
    </div>

    <details class="more">
      <summary>AI와 나의 역할 나누기</summary>
      <div class="more-body">
        <div class="tbl-wrap">
          <table class="tbl">
            <tr><th>누가</th><th>하는 일</th></tr>
            <tr><td>AI</td><td>찾기(필요한 기록 골라내기) · 계산(합계·평균·순위) · 정리(표로 묶기) · 그래프 그리기</td></tr>
            <tr><td>나</td><td>질문하기(무엇을 물을지) · 확인하기(결과가 맞는지) · 결론 내리기(무엇을 할지)</td></tr>
          </table>
        </div>
        <div class="note"><b>확인 요령</b><p>원래 표의 숫자 한두 개를 직접 맞춰 보고, 상식과 맞는지 살펴보세요.</p></div>
      </div>
    </details>
  </div>
</section>

<!-- ───────────── 1. 데이터 분석 ───────────── -->
<section id="s1">
  <div class="sec-head"><span class="sec-num">1</span><h2>실습 1. 우리 집 가계부 6개월 돌아보기</h2></div>
  <p class="sec-note">5월부터 10월까지 6개월치, 256줄짜리 가계부입니다. "반년 동안 우리 집 돈은 어디로, 언제, 얼마나 나갔을까?"를 질문 4가지로 하나씩 풀어 봅니다. ※ 설명을 위한 가상의 가계부입니다.</p>

  <a class="linkbtn" href="가계부_5월-10월.xlsx" download>실습 파일 내려받기 (가계부_5월-10월.xlsx)</a>

  <h3 class="sub">넣기 · 읽기</h3>
  <ul class="flow"><li class="on">넣기</li><li class="on">읽기</li><li>질문</li><li>확인</li><li>결론</li></ul>

  <div class="card">
    <h3>파일 올리고 어떤 표인지 듣기</h3>
    <ol class="steps">
      <li><span>위 버튼으로 <b>가계부_5월-10월.xlsx</b>를 내려받습니다.</span></li>
      <li><span>Gemini 대화창 왼쪽 <b>＋</b>를 눌러 파일을 올립니다. (다운로드 폴더에서 선택)</span></li>
      <li><span>아래 프롬프트를 붙여넣고 보냅니다.</span></li>
    </ol>
  </div>

  <div class="card">
    <pre data-copy>올린 파일은 우리 집 5월부터 10월까지의 가계부야. 아직 계산은 하지 말고, 이 표가 어떤 내용인지 세 줄로 쉽게 설명해줘.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="answer"><b>이 말이 나오면 성공</b><p><strong>6개월</strong> · 날짜·요일·분류·내용·금액 · 식비·공과금 등 <strong>6가지 분류</strong></p></div>
  </div>

  <h3 class="sub">질문 ① 얼마나? — 숫자 하나</h3>
  <ul class="flow"><li>넣기</li><li>읽기</li><li class="on">질문</li><li>확인</li><li>결론</li></ul>

  <div class="card">
    <h3>6개월 동안 모두 얼마 썼을까?</h3>
    <pre data-copy>6개월 동안 모두 얼마를 썼는지, 한 달 평균은 얼마인지 알려줘. 큰 숫자로 한눈에 보이게 정리해줘.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="answer"><b>확인 포인트</b><p>6개월 총지출 <strong>862만 원</strong> · 한 달 평균 <strong>약 144만 원</strong></p></div>
  </div>

  <h3 class="sub">질문 ② 무엇이 제일? — 막대그래프</h3>

  <div class="card">
    <h3>어디에 가장 많이 썼을까?</h3>
    <pre data-copy>분류별로 얼마를 썼는지 많은 순서대로 표로 정리하고, 막대그래프로 그려줘.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="answer"><b>확인 포인트</b><p>① 식비 약 327만 원 ② 공과금 241만 원 ③ 교통 126만 원 ④ 문화 101만 원 ⑤ 의료 41만 원 ⑥ 선물·경조사 26만 원</p></div>
    <span class="mlabel" style="margin-top:16px">더 물어보기</span>
    <div class="chips one"><button class="chip" type="button" data-copy="한 번에 가장 많이 쓴 기록은 뭐야?">한 번에 가장 많이 쓴 기록은 뭐야?<span class="tag">복사</span></button></div>
    <div class="note"><b>살펴보기</b><p>한 건 1위는 8월 관리비 20만 원. 합계 1위(식비)와 다릅니다.</p></div>
  </div>

  <h3 class="sub">질문 ③ 어떻게 변했나? — 꺾은선그래프</h3>

  <div class="card">
    <h3>여섯 달 동안 어떻게 변했을까?</h3>
    <pre data-copy>월별 총지출을 구해서 5월부터 10월까지 꺾은선그래프로 그려줘. 가장 많이 쓴 달은 왜 많았는지도 알려줘.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="answer"><b>확인 포인트</b><p>가장 많이 쓴 달 <strong>8월 156만 원</strong> (131 → 135 → 148 → 156 → 150 → 142만 원) · 여름휴가 KTX·숙소, 에어컨 전기요금 때문</p></div>
    <span class="mlabel" style="margin-top:16px">더 물어보기</span>
    <div class="chips one"><button class="chip" type="button" data-copy="전기요금만 따로 꺾은선그래프로 그려줘.">전기요금만 따로 꺾은선그래프로 그려줘.<span class="tag">복사</span></button></div>
    <div class="note"><b>살펴보기</b><p>전기요금은 7·8월에 솟았다가 내려갑니다. 계절이 데이터에 보입니다.</p></div>
  </div>

  <h3 class="sub">질문 ④ 무엇과 다른가? — 막대그래프</h3>

  <div class="card">
    <h3>평일과 주말, 언제 더 많이 쓸까?</h3>
    <pre data-copy>평일과 주말의 하루 평균 지출을 비교해서 막대그래프로 그려줘. 평일과 주말이 각각 며칠인지도 알려줘.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="answer"><b>확인 포인트</b><p>주말이 <strong>약 2.4배</strong> · 주말 하루 약 7.9만 원, 평일 하루 약 3.4만 원 · 주말 53일, 평일 131일</p></div>
    <span class="mlabel" style="margin-top:16px">더 물어보기</span>
    <div class="chips one"><button class="chip" type="button" data-copy="주말에는 주로 무엇에 돈을 썼어?">주말에는 주로 무엇에 돈을 썼어?<span class="tag">복사</span></button></div>
    <div class="note"><b>살펴보기</b><p>외식·나들이·휴가가 많습니다. 결론 단계의 재료가 됩니다.</p></div>
  </div>

  <h3 class="sub">확인 — AI 계산, 그대로 믿어도 될까?</h3>
  <ul class="flow"><li>넣기</li><li>읽기</li><li>질문</li><li class="on">확인</li><li>결론</li></ul>

  <div class="card">
    <h3>방법 1 · 아는 숫자와 맞춰 보기</h3>
    <p>질문 ③의 월별 합계가 앞에서 본 그래프와 같은지 확인합니다. 예: 8월이 156만 원으로 최고</p>
    <h3>방법 2 · 근거 요청하기</h3>
    <pre data-copy>8월 교통비를 어떤 기록으로 더했는지 하나씩 보여줘.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="answer"><b>확인 포인트</b><p>KTX 96,000원 × 2 + 교통카드 20,000원 × 5 = <strong>292,000원</strong> · 7줄뿐이라 직접 더해 볼 수 있어요</p></div>
    <div class="note"><b>기억하기</b><p>계산은 AI가, 확인은 내가</p></div>
  </div>

  <h3 class="sub">결론 — 그래서 연말에는 어떻게 할까?</h3>
  <ul class="flow"><li>넣기</li><li>읽기</li><li>질문</li><li>확인</li><li class="on">결론</li></ul>

  <div class="card">
    <pre data-copy>지금까지 분석한 내용을 바탕으로, 11월과 12월에 돈을 아낄 수 있는 방법 3가지를 알려줘.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="note"><b>활동</b><p>AI가 제안한 3가지 중 <strong>"우리 집이라면 할 수 있는 것"</strong> 1가지를 고릅니다. 예: 주말 외식 횟수 정하기, 겨울 난방비 미리 대비하기</p></div>
    <div class="note"><b>기억하기</b><p>AI는 제안하고, 결론은 내가 내립니다.</p></div>
  </div>
</section>

<!-- ───────────── 2. AI 윤리 ───────────── -->
<section id="s2">
  <div class="sec-head"><span class="sec-num">2</span><h2>나를 위한 AI 윤리</h2></div>
  <p class="sec-note">의심하기, 확인하기, 지키기. AI를 쓸 때와 AI 광고를 볼 때 기억할 것입니다.</p>

  <div class="card">
    <h3>AI를 쓸 때 기억할 다섯 단어</h3>
    <div class="tbl-wrap">
      <table class="tbl">
        <tr><th>단어</th><th>뜻</th><th>이렇게 합니다</th></tr>
        <tr><td>환각</td><td>AI도 그럴듯하게 틀린다</td><td>건강·법률·돈에 관한 답은 원문이나 전문가에게 다시 확인</td></tr>
        <tr><td>아첨</td><td>AI는 내 말에 맞장구친다</td><td>장점과 단점, 반대 의견을 함께 묻기</td></tr>
        <tr><td>편향</td><td>AI도 한쪽으로 치우친다</td><td>결과가 나에게도 맞는지 한 번 더 따져보기</td></tr>
        <tr><td>개인정보</td><td>입력한 것은 남는다</td><td>주민번호·계좌·카드번호·비밀번호·진료 기록·남의 연락처는 넣지 않기</td></tr>
        <tr><td>딥페이크</td><td>내가 만든 것도 책임이 있다</td><td>허락받기 · AI로 만들었다고 밝히기 · 확인하고 나누기</td></tr>
      </table>
    </div>
  </div>

  <div class="card">
    <h3>아첨을 피하는 질문법</h3>
    <p>"이 건강식품 좋다던데, 맞지?"처럼 물으면 좋은 점 위주로 답할 수 있습니다. 이렇게 바꿔 물어보세요.</p>
    <div class="chips one">
      <button class="chip" type="button" data-copy="장점과 단점을 모두 알려줘">장점과 단점을 모두 알려줘<span class="tag">복사</span></button>
      <button class="chip" type="button" data-copy="반대 의견도 알려줘">반대 의견도 알려줘<span class="tag">복사</span></button>
      <button class="chip" type="button" data-copy="내 생각에 틀린 부분이 있으면 지적해줘">내 생각에 틀린 부분이 있으면 지적해줘<span class="tag">복사</span></button>
    </div>
    <div class="note"><b>핵심</b><p>AI가 칭찬하고 동의해도, 그게 사실이라는 뜻은 아닙니다.</p></div>
  </div>

  <div class="card">
    <h3>AI 광고 앞에서 물어볼 5가지</h3>
    <ol class="steps">
      <li><span>AI가 정확히 <b>무엇을</b> 해주나요?</span></li>
      <li><span><b>어떤 조건</b>에서 작동하나요? (앱 연결, 인터넷 등)</span></li>
      <li><span><b>성능 수치</b>는 어디서, 어떻게 시험한 건가요?</span></li>
      <li><span>상담원이 <b>AI인지 사람인지</b> 알려주나요?</span></li>
      <li><span>후기와 영상 속 <b>인물은 진짜</b>인가요?</span></li>
    </ol>
    <div class="note"><b>표시 찾기</b><p>AI 인물이 나오는 광고에는 [가상인물] 표시가 있어야 합니다. 표시 없이 전문가가 나오는 건강 광고는 일단 의심하세요. 2026년 11월 27일부터 식품·화장품·의약품 광고에서 AI 가상 전문가의 추천 자체가 금지됩니다.</p></div>
    <p style="margin:12px 0 0;font-size:.85em">출처: 공정거래위원회, 「AI 관련 표시·광고 가이드라인(안)」, 2026.10.22 (의견수렴용 초안)</p>
  </div>

  <details class="more">
    <summary>이렇게 해도 될까요? 상황 6가지</summary>
    <div class="more-body">
      <dl class="qa">
        <dt>1. 유명 의사가 영상에서 건강식품이 모든 병에 좋다고 말합니다.</dt>
        <dd>→ [가상인물] 표시, 실제 발언 여부, 효능의 근거를 확인합니다.</dd>
        <dt>2. 아는 사람 목소리로 급하게 돈을 보내 달라는 전화가 왔습니다.</dt>
        <dd>→ 끊고 원래 알던 번호로 다시 겁니다.</dd>
        <dt>3. "최첨단 AI 탑재, 정확도 100%"</dt>
        <dd>→ 어떤 기능에 AI를 썼는지, 어떤 조건에서 시험했는지가 없습니다.</dd>
        <dt>4. AI에게 "내 생각이 맞지?"라고 물었더니 "훌륭한 생각입니다!"라고 합니다.</dt>
        <dd>→ "틀린 부분이나 반대 의견도 알려줘"라고 다시 묻습니다.</dd>
        <dt>5. 건강검진 결과지를 사진 찍어 AI에게 해석해 달라고 하려 합니다.</dt>
        <dd>→ 이름·주민번호를 가리고, 해석은 의사에게 다시 확인합니다.</dd>
        <dt>6. 동호회 친구 사진으로 재미있는 AI 영상을 만들어 단톡방에 올리려 합니다.</dt>
        <dd>→ 친구에게 허락받고, AI로 만들었다고 밝힙니다.</dd>
      </dl>
    </div>
  </details>
</section>

<!-- ───────────── 3. 종합 실습: 주제 · 마스코트 ───────────── -->
<section id="s3">
  <div class="sec-head"><span class="sec-num">3</span><h2>종합 실습 · AI 안전 지킴이 캠페인</h2></div>
  <p class="sec-note">6주간 배운 기능으로, 우리 모임(동호회·동창 모임·가족 단톡방)에 알릴 AI 안전 캠페인을 만듭니다. 주제 고르기 → 마스코트 → 만들기 → 점검 → 공유 순서입니다.</p>

  <div class="note"><b>기억하기</b><p>이 중 하나만 골라도 충분합니다. 빨리 끝나면 다른 코스도 해보세요.</p></div>

  <h3 class="sub">① 캠페인 주제 고르기</h3>
  <ul class="flow"><li class="on">주제</li><li>마스코트</li><li>만들기</li><li>점검</li><li>공유</li></ul>

  <div class="card">
    <p>하나를 고르세요. 고른 슬로건 한 줄이 오늘 만드는 모든 결과물에 들어갑니다. 내 말로 바꿔도 좋습니다.</p>
    <div class="tbl-wrap">
      <table class="tbl">
        <tr><th>주제</th><th>슬로건 예시</th></tr>
        <tr><td>환각</td><td>"AI 답은 초안, 확인은 내가"</td></tr>
        <tr><td>아첨</td><td>"맞장구 말고 반대 의견도"</td></tr>
        <tr><td>편향</td><td>"나에게도 맞는지 한 번 더"</td></tr>
        <tr><td>개인정보</td><td>"AI 대화창은 일기장이 아닙니다"</td></tr>
        <tr><td>딥페이크</td><td>"끊고 다시 걸어 확인하기"</td></tr>
        <tr><td>AI 광고</td><td>"'최강'보다 조건과 한계"</td></tr>
      </table>
    </div>
  </div>

  <h3 class="sub">② 우리 캠페인 마스코트 그리기</h3>
  <ul class="flow"><li>주제</li><li class="on">마스코트</li><li>만들기</li><li>점검</li><li>공유</li></ul>

  <div class="card">
    <h3>마스코트 그리기 · 1주차 캐릭터 만들기</h3>
    <pre data-copy>[3D 피규어] 스타일로 'AI 안전 지킴이' 마스코트를 그려줘.
- [돋보기를 든 부엉이]
- [든든하고 친근한] 인상
- 가슴에 [방패 모양 배지]
- 배경은 [청록색] 계열 단색
- 정면, 전신, 정사각형
- 그림 안에 글자는 넣지 마</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="note"><b>바꿔도 좋아요</b><p>돋보기 든 부엉이 → 호루라기 든 강아지 · 우산 쓴 거북이 · 방패 든 고양이</p></div>
    <div class="note"><b>지키기</b><p>실제 사람 얼굴 · 유명 캐릭터는 넣지 않습니다. 글자는 그림에서 깨지니 빼고 그립니다.</p></div>
  </div>

  <details class="more">
    <summary>마스코트, 이렇게도 써보세요 (선택)</summary>
    <div class="more-body">
      <div class="card">
        <h3>이모티콘 만들기</h3>
        <pre data-copy>방금 이 마스코트로 이모티콘 4개를 만들어줘.
표정은 [의심하는 눈빛], [돋보기로 살펴보기], [엄지 척], [손바닥 펴고 잠깐!]
글자는 넣지 말고, 네 개를 한 장에 배치해줘.</pre>
        <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
      </div>
      <div class="card">
        <h3>캠페인 부스 미니어처</h3>
        <pre data-copy>'AI 안전 지킴이' 캠페인 부스의 미니어처 입체 모형.
지붕은 거대한 [돋보기]로 만들어지고, 방금 만든 마스코트가 손님에게 [안내 전단]을 건네고 있다.
핸드메이드 소프트 클레이 조형, 부드러운 조명, 세로 3:4 비율.</pre>
        <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
      </div>
      <div class="note"><b>기억하기</b><p>같은 채팅창에서 이어서 말해야 캐릭터 모습이 유지됩니다.</p></div>
    </div>
  </details>
</section>

<!-- ───────────── 4. 만들기 코스 ───────────── -->
<section id="s4">
  <div class="sec-head"><span class="sec-num">4</span><h2>③ 만들기 코스 고르기</h2></div>
  <p class="sec-note">A~D 중 하나를 고르세요. 타이핑이 어렵다면 복사·붙여넣기 위주인 A(노래)나 D(Gem)를 추천합니다.</p>
  <ul class="flow"><li>주제</li><li>마스코트</li><li class="on">만들기</li><li>점검</li><li>공유</li></ul>

  <div class="tbl-wrap" style="margin-bottom:18px">
    <table class="tbl">
      <tr><th>코스</th><th>만드는 것</th><th>쓰는 도구</th></tr>
      <tr><td>A 캠페인송</td><td>슬로건으로 따라 부르는 노래</td><td>Gemini 가사 → 수노</td></tr>
      <tr><td>B 안내 글 + 카드</td><td>단톡방에 올릴 안내 글과 그림</td><td>AI 인터뷰 → 초안 → 점검</td></tr>
      <tr><td>C 체크 앱</td><td>광고를 믿어도 될지 눌러 보는 앱</td><td>Canvas 바이브코딩</td></tr>
      <tr><td>D 지킴이 Gem</td><td>의심스러운 광고를 함께 따져 주는 비서</td><td>Gem 요청사항</td></tr>
    </table>
  </div>

  <!-- 코스 A -->
  <h3 class="sub">코스 A · 캠페인송</h3>

  <div class="card">
    <h3>1단계 · Gemini에서 가사 받기</h3>
    <pre data-copy>너는 따라 부르기 쉬운 노래를 만드는 작사가야.
[개인정보 지키기]를 알리는 캠페인송 가사를 써줘.
- 듣는 사람: [우리 동호회 회원들]
- 꼭 넣을 말: [AI 대화창은 일기장이 아닙니다]
- 1절과 후렴만, 한 줄은 짧게
- 후렴은 같은 말을 세 번 반복
- 분위기: [밝고 신나게]</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <span class="mlabel" style="margin-top:16px">2단계 · 말로 고치기</span>
    <div class="chips">
      <button class="chip" type="button" data-copy="후렴을 더 짧게 해줘">후렴을 더 짧게 해줘<span class="tag">복사</span></button>
      <button class="chip" type="button" data-copy="두 번째 줄은 그대로 둬">두 번째 줄은 그대로 둬<span class="tag">복사</span></button>
    </div>
    <div class="note"><b>기억하기</b><p>고칠 곳을 콕 집어 말하면 마음에 드는 부분은 그대로 남습니다.</p></div>
  </div>

  <div class="card">
    <h3>3단계 · 수노 '고급'에서 노래 완성하기</h3>
    <p><strong>가사 칸</strong>에는 Gemini에서 받은 가사를, <strong>음악 스타일 칸</strong>에는 아래 문장을 붙여넣습니다.</p>
    <pre data-copy>[밝은 트로트], [박수 소리], 따라 부르기 쉬운 후렴, 경쾌하게</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="note"><b>다른 스타일</b><p>신나는 동요 · 경쾌한 포크 · 행진곡 · 잔잔한 발라드</p></div>
    <div class="note"><b>지키기</b><p>유명 가수 이름이나 목소리를 흉내 내 달라고 하지 않기 · 남의 노래 가사를 그대로 넣지 않기 · 공유할 때 "AI로 만든 노래예요" 함께 적기</p></div>
  </div>

  <!-- 코스 B -->
  <h3 class="sub">코스 B · 단톡방 안내 글 + 카드</h3>

  <div class="card">
    <h3>1단계 · AI가 먼저 묻게 하기</h3>
    <pre data-copy>우리 [산악 동호회] 단톡방에 [AI 목소리 전화 사기 조심] 안내 글을 올리려고 해.
글을 쓰기 전에 나한테 질문을 3개 해줘.
한 번에 하나씩 물어봐줘.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
  </div>

  <div class="card">
    <h3>2단계 · 초안 받기</h3>
    <pre data-copy>좋아, 내 답을 바탕으로 안내 글을 써줘.
- 분량: [다섯 줄] 정도
- 말투: [따뜻하고 정중하게]
- 꼭 넣을 말: [끊고 다시 걸어 확인하기]
- 내가 말하지 않은 숫자나 사례는 지어내지 마.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="note"><b>기억하기</b><p>재료는 내가 줍니다. AI는 내가 말하지 않은 것을 지어낼 수 있습니다.</p></div>
  </div>

  <div class="card">
    <h3>3단계 · 글 점검하기</h3>
    <pre data-copy>이 글에서 사실 확인이 필요한 부분과, 내가 말하지 않았는데 들어간 내용을 목록으로 알려줘.
글은 고치지 말고 목록으로만 보여줘.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
  </div>

  <div class="card">
    <h3>4단계 · 카드 그림 만들기</h3>
    <pre data-copy>이 안내 글과 어울리는 카드 그림을 만들어줘.
방금 만든 마스코트가 [휴대폰을 들고 손바닥을 펴서 '잠깐!' 하는] 장면으로.
글자는 넣지 말고, 밝고 따뜻한 색으로, 정사각형.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="note"><b>기억하기</b><p>카드 그림과 안내 글을 함께 보내면 글자가 깨질 걱정이 없습니다.</p></div>
  </div>

  <!-- 코스 C -->
  <h3 class="sub">코스 C · '잠깐! AI 광고 체크' 앱</h3>

  <div class="card">
    <h3>새 채팅 → 도구 → Canvas 켜고 붙여넣기</h3>
    <p>3주차 '오늘 뭐 먹지' 앱과 같은 틀입니다. ① 무엇을 ② 누르면 어떻게 ③ 내용 ④ 어떤 모양으로</p>
    <pre data-copy>① 무엇을: AI 광고를 믿어도 될지 점검하는 '잠깐! AI 광고 체크' 앱을 만들어줘.
② 누르면: 질문을 하나씩 보여주고 '예 / 아니오' 단추로 답하게 해줘. 다 답하면 '아니오' 개수에 따라 '믿을 만해요 / 한 번 더 확인 / 일단 의심!'을 크게 보여줘. '처음부터' 단추도.
③ 질문: [AI가 무엇을 해 주는지 적혀 있나요? / 어떤 조건에서 작동하는지 적혀 있나요? / 성능 수치를 어디서 시험했는지 나와 있나요? / 상담원이 AI인지 사람인지 알려 주나요? / 광고 속 인물이 AI 가상인물이면 표시가 있나요?]
④ 모양: 글씨와 단추는 크게, 결과는 [신호등] 색으로, 한 화면에</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="note"><b>기억하기</b><p>말하지 않으면 AI 마음대로, 말하면 내 마음대로</p></div>
  </div>

  <div class="card">
    <h3>눌러 보고 고치기</h3>
    <ol class="steps">
      <li><span>모두 <b>'예'</b>를 누르면 → '믿을 만해요'가 나오나요?</span></li>
      <li><span>모두 <b>'아니오'</b>를 누르면 → '일단 의심!'이 나오나요?</span></li>
    </ol>
    <span class="mlabel" style="margin-top:12px">이상하면 그대로 말하기</span>
    <div class="chips one"><button class="chip" type="button" data-copy="아니오를 다 눌렀는데 믿을 만하다고 나와. 고쳐줘">아니오를 다 눌렀는데 믿을 만하다고 나와. 고쳐줘<span class="tag">복사</span></button></div>
    <span class="mlabel" style="margin-top:16px">한 번에 하나씩 더하기</span>
    <div class="chips one">
      <button class="chip" type="button" data-copy="결과 화면에 [끊고 다시 걸어 확인하기] 한 줄을 크게 넣어줘.">결과 화면에 [끊고 다시 걸어 확인하기] 한 줄을 크게 넣어줘.<span class="tag">복사</span></button>
      <button class="chip" type="button" data-copy="'일단 의심!'이 나오면 [빨간 방패] 그림이 통통 튀며 나타나게 해줘.">'일단 의심!'이 나오면 [빨간 방패] 그림이 통통 튀며 나타나게 해줘.<span class="tag">복사</span></button>
      <button class="chip" type="button" data-copy="맨 위에 내가 만든 [마스코트 그림]을 넣어줘.">맨 위에 내가 만든 [마스코트 그림]을 넣어줘.<span class="tag">복사</span></button>
    </div>
    <div class="note"><b>기억하기</b><p>앱이 그럴듯해 보여도 눌러 보고 확인하는 것은 내 몫입니다.</p></div>
  </div>

  <!-- 코스 D -->
  <h3 class="sub">코스 D · 지킴이 Gem</h3>

  <div class="card">
    <h3>Gem 만들기</h3>
    <ol class="steps">
      <li><span>Gemini 왼쪽 메뉴에서 <b>Gem 새로 만들기</b>를 누릅니다.</span></li>
      <li><span>이름: <b>AI 안전 지킴이</b> / 설명: <b>의심스러운 광고·문자 점검 도우미</b></span></li>
      <li><span><b>요청사항</b> 칸에 아래 내용을 붙여넣고 저장합니다.</span></li>
    </ol>
  </div>

  <div class="card">
    <h3>요청사항 칸</h3>
    <pre data-copy>너는 내가 받은 광고·문자·영상을 함께 점검해 주는 'AI 안전 지킴이'야.

[반드시 지킬 것]
- 아래 5가지로 하나씩 점검한다: AI가 무엇을 해 주는지 / 작동 조건 / 성능 수치의 근거 / 상담원이 AI인지 사람인지 / 인물이 가상인물인지 표시가 있는지
- 내 말에 무조건 맞장구치지 말고, 의심스러운 점과 반대 의견도 알려준다.
- 송금이나 개인정보를 요구하는 내용이면 '멈추고, 원래 알던 번호로 확인하기'를 가장 먼저 알려준다.
- 내가 주민번호 · 계좌번호를 적으면 지우라고 알려준다.

[출력 형식]
표로 만든다. 점검 질문 | 확인 결과 | 내가 할 일. 마지막에 한 줄 결론.

[중요]
모르는 정보는 지어내지 말고 "확인 필요"라고 표시한다. 정보가 부족하면 먼저 세 가지만 물어본다.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="note"><b>기억하기</b><p>[중요] 한 줄이 그럴듯한 거짓 답을 막아줍니다.</p></div>
  </div>

  <div class="card">
    <h3>시험 1 · 가상 광고 붙여넣기</h3>
    <pre data-copy>이 광고 점검해줘.
"최첨단 AI 탑재! 정확도 100%! 'AI 척척 밥솥'은 타사 대비 3배 맛있는 밥을 지어 드립니다. 오늘만 반값!"</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <p style="margin:12px 0 0;font-size:.85em">※ 설명을 위한 가상의 광고</p>
  </div>

  <div class="card">
    <h3>시험 2 · 맞장구 유도해 보기</h3>
    <pre data-copy>이 밥솥 정말 좋은 거 맞지? 오늘 바로 살 거야.</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <span class="mlabel" style="margin-top:16px">Gem이 맞장구만 친다면? 요청사항에 한 줄 더</span>
    <div class="chips one"><button class="chip" type="button" data-copy="내가 사려고 해도 단점부터 먼저 말해줘.">내가 사려고 해도 단점부터 먼저 말해줘.<span class="tag">복사</span></button></div>
    <div class="note"><b>핵심</b><p>AI가 칭찬하고 동의해도, 그게 사실이라는 뜻은 아닙니다.</p></div>
  </div>

  <!-- 더 해보기 -->
  <details class="more">
    <summary>더 해보기 · Notebook 퀴즈 (선택)</summary>
    <div class="more-body">
      <p style="margin:0 0 14px;color:var(--ink-soft)"><strong style="color:var(--ink)">넣을 자료</strong> 오늘 6주차 윤리 자료, 공정위 AI 광고 가이드라인(안) 소비자 유의사항 (강사가 만든 노트북 사본을 써도 됩니다)</p>
      <div class="card">
        <h3>오디오 개요 · 맞춤설정</h3>
        <pre data-copy>딥페이크 전화와 AI 광고를 생활 속 예를 들어 쉽게 설명해줘. 두 사람이 대화하듯.</pre>
        <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
      </div>
      <div class="card">
        <h3>퀴즈 · 맞춤설정</h3>
        <pre data-copy>'이렇게 해도 될까요?'처럼 상황을 주고 고르는 객관식 5문제를 만들어줘. 정답과 근거도.</pre>
        <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
      </div>
      <div class="note"><b>기억하기</b><p>답 옆의 출처 번호를 눌러 자료에 정말 있는지 확인하세요.</p></div>
    </div>
  </details>
</section>

<!-- ───────────── 5. 점검 · 공유 ───────────── -->
<section id="s5">
  <div class="sec-head"><span class="sec-num">5</span><h2>④ 점검하고 ⑤ 공유하기</h2></div>
  <p class="sec-note">속지 않는 것만큼, 속이지 않는 것도 중요합니다. 내가 만든 것도 다섯 단어로 점검합니다.</p>
  <ul class="flow"><li>주제</li><li>마스코트</li><li>만들기</li><li class="on">점검</li><li class="on">공유</li></ul>

  <div class="card">
    <h3>AI에게 점검 부탁하기</h3>
    <pre data-copy>내가 만든 이 [안내 글]을 꼼꼼한 검토자처럼 읽고, 아래 세 가지를 목록으로만 알려줘. 고치지는 마.
1) 사실 확인이 필요한 곳
2) 오해할 수 있는 표현
3) 개인정보가 들어간 곳</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
  </div>

  <div class="card">
    <h3>다섯 단어 점검표</h3>
    <ul class="check">
      <li><input type="checkbox" id="k1"><label for="k1"><b>환각</b> 틀린 사실 · 지어낸 숫자는 없나요?</label></li>
      <li><input type="checkbox" id="k2"><label for="k2"><b>아첨</b> 칭찬만 들었다면, 약점도 물어봤나요?</label></li>
      <li><input type="checkbox" id="k3"><label for="k3"><b>편향</b> 한쪽 나이 · 성별로만 그리진 않았나요?</label></li>
      <li><input type="checkbox" id="k4"><label for="k4"><b>개인정보</b> 이름 · 번호 · 친구 사진이 들어가지 않았나요?</label></li>
      <li><input type="checkbox" id="k5"><label for="k5"><b>딥페이크</b> 남의 얼굴 · 목소리를 허락 없이 쓰지 않았나요?</label></li>
    </ul>
  </div>

  <div class="card">
    <h3>패들렛 게시물 쓰기</h3>
    <pre data-copy>[개인정보] 캠페인 · [홍길동]
슬로건: "[AI 대화창은 일기장이 아닙니다]"
만든 것: [마스코트 + 캠페인송 QR]
점검: [개인정보 ☑ 딥페이크 ☑]
AI로 만들었어요 ([Gemini · 수노])</pre>
    <button class="copy" type="button"><span class="ico">⧉</span>복사하기</button>
    <div class="note"><b>함께 나눠요</b><p>어떤 프롬프트로 만들었나요? · AI가 틀리거나 지어낸 곳이 있었나요? · 점검하면서 고친 부분은요?</p></div>
    <div class="note"><b>기억하기</b><p>AI로 만든 것을 나눌 때는 AI로 만들었다고 함께 적습니다. 광고의 [가상인물] 표시와 같은 원리입니다.</p></div>
  </div>
</section>

<!-- ───────────── 체크리스트 ───────────── -->
<section id="check">
  <div class="sec-head"><span class="sec-num">✓</span><h2>꼭 지킬 것</h2></div>
  <p class="sec-note">AI는 똑똑하게 쓰고, 최종 판단은 내가 합니다.</p>
  <div class="card">
    <ul class="check">
      <li><input type="checkbox" id="c1"><label for="c1">AI가 계산한 숫자 한두 개를 원래 표와 직접 맞춰 봤다.</label></li>
      <li><input type="checkbox" id="c2"><label for="c2">건강·법률·돈에 관한 AI의 답은 원문이나 전문가에게 다시 확인했다.</label></li>
      <li><input type="checkbox" id="c3"><label for="c3">AI가 맞장구만 칠 때는 단점과 반대 의견도 물어봤다.</label></li>
      <li><input type="checkbox" id="c4"><label for="c4">주민등록번호, 계좌·카드번호, 비밀번호, 진료 기록, 남의 연락처는 넣지 않았다.</label></li>
      <li><input type="checkbox" id="c5"><label for="c5">남의 얼굴·목소리는 허락받고 쓰고, 공유할 때 "AI로 만들었어요"라고 적었다.</label></li>
      <li><input type="checkbox" id="c6"><label for="c6">수업이 끝난 뒤 오른쪽 위 내 사진 → '로그아웃'을 눌렀다. (수노도 로그아웃)</label></li>
    </ul>
  </div>
</section>

<div class="banner">
  <span class="label">결과물 올리는 곳</span>
  <span class="addr">bit.ly/업스킬링</span>
</div>

<div class="card" style="margin-top:24px">
  <h3>QR코드 만들기</h3>
  <p>수노 노래 링크나 Gem·앱 공유 주소를 넣으면 QR코드가 만들어집니다.</p>
  <div class="qr-row">
    <input type="text" id="qr-link" placeholder="https://example.com" aria-label="QR코드로 만들 주소">
    <button type="button" id="qr-make">QR코드 만들기</button>
  </div>
  <div id="qrcode"></div>
</div>

<footer>
  <p><b>마치기 전에 꼭</b> — 공용 컴퓨터는 로그아웃, 꼭 잊지 말아주세요!</p>
  <p>6주 동안 함께해 주셔서 감사합니다. 문의: cwh525@uos.ac.kr</p>
</footer>

</div>

<script src="https://cdn.jsdelivr.net/npm/qrcodejs@1.0.0/qrcode.min.js"></script>
<script>
(function(){
  /* [대괄호] 부분 노란색 표시 (복사되는 문장은 그대로) */
  var KEEP=['[반드시 지킬 것]','[출력 형식]','[중요]'];
  document.querySelectorAll('pre[data-copy]').forEach(function(pre){
    var raw = pre.textContent;
    pre.setAttribute('data-copy', raw);
    var html = raw
      .replace(/&/g,'&amp;')
      .replace(/</g,'&lt;')
      .replace(/>/g,'&gt;')
      .replace(/\[[^\]]*\]/g,function(m){
        /* Gem 요청사항의 제목 칸은 바꾸는 칸이 아니므로 노란색 표시 안 함 */
        if(KEEP.indexOf(m)>-1) return m;
        return '<span class="ph">' + m + '</span>';
      });
    pre.innerHTML = html;
  });

  /* 복사 기능 */
  function legacy(text){
    var ta = document.createElement('textarea');
    ta.value = text;
    ta.setAttribute('readonly','');
    ta.style.position = 'fixed';
    ta.style.top = '0';
    ta.style.opacity = '0';
    document.body.appendChild(ta);
    ta.select();
    var ok = false;
    try{ok=document.execCommand('copy')}catch(e){ok=false}
    document.body.removeChild(ta);
    return ok;
  }
  function copyText(text){
    if(navigator.clipboard && window.isSecureContext){
      return navigator.clipboard.writeText(text).then(
        function(){return true},
        function(){return legacy(text)}
      );
    }
    return Promise.resolve(legacy(text));
  }
  function flash(btn,label){
    var original=btn.dataset.label||btn.innerHTML;
    btn.dataset.label=original;
    btn.classList.add('done');
    btn.innerHTML=label;
    clearTimeout(btn._t);
    btn._t=setTimeout(function(){
      btn.classList.remove('done');
      btn.innerHTML=btn.dataset.label;
    },1800);
  }
  document.querySelectorAll('button.copy').forEach(function(btn){
    btn.addEventListener('click',function(){
      var pre=btn.parentElement.querySelector('pre[data-copy]');
      if(!pre) return;
      copyText(pre.getAttribute('data-copy')).then(function(ok){
        flash(btn,ok?'복사됐습니다':'복사가 안 됩니다');
      });
    });
  });
  document.querySelectorAll('button.chip').forEach(function(btn){
    btn.addEventListener('click',function(){
      copyText(btn.getAttribute('data-copy')).then(function(ok){
        flash(btn,ok?'복사됐습니다':'복사가 안 됩니다');
      });
    });
  });

  /* 글자 크기 */
  var STEPS=[1,1.15,1.32,1.5];
  var idx=0;
  try{
    var saved=localStorage.getItem('uskill-size');
    if(saved!==null) idx=Math.min(STEPS.length-1,Math.max(0,parseInt(saved,10)||0));
  }catch(e){}
  function apply(){
    document.documentElement.style.setProperty('--step',STEPS[idx]);
    try{localStorage.setItem('uskill-size',String(idx))}catch(e){}
  }
  apply();
  document.getElementById('bigger').addEventListener('click',function(){
    if(idx<STEPS.length-1){idx++;apply()}
  });
  document.getElementById('smaller').addEventListener('click',function(){
    if(idx>0){idx--;apply()}
  });

  /* QR코드 */
  document.getElementById('qr-make').addEventListener('click',function(){
    var link=document.getElementById('qr-link').value.trim();
    var box=document.getElementById('qrcode');
    if(!link){alert('링크를 입력해주세요.');return;}
    box.innerHTML='';
    if(typeof QRCode==='undefined'){box.textContent='QR코드 도구를 불러오지 못했습니다.';return;}
    new QRCode(box,{text:link,width:200,height:200});
  });
})();
</script>

</body>
</html>
