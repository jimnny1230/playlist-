<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>skoshism · 나만의 유튜브 플레이리스트</title>

<style>
:root{
  --pink-000:#FFF6FA;
  --pink-050:#FFE9F3;
  --pink-100:#FFD3E7;
  --pink-200:#FFC3DE;
  --pink-300:#FF9EC4;
  --pink-500:#FF6FA0;
  --pink-700:#E24E82;
  --pink-icon:#B9637F;

  --pearl-100:#FFFFFF;
  --pearl-200:#F7F5F4;
  --ink-900:#2B2730;
  --ink-500:#8A8390;
  --bezel:#181418;

  --screen-idle-a:#FFF1F6;
  --screen-idle-b:#FBDCEA;

  --theme-bg:linear-gradient(
    180deg,
    var(--pink-050) 0%,
    var(--pink-100) 40%,
    var(--pink-200) 100%
  );

  --theme-device:linear-gradient(
    155deg,
    var(--pearl-100) 0%,
    var(--pink-050) 38%,
    var(--pink-100) 78%,
    var(--pink-200) 100%
  );

  --theme-wheel:radial-gradient(
    circle at 32% 28%,
    var(--pearl-100),
    var(--pink-100) 55%,
    var(--pink-200) 100%
  );

  --theme-idle:linear-gradient(
    165deg,
    var(--screen-idle-a),
    var(--screen-idle-b)
  );

  --theme-transition:
    background-color .45s ease,
    border-color .45s ease,
    color .45s ease;
}

*{
  box-sizing:border-box;
}

html,
body{
  margin:0;
  padding:0;
  min-height:100%;
  font-family:
    'Apple SD Gothic Neo',
    'Pretendard',
    'Noto Sans KR',
    -apple-system,
    BlinkMacSystemFont,
    'Malgun Gothic',
    sans-serif;
  color:var(--ink-900);
  background:var(--theme-bg);
  -webkit-tap-highlight-color:transparent;
  transition:var(--theme-transition);
}

body{
  display:flex;
  justify-content:center;
  padding:14px 12px 40px;
}

.app{
  width:100%;
  max-width:440px;
  display:flex;
  flex-direction:column;
  align-items:center;
  gap:18px;
}

.device{
  position:relative;
  width:100%;
  background:var(--theme-device);
  border-radius:34px;
  padding:16px 16px 22px;
  box-shadow:
    0 30px 60px -18px rgba(226,78,130,.35),
    0 2px 0 rgba(255,255,255,.9) inset,
    0 -6px 18px rgba(255,150,190,.25) inset;
  border:1px solid var(--pink-100);
  transition:var(--theme-transition);
}

.device-brand{
  text-align:center;
  padding:2px 4px 10px;
}

.device-brand-word{
  font-size:15px;
  font-weight:800;
  letter-spacing:.02em;
  color:var(--pink-700);
  transition:var(--theme-transition);
}

.device-brand-sub{
  font-size:10.5px;
  font-weight:600;
  letter-spacing:.06em;
  text-transform:lowercase;
  color:var(--ink-500);
  margin-left:6px;
}

.device-footnote{
  margin:12px 6px 0;
  text-align:center;
  font-size:10.5px;
  line-height:1.5;
  color:var(--ink-500);
}

.screen-bezel{
  background:linear-gradient(160deg,#232025,var(--bezel) 60%);
  border-radius:20px;
  padding:10px;
  box-shadow:
    0 1px 0 rgba(255,255,255,.06) inset,
    0 10px 20px -12px rgba(0,0,0,.5);
}

.screen{
  position:relative;
  width:100%;
  height:clamp(430px,118vw,490px);
  border-radius:12px;
  overflow:hidden;
  background:var(--theme-idle);
  display:flex;
  flex-direction:column;
  transition:var(--theme-transition);
}

.screen-topbar{
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding:9px 10px 6px;
  flex-shrink:0;
}

.screen-tabs{
  display:flex;
  gap:6px;
}

.tab-btn{
  border:1px solid transparent;
  background:transparent;
  color:var(--ink-500);
  font-family:inherit;
  font-size:11px;
  font-weight:700;
  padding:4px 10px;
  border-radius:99px;
  cursor:pointer;
}

.tab-btn.active{
  background:#fff;
  color:var(--pink-700);
  border-color:var(--pink-100);
  box-shadow:0 2px 5px rgba(226,78,130,.15);
}

.topbar-count{
  font-size:10.5px;
  font-weight:700;
  color:var(--ink-500);
}

.screen-input{
  flex-shrink:0;
  padding:0 10px 7px;
}

.screen-input-form{
  display:flex;
  gap:6px;
}

.screen-input-form input{
  flex:1;
  min-width:0;
  padding:8px 10px;
  border-radius:9px;
  border:1.5px solid rgba(226,78,130,.22);
  background:#fff;
  font-size:12.5px;
  color:var(--ink-900);
  outline:none;
  font-family:inherit;
}

.screen-input-form input:focus{
  border-color:var(--pink-500);
}

.screen-input-form button{
  flex-shrink:0;
  padding:0 13px;
  border:0;
  border-radius:9px;
  background:linear-gradient(160deg,var(--pink-500),var(--pink-700));
  color:#fff;
  font-weight:800;
  font-size:12px;
  font-family:inherit;
  cursor:pointer;
}

.screen-input-form button:disabled{
  opacity:.55;
  cursor:default;
}

.screen-form-msg{
  min-height:14px;
  font-size:10.5px;
  color:var(--pink-700);
  margin-top:5px;
}

.screen-manual{
  margin-top:6px;
  display:flex;
  flex-direction:column;
  gap:6px;
}

.screen-manual.hidden{
  display:none;
}

.screen-manual input{
  padding:8px 10px;
  border-radius:8px;
  border:1.5px solid rgba(226,78,130,.22);
  font-size:12px;
  outline:none;
  font-family:inherit;
}

.screen-manual input:focus{
  border-color:var(--pink-500);
}

.screen-manual button{
  align-self:flex-end;
  padding:6px 13px;
  border:0;
  border-radius:8px;
  background:var(--pink-500);
  color:#fff;
  font-weight:700;
  font-size:11px;
  font-family:inherit;
  cursor:pointer;
}

.screen-body{
  position:relative;
  flex:1 1 auto;
  min-height:0;
}

.screen-panel{
  position:absolute;
  inset:0;
  display:flex;
  flex-direction:column;
  opacity:0;
  pointer-events:none;
  transition:opacity .18s ease;
}

.screen-panel.active{
  opacity:1;
  pointer-events:auto;
}

.video-wrap{
  position:relative;
  width:100%;
  flex:1 1 auto;
  min-height:0;
  background:#000;
  overflow:hidden;
}

.video-wrap #player,
.video-wrap iframe{
  position:absolute;
  inset:0;
  width:100%;
  height:100%;
  border:0;
}

.idle-screen{
  position:absolute;
  inset:0;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  gap:8px;
  background:var(--theme-idle);
  transition:opacity .25s ease;
}

.idle-screen.hidden{
  opacity:0;
  pointer-events:none;
}

.idle-cat{
  width:58px;
  height:50px;
  position:relative;
}

.idle-cat::before,
.idle-cat::after{
  content:"";
  position:absolute;
  top:0;
  width:0;
  height:0;
  border-left:10px solid transparent;
  border-right:10px solid transparent;
  border-bottom:16px solid var(--pink-300);
}

.idle-cat::before{
  left:2px;
  transform:rotate(-8deg);
}

.idle-cat::after{
  right:2px;
  transform:rotate(8deg);
}

.idle-cat .face{
  position:absolute;
  left:7px;
  right:7px;
  bottom:0;
  height:40px;
  background:#fff;
  border-radius:50% 50% 46% 46%;
  box-shadow:0 2px 6px rgba(226,78,130,.18);
}

.idle-cat .face::before,
.idle-cat .face::after{
  content:"";
  position:absolute;
  top:17px;
  width:5px;
  height:5px;
  border-radius:50%;
  background:var(--ink-900);
}

.idle-cat .face::before{
  left:13px;
}

.idle-cat .face::after{
  right:13px;
}

.idle-text{
  font-size:12.5px;
  font-weight:700;
  color:var(--pink-700);
}

.idle-sub{
  font-size:11px;
  color:var(--ink-500);
}

.now-playing-info{
  flex-shrink:0;
  padding:9px 12px 11px;
}

.track-title{
  font-size:13.5px;
  font-weight:800;
  line-height:1.3;
  white-space:nowrap;
  overflow:hidden;
  text-overflow:ellipsis;
}

.track-artist{
  font-size:11.5px;
  color:var(--ink-500);
  margin-top:1px;
  white-space:nowrap;
  overflow:hidden;
  text-overflow:ellipsis;
}

.progress-track{
  margin-top:8px;
  height:5px;
  border-radius:99px;
  background:#E7E2E6;
  overflow:hidden;
}

.progress-fill{
  height:100%;
  width:0%;
  background:linear-gradient(90deg,var(--pink-300),var(--pink-500));
  border-radius:99px;
  transition:width .3s linear;
}

.time-row{
  display:flex;
  justify-content:space-between;
  font-size:10px;
  color:var(--ink-500);
  margin-top:5px;
  font-variant-numeric:tabular-nums;
}

.screen-panel-list{
  background:var(--pink-000);
  transition:var(--theme-transition);
}

.history-list{
  list-style:none;
  margin:0;
  padding:6px 8px 4px;
  overflow-y:auto;
  flex:1 1 auto;
  min-height:0;
}

.history-item{
  display:flex;
  gap:9px;
  align-items:center;
  padding:6px 6px;
  border-radius:10px;
  cursor:pointer;
  border-bottom:1px solid var(--pink-050);
}

.history-item:last-child{
  border-bottom:0;
}

.history-item:hover{
  background:rgba(255,159,196,.12);
}

.history-item.active{
  background:rgba(255,111,160,.16);
}

.history-item img{
  width:34px;
  height:34px;
  border-radius:7px;
  object-fit:cover;
  flex-shrink:0;
  box-shadow:0 2px 5px rgba(0,0,0,.12);
}

.history-text{
  min-width:0;
  flex:1;
}

.history-title{
  font-size:12px;
  font-weight:700;
  white-space:nowrap;
  overflow:hidden;
  text-overflow:ellipsis;
}

.history-sub{
  font-size:10.5px;
  color:var(--ink-500);
  white-space:nowrap;
  overflow:hidden;
  text-overflow:ellipsis;
}

.history-actions{
  display:flex;
  align-items:center;
  gap:4px;
  flex-shrink:0;
}

.history-move{
  display:flex;
  flex-direction:column;
  gap:1px;
}

.history-move button{
  width:18px;
  height:13px;
  padding:0;
  border:0;
  background:rgba(226,78,130,.07);
  color:var(--pink-icon);
  font-size:8px;
  line-height:1;
  border-radius:3px;
  cursor:pointer;
  display:flex;
  align-items:center;
  justify-content:center;
  font-family:inherit;
}

.history-move button:hover{
  background:rgba(226,78,130,.16);
}

.history-move button:disabled{
  opacity:.25;
  cursor:default;
  background:transparent;
}

.history-delete{
  width:22px;
  height:22px;
  flex-shrink:0;
  border:0;
  border-radius:50%;
  background:rgba(226,78,130,.08);
  color:var(--pink-700);
  font-size:11px;
  cursor:pointer;
  display:flex;
  align-items:center;
  justify-content:center;
  font-family:inherit;
}

.history-delete:hover{
  background:rgba(226,78,130,.2);
}

.empty-state{
  padding:14px 14px 10px;
  font-size:11.5px;
  color:var(--ink-500);
  line-height:1.6;
  text-align:center;
}

.empty-state.hidden{
  display:none;
}

.wheel-area{
  display:flex;
  justify-content:center;
  padding-top:22px;
}

.click-wheel{
  position:relative;
  width:clamp(180px,52vw,220px);
  aspect-ratio:1/1;
  border-radius:50%;
  background:var(--theme-wheel);
  box-shadow:
    0 10px 22px -10px rgba(226,78,130,.4),
    0 1px 0 rgba(255,255,255,.8) inset;
  transition:var(--theme-transition);
}

.wheel-btn{
  position:absolute;
  border:0;
  background:none;
  color:var(--pink-icon);
  font-weight:800;
  cursor:pointer;
  font-family:inherit;
  transition:var(--theme-transition);
}

.wheel-btn:active{
  color:var(--pink-700);
}

.wheel-btn:disabled{
  opacity:.3;
  cursor:default;
}

.plus-btn{
  top:8%;
  left:50%;
  transform:translateX(-50%);
  font-size:19px;
}

.minus-btn{
  bottom:9%;
  left:50%;
  transform:translateX(-50%);
  font-size:19px;
  line-height:1;
}

.prev-btn{
  left:9%;
  top:50%;
  transform:translateY(-50%);
  font-size:16px;
}

.next-btn{
  right:9%;
  top:50%;
  transform:translateY(-50%);
  font-size:16px;
}

.wheel-hole{
  position:absolute;
  top:50%;
  left:50%;
  transform:translate(-50%,-50%);
  width:45%;
  aspect-ratio:1/1;
  border-radius:50%;
  border:0;
  cursor:pointer;
  background:
    radial-gradient(
      circle at 38% 32%,
      var(--pink-300),
      var(--pink-500) 55%,
      var(--pink-700) 100%
    );
  box-shadow:
    0 2px 6px rgba(0,0,0,.18) inset,
    0 1px 0 rgba(255,255,255,.25) inset;
  transition:var(--theme-transition);
  display:flex;
  align-items:center;
  justify-content:center;
  gap:3px;
}

.wheel-hole:disabled{
  opacity:.55;
  cursor:default;
}

.wheel-hole .play-icon{
  width:0;
  height:0;
  border-top:7px solid transparent;
  border-bottom:7px solid transparent;
  border-left:11px solid rgba(255,255,255,.92);
}

.wheel-hole .pause-icon{
  display:flex;
  gap:3px;
}

.wheel-hole .pause-icon span{
  width:3px;
  height:14px;
  background:rgba(255,255,255,.92);
  border-radius:1px;
}
</style>
</head>

<body>
<div class="app">

  <div class="device" id="device">

    <div class="device-brand">
      <span class="device-brand-word">skoshism</span>
      <span class="device-brand-sub">playlist</span>
    </div>

    <div class="screen-bezel">

      <div class="screen" id="screen">

        <div class="screen-topbar">

          <div class="screen-tabs">
            <button
              type="button"
              class="tab-btn active"
              id="tabPlayerBtn"
            >
              재생
            </button>

            <button
              type="button"
              class="tab-btn"
              id="tabListBtn"
            >
              목록
            </button>
          </div>

          <span
            class="topbar-count"
            id="topbarCount"
          >
            0 / 0
          </span>

        </div>

        <div class="screen-input">

          <form
            class="screen-input-form"
            id="addForm"
          >

            <input
              type="text"
              inputmode="url"
              autocomplete="off"
              autocapitalize="off"
              spellcheck="false"
              id="urlInput"
              placeholder="유튜브 링크 붙여넣기"
              required
            >

            <button
              type="submit"
              id="addBtn"
            >
              추가
            </button>

          </form>

          <div
            class="screen-form-msg"
            id="formMsg"
          ></div>

          <div
            class="screen-manual hidden"
            id="manualMeta"
          >

            <input
              type="text"
              id="manualTitle"
              placeholder="곡 제목을 입력해 주세요"
            >

            <input
              type="text"
              id="manualArtist"
              placeholder="아티스트(가수) 이름을 입력해 주세요"
            >

            <button
              type="button"
              id="manualConfirm"
            >
              이 정보로 추가하기
            </button>

          </div>

        </div>

        <div class="screen-body">

          <div
            class="screen-panel screen-panel-player active"
            id="panelPlayer"
          >

            <div
              class="video-wrap"
              id="videoWrap"
            >

              <div id="player"></div>

              <div
                class="idle-screen"
                id="idleScreen"
              >

                <div class="idle-cat">
                  <div class="face"></div>
                </div>

                <div class="idle-text">
                  아직 재생 중인 곡이 없어요
                </div>

                <div class="idle-sub">
                  위 칸에 유튜브 링크를 붙여넣어 보세요
                </div>

              </div>

            </div>

            <div
              class="now-playing-info"
              id="nowPlayingInfo"
              style="display:none;"
            >

              <div
                class="track-title"
                id="trackTitle"
              >
                —
              </div>

              <div
                class="track-artist"
                id="trackArtist"
              >
                —
              </div>

              <div class="progress-track">
                <div
                  class="progress-fill"
                  id="progressFill"
                ></div>
              </div>

              <div class="time-row">
                <span id="curTime">0:00</span>
                <span id="remTime">-0:00</span>
              </div>

            </div>

          </div>

          <div
            class="screen-panel screen-panel-list"
            id="panelList"
          >

            <ul
              class="history-list"
              id="historyList"
            ></ul>

            <p
              class="empty-state"
              id="emptyState"
            >
              아직 추가한 노래가 없어요.<br>
              위 칸에 유튜브 링크를 넣으면 여기에 기록돼요.
            </p>

          </div>

        </div>

      </div>

    </div>

    <div class="wheel-area">

      <div class="click-wheel">

        <button
          class="wheel-btn plus-btn"
          id="volUpBtn"
          title="음량 크게"
          disabled
        >
          +
        </button>

        <button
          class="wheel-btn minus-btn"
          id="volDownBtn"
          title="음량 작게"
          disabled
        >
          &minus;
        </button>

        <button
          class="wheel-btn prev-btn"
          id="prevBtn"
          title="이전 곡"
          disabled
        >
          ⏮
        </button>

        <button
          class="wheel-btn next-btn"
          id="nextBtn"
          title="다음 곡"
          disabled
        >
          ⏭
        </button>

        <button
          class="wheel-hole"
          id="playBtn"
          title="재생/일시정지"
          disabled
        >

          <span class="play-icon"></span>

          <span class="pause-icon">
            <span></span>
            <span></span>
          </span>

        </button>

      </div>

    </div>

    <p class="device-footnote">
      재생에는 인터넷 연결이 필요해요 · 기록은 이 브라우저에만 저장돼요
    </p>

  </div>

</div>

<script>
(function(){
  "use strict";

  var STORAGE_KEY = "pinkpod_history_v1";

  var history = [];

  var currentIndex = -1;

  var player = null;

  var ytApiReady = false;

  var ytApiFailed = false;

  var progressTimer = null;

  var pendingEntry = null;


  var el = {

    addForm:
      document.getElementById('addForm'),

    urlInput:
      document.getElementById('urlInput'),

    addBtn:
      document.getElementById('addBtn'),

    formMsg:
      document.getElementById('formMsg'),

    manualMeta:
      document.getElementById('manualMeta'),

    manualTitle:
      document.getElementById('manualTitle'),

    manualArtist:
      document.getElementById('manualArtist'),

    manualConfirm:
      document.getElementById('manualConfirm'),

    historyList:
      document.getElementById('historyList'),

    emptyState:
      document.getElementById('emptyState'),

    idleScreen:
      document.getElementById('idleScreen'),

    nowPlayingInfo:
      document.getElementById('nowPlayingInfo'),

    trackTitle:
      document.getElementById('trackTitle'),

    trackArtist:
      document.getElementById('trackArtist'),

    progressFill:
      document.getElementById('progressFill'),

    curTime:
      document.getElementById('curTime'),

    remTime:
      document.getElementById('remTime'),

    topbarCount:
      document.getElementById('topbarCount'),

    playerWrap:
      document.getElementById('player'),

    videoWrap:
      document.getElementById('videoWrap'),

    prevBtn:
      document.getElementById('prevBtn'),

    nextBtn:
      document.getElementById('nextBtn'),

    playBtn:
      document.getElementById('playBtn'),

    volUpBtn:
      document.getElementById('volUpBtn'),

    volDownBtn:
      document.getElementById('volDownBtn'),

    tabPlayerBtn:
      document.getElementById('tabPlayerBtn'),

    tabListBtn:
      document.getElementById('tabListBtn'),

    panelPlayer:
      document.getElementById('panelPlayer'),

    panelList:
      document.getElementById('panelList')

  };


  function loadHistory(){

    try{

      var raw =
        localStorage.getItem(STORAGE_KEY);

      history =
        raw ? JSON.parse(raw) : [];

    }catch(e){

      history = [];

    }

  }


  function saveHistory(){

    try{

      localStorage.setItem(
        STORAGE_KEY,
        JSON.stringify(history)
      );

    }catch(e){}

  }


  function switchTab(name){

    var toPlayer =
      name === 'player';

    el.tabPlayerBtn.classList.toggle(
      'active',
      toPlayer
    );

    el.tabListBtn.classList.toggle(
      'active',
      !toPlayer
    );

    el.panelPlayer.classList.toggle(
      'active',
      toPlayer
    );

    el.panelList.classList.toggle(
      'active',
      !toPlayer
    );

  }


  el.tabPlayerBtn.addEventListener(
    'click',
    function(){
      switchTab('player');
    }
  );


  el.tabListBtn.addEventListener(
    'click',
    function(){
      switchTab('list');
    }
  );


  function extractId(raw){

    var input =
      (raw || '').trim();

    if(!input)
      return null;


    var urlMatch =
      input.match(
        /https?:\/\/[^\s"'<>]+/i
      );

    var candidate =
      urlMatch ? urlMatch[0] : input;


    if(
      !/^https?:\/\//i.test(candidate) &&
      /^(www\.|m\.|music\.)?youtu(\.be|be\.com)/i.test(candidate)
    ){

      candidate =
        'https://' + candidate;

    }


    try{

      var u =
        new URL(candidate);

      var host =
        u.hostname
          .toLowerCase()
          .replace(/^(www|m|music)\./, '');


      if(host === 'youtu.be'){

        var seg =
          u.pathname
            .split('/')
            .filter(Boolean)[0];

        if(seg)
          return seg;

      }


      if(
        host === 'youtube.com' ||
        host === 'youtube-nocookie.com'
      ){

        if(u.searchParams.get('v'))
          return u.searchParams.get('v');


        var m =
          u.pathname.match(
            /\/(embed|shorts|live)\/([^\/?]+)/
          );

        if(m)
          return m[2];

      }

    }catch(e){}


    var m2 =
      candidate.match(
        /[?&]v=([A-Za-z0-9_-]{6,})/
      ) ||

      candidate.match(
        /youtu\.be\/([A-Za-z0-9_-]{6,})/
      ) ||

      candidate.match(
        /shorts\/([A-Za-z0-9_-]{6,})/
      ) ||

      candidate.match(
        /embed\/([A-Za-z0-9_-]{6,})/
      ) ||

      candidate.match(
        /live\/([A-Za-z0-9_-]{6,})/
      );


    return m2 ? m2[1] : null;

  }


  function fmtTime(sec){

    if(
      !isFinite(sec) ||
      sec < 0
    ){

      sec = 0;

    }


    var m =
      Math.floor(sec / 60);

    var s =
      Math.floor(sec % 60);


    return (
      m +
      ':' +
      (s < 10 ? '0' : '') +
      s
    );

  }


  function setMsg(text,isError){

    el.formMsg.textContent =
      text || '';

    el.formMsg.style.color =
      isError
        ? 'var(--pink-700)'
        : 'var(--ink-500)';

  }


  var CHAR_COLORS = {

    robo:
      '#B1FC00',

    iro:
      '#b4e7ff',

    oto:
      '#63386e',

    koyo:
      '#A11010',

    nino:
      '#FF7A1A'

  };


  var CHAR_ALIASES = {

    robo:[
      '로보 프로스터',
      'robo_mixtape',
      '로보'
    ],

    iro:[
      '이로 클라우드',
      '이로'
    ],

    oto:[
      '오토 레이니',
      '아마오토',
      '오토'
    ],

    koyo:[
      '코요템페스트',
      '코라오케',
      '코요'
    ],

    nino:[
      '니노 선데이',
      '니노뮤직',
      '니노'
    ]

  };


  var THEME_VARS = [

    '--pink-000',
    '--pink-050',
    '--pink-100',
    '--pink-200',
    '--pink-300',
    '--pink-500',
    '--pink-700',
    '--pink-icon',
    '--screen-idle-a',
    '--screen-idle-b',

    '--theme-bg',
    '--theme-device',
    '--theme-wheel',
    '--theme-idle'

  ];


  function normalizeName(str){

    return (
      str || ''
    )
      .toLowerCase()
      .replace(/[\s_\-]/g,'');

  }


  function detectCharacters(artist){

    var a =
      normalizeName(artist);

    if(!a)
      return [];


    var found = [];


    for(
      var key in CHAR_ALIASES
    ){

      var list =
        CHAR_ALIASES[key];


      for(
        var i = 0;
        i < list.length;
        i++
      ){

        if(
          a.indexOf(
            normalizeName(list[i])
          ) !== -1
        ){

          found.push(key);

          break;

        }

      }

    }


    return found;

  }


  function hexToHsl(hex){

    hex =
      hex.replace('#','');


    if(hex.length === 3){

      hex =
        hex
          .split('')
          .map(function(c){
            return c + c;
          })
          .join('');

    }


    var r =
      parseInt(
        hex.substr(0,2),
        16
      ) / 255;

    var g =
      parseInt(
        hex.substr(2,2),
        16
      ) / 255;

    var b =
      parseInt(
        hex.substr(4,2),
        16
      ) / 255;


    var max =
      Math.max(r,g,b);

    var min =
      Math.min(r,g,b);

    var h,s;

    var l =
      (max + min) / 2;


    if(max === min){

      h = s = 0;

    }else{

      var d =
        max - min;

      s =
        l > 0.5
          ? d / (2 - max - min)
          : d / (max + min);


      switch(max){

        case r:

          h =
            (g - b) / d +
            (g < b ? 6 : 0);

          break;

        case g:

          h =
            (b - r) / d + 2;

          break;

        default:

          h =
            (r - g) / d + 4;

          break;

      }


      h /= 6;

    }


    return {
      h:h * 360,
      s:s * 100,
      l:l * 100
    };

  }


  function clampNum(v,min,max){

    return Math.min(
      Math.max(v,min),
      max
    );

  }


  function hslCss(h,s,l){

    return (
      'hsl(' +
      h.toFixed(1) +
      ',' +
      clampNum(s,0,100).toFixed(1) +
      '%,' +
      clampNum(l,0,100).toFixed(1) +
      '%)'
    );

  }


  function applyThemeColors(hexList){

    var primary =
      hexList[0];

    var hsl =
      hexToHsl(primary);

    var h =
      hsl.h;

    var s =
      hsl.s;

    var l =
      hsl.l;

    var root =
      document.documentElement.style;


    root.setProperty(
      '--pink-000',
      hslCss(h,s * .35,97)
    );

    root.setProperty(
      '--pink-050',
      hslCss(h,s * .45,94)
    );

    root.setProperty(
      '--pink-100',
      hslCss(h,s * .55,88)
    );

    root.setProperty(
      '--pink-200',
      hslCss(h,s * .60,81)
    );

    root.setProperty(
      '--pink-300',
      hslCss(h,s * .65,73)
    );

    root.setProperty(
      '--pink-500',
      primary
    );


    var l700 =
      clampNum(
        l * .55,
        14,
        46
      );

    var s700 =
      Math.max(s,45);


    root.setProperty(
      '--pink-700',
      hslCss(
        h,
        s700,
        l700
      )
    );


    var lIcon =
      clampNum(
        l,
        42,
        58
      );

    var sIcon =
      clampNum(
        s * .55,
        25,
        70
      );


    root.setProperty(
      '--pink-icon',
      hslCss(
        h,
        sIcon,
        lIcon
      )
    );


    root.setProperty(
      '--screen-idle-a',
      'var(--pink-000)'
    );

    root.setProperty(
      '--screen-idle-b',
      'var(--pink-050)'
    );


    if(hexList.length === 1){

      root.setProperty(
        '--theme-bg',
        'linear-gradient(' +
        '180deg,' +
        'var(--pink-050) 0%,' +
        'var(--pink-100) 40%,' +
        'var(--pink-200) 100%)'
      );


      root.setProperty(
        '--theme-device',
        'linear-gradient(' +
        '155deg,' +
        'var(--pearl-100) 0%,' +
        'var(--pink-050) 38%,' +
        'var(--pink-100) 78%,' +
        'var(--pink-200) 100%)'
      );


      root.setProperty(
        '--theme-wheel',
        'radial-gradient(' +
        'circle at 32% 28%,' +
        'var(--pearl-100),' +
        'var(--pink-100) 55%,' +
        'var(--pink-200) 100%)'
      );


      root.setProperty(
        '--theme-idle',
        'linear-gradient(' +
        '165deg,' +
        'var(--screen-idle-a),' +
        'var(--screen-idle-b))'
      );


      return;

    }


    var stops = [];

    var n =
      hexList.length;


    hexList.forEach(
      function(color,index){

        var start =
          (
            index * 100 / n
          ).toFixed(2);

        var end =
          (
            (index + 1) *
            100 / n
          ).toFixed(2);


        stops.push(
          color +
          ' ' +
          start +
          '%',

          color +
          ' ' +
          end +
          '%'
        );

      }
    );


    var mix =
      'linear-gradient(90deg,' +
      stops.join(',') +
      ')';


    var softStops = [];


    hexList.forEach(
      function(color,index){

        var start =
          (
            index * 100 / n
          ).toFixed(2);

        var end =
          (
            (index + 1) *
            100 / n
          ).toFixed(2);


        var hh =
          hexToHsl(color);


        softStops.push(

          hslCss(
            hh.h,
            hh.s * .45,
            94
          ) +
          ' ' +
          start +
          '%',

          hslCss(
            hh.h,
            hh.s * .55,
            88
          ) +
          ' ' +
          end +
          '%'

        );

      }
    );


    var softMix =
      'linear-gradient(90deg,' +
      softStops.join(',') +
      ')';


    root.setProperty(
      '--theme-bg',
      softMix
    );


    root.setProperty(
      '--theme-device',
      'linear-gradient(155deg,' +
      softStops.join(',') +
      ')'
    );


    root.setProperty(
      '--theme-wheel',
      'radial-gradient(' +
      'circle at 32% 28%,' +
      '#fff 0%,' +
      mix +
      ')'
    );


    root.setProperty(
      '--theme-idle',
      softMix
    );

  }


  function resetTheme(){

    var root =
      document.documentElement.style;


    THEME_VARS.forEach(
      function(v){

        root.removeProperty(v);

      }
    );

  }


  function canonicalizeArtist(artist){

    var result =
      (artist || '').trim();

    var keys =
      detectCharacters(result);


    keys.forEach(
      function(key){

        var canonical =
          key === 'nino'
            ? '니노'
            : key === 'koyo'
              ? '코요'
              : key === 'oto'
                ? '오토'
                : key === 'iro'
                  ? '이로'
                  : '로보';


        CHAR_ALIASES[key].forEach(
          function(alias){

            var escaped =
              alias.replace(
                /[.*+?^${}()|[\]\\]/g,
                '\\$&'
              );


            result =
              result.replace(
                new RegExp(
                  escaped,
                  'gi'
                ),
                canonical
              );

          }
        );

      }
    );


    var parts =
      result
        .split(
          /\s*(?:&|,|\/|\+|×|[Xx]|feat\.?|ft\.?)\s*/i
        )
        .filter(Boolean);


    var seen = {};


    parts =
      parts
        .map(function(part){
          return part.trim();
        })
        .filter(function(part){

          var k =
            normalizeName(part);


          if(!k || seen[k])
            return false;


          seen[k] = true;

          return true;

        });


    return parts.length
      ? parts.join(' & ')
      : result;

  }


  function updateThemeForArtist(artist){

    var keys =
      detectCharacters(artist);


    if(keys.length > 0){

      var colors =
        keys.map(function(k){
          return CHAR_COLORS[k];
        });


      applyThemeColors(colors);

    }else{

      resetTheme();

    }

  }


  var JUNK_WORDS = [

    'official music video',
    'official video',
    'official audio',
    'official mv',
    'official m/v',
    'official teaser',
    'official trailer',
    'music video',
    'lyric video',
    'lyrics video',
    'lyrics',
    'visualizer',
    'teaser',
    'trailer',
    'dance practice',
    'choreography',
    'performance video',
    'performance',
    'full ver',
    'full version',
    'ver.',
    'shorts',
    'short ver',
    'tiktok ver',
    'reaction',
    'review',
    'mv',
    'm/v',
    'audio',
    'video',
    'hd',
    '4k',
    '뮤직비디오',
    '뮤비',
    '안무영상',
    '안무',
    '가사영상',
    '가사',
    '퍼포먼스영상',
    '퍼포먼스',
    '티저',
    '예고편',
    '풀버전',
    '라이브',
    '커버',
    '리액션'

  ];


  function stripJunkSegments(text){

    return text.replace(
      /[\(\[\{【][^\)\]\}】]*[\)\]\}】]/g,
      function(match){

        var inner =
          match
            .slice(1,-1)
            .toLowerCase()
            .trim();


        for(
          var i = 0;
          i < JUNK_WORDS.length;
          i++
        ){

          if(
            inner.indexOf(
              JUNK_WORDS[i]
            ) !== -1
          ){

            return '';

          }

        }


        return match;

      }
    );

  }


  function cleanTitleText(text){

    var t =
      text || '';


    t =
      t.replace(
        /\s*[–—―ー－]\s*/g,
        ' - '
      );


    t =
      stripJunkSegments(t);


    t =
      t.replace(
        /\bofficial\s*(music\s*video|video|audio|mv|m\/v)\b/gi,
        ''
      );


    t =
      t.replace(
        /\bm\/v\b/gi,
        ''
      );


    t =
      t.replace(
        /\bmv\b/gi,
        ''
      );


    t =
      t.replace(
        /\s{2,}/g,
        ' '
      )
      .trim();


    t =
      t.replace(
        /^[-|:∙·\s]+|[-|:∙·\s]+$/g,
        ''
      )
      .trim();


    return t;

  }


  function cleanChannelName(name){

    var n =
      (name || '').trim();


    n =
      n.replace(
        /\s*-\s*topic$/i,
        ''
      );


    n =
      n.replace(
        /vevo$/i,
        ''
      );


    n =
      n.replace(
        /(공식\s*채널|official\s*channel)$/i,
        ''
      );


    return n.trim();

  }


  function extractCollabArtist(
    title,
    channelArtist
  ){

    var result = {
      title:title,
      artist:channelArtist
    };


    var featRe =
      /[\(\[]\s*(?:feat\.?|ft\.?|with)\s+([^\)\]]+)[\)\]]/i;


    var featMatch =
      title.match(featRe);


    if(featMatch){

      var other =
        featMatch[1].trim();


      var cleanedTitle =
        title
          .replace(
            featMatch[0],
            ''
          )
          .replace(
            /\s{2,}/g,
            ' '
          )
          .trim();


      if(
        other &&
        normalizeName(other) !==
        normalizeName(channelArtist)
      ){

        result.title =
          cleanedTitle;

        result.artist =
          channelArtist +
          ' & ' +
          other;

      }


      return result;

    }


    var dashIdx =
      title.indexOf(' - ');


    if(dashIdx > -1){

      var left =
        title
          .slice(0,dashIdx)
          .trim();

      var right =
        title
          .slice(dashIdx + 3)
          .trim();


      var sepMatch =
        left.match(
          /^(.{1,40}?)\s*(,|&|[Xx]|×)\s*(.{1,40})$/
        );


      if(
        sepMatch &&
        right
      ){

        var a1 =
          sepMatch[1].trim();

        var a2 =
          sepMatch[3].trim();


        if(a1 && a2){

          result.title =
            right;

          result.artist =
            a1 +
            ' & ' +
            a2;

        }

      }

    }


    return result;

  }


  function parseVideoMeta(
    rawTitle,
    channelName
  ){

    var artist =
      cleanChannelName(
        channelName || ''
      ) ||
      '아티스트 미상';


    var title =
      cleanTitleText(
        rawTitle || ''
      );


    var collab =
      extractCollabArtist(
        title,
        artist
      );


    title =
      collab.title ||
      title;


    artist =
      collab.artist ||
      artist;


    return {

      title:
        title ||
        rawTitle ||
        '제목 없음',

      artist:
        canonicalizeArtist(
          artist ||
          '아티스트 미상'
        ) ||
        '아티스트 미상'

    };

  }


  function fetchMeta(id){

    var target =
      'https://
