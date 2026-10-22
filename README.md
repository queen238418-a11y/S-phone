# S-phone
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>PRISON PHONE</title>

<script>
/* ==================================================
   ★ 여기에서 이름 / 배경 / 대사 / 게시물 / 뉴스 수정
   ================================================== */

const CONFIG = {
  owner: "PRISON",

  // 배경 사진을 올렸다면 정확한 파일 이름 입력
  // 예: wallpaper: "다운로드 (9).jpg"
  wallpaper: "",

  carrier: "SKT",
  battery: 70,

  // 잠금화면 글자와 상단 아이콘 색
  lockColor: "#ffffff",
  statusColor: "#ffffff",

  // true → 실제 현재 시간
  // false → 아래에 적은 시간
  liveClock: false,
  time: "2:14",
  date: "22일 (목)",

  musicTitle: "Your likes",
  musicArtist: "S",

  contacts: [
    {
      id: "mio",
      name: "미오",
      emoji: "🦊",
      number: "09000000001",
      callLines: [
        "여기에 통화 대사를 입력해.",
        "이렇게 한 줄씩 순서대로 나타나."
      ],
      audio: ""
    },
    {
      id: "yuu",
      name: "유우",
      emoji: "🦔",
      number: "09000000002",
      callLines: ["유우의 통화 대사를 입력해."],
      audio: ""
    },
    {
      id: "shizuka",
      name: "시즈카",
      emoji: "🦌",
      number: "09000000003",
      callLines: ["시즈카의 통화 대사를 입력해."],
      audio: ""
    },
    {
      id: "seina",
      name: "세이나",
      emoji: "🐇",
      number: "09000000004",
      callLines: ["세이나의 통화 대사를 입력해."],
      audio: ""
    },
    {
      id: "itsuki",
      name: "이츠키",
      emoji: "🐺",
      number: "09000000005",
      callLines: ["이츠키의 통화 대사를 입력해."],
      audio: ""
    },
    {
      id: "rea",
      name: "레아",
      emoji: "🐶",
      number: "09000000006",
      callLines: ["레아의 통화 대사를 입력해."],
      audio: ""
    }
  ],

  // 기존 문자 기록
  // me: false → 상대가 보낸 문자
  // me: true  → 휴대폰 주인이 보낸 문자
  chats: {
    mio: [
      {
        me: false,
        text: "여기에 받은 문자 내용을 입력해.",
        time: "13:50"
      },
      {
        me: true,
        text: "여기에 보낸 문자 내용을 입력해.",
        time: "13:51"
      }
    ],
    yuu: [
      {
        me: false,
        text: "기존 대화 내용을 여기에 입력해.",
        time: "12:10"
      }
    ],
    shizuka: [],
    seina: [],
    itsuki: [],
    rea: []
  },

  // 답장을 보내면 자동으로 오는 문자
  // 자동 답장이 필요 없으면 빈칸 ""으로 두기
  autoReplies: {
    mio: "여기에 자동 답장 내용을 입력해.",
    yuu: "",
    shizuka: "",
    seina: "",
    itsuki: "",
    rea: ""
  },

  // 첫 잠금 해제 후 자동 이벤트
  // after: 몇 초 뒤 발생할지
  // type: "message" 또는 "call"
  // 자동 이벤트를 없애려면 events: [] 로 변경
  events: [
    {
      after: 12,
      type: "message",
      contact: "mio",
      text: "새 문자가 도착했어. 여기에 대사를 넣어줘."
    },
    {
      after: 28,
      type: "call",
      contact: "mio"
    },
    {
      after: 55,
      type: "message",
      contact: "yuu",
      text: "다른 앱을 보고 있어도 알림이 떠."
    }
  ],

  notes: [
    {
      id: "note1",
      title: "메모 제목",
      body: "여기에 메모 내용을 입력해.\n\n메모 앱 안에서도 수정할 수 있어."
    },
    {
      id: "note2",
      title: "해야 할 일",
      body: "□ 첫 번째\n□ 두 번째\n□ 세 번째"
    }
  ],

  profile: {
    name: "내 계정",
    handle: "@my_account",
    emoji: "🤍"
  },

  posts: [
    {
      id: "post1",
      name: "PRISON Official",
      handle: "@PRISON_official",
      emoji: "🔒",
      time: "10분",
      text: "여기에 공식 계정 게시물을 입력해.",
      image: "",
      likes: 1280,
      comments: [
        {
          name: "팬 계정",
          text: "여기에 답글을 입력해."
        }
      ]
    },
    {
      id: "post2",
      name: "팬 계정",
      handle: "@prison_fan",
      emoji: "🌷",
      time: "25분",
      text: "여기에 팬이나 멤버 계정의 게시물을 입력해.",
      image: "",
      likes: 24,
      comments: []
    }
  ],

  /*
    뉴스 설정
    category: "연예", "뉴스", "스포츠", "날씨"
    section: "뉴스", "연재", "포토", "월간다음"

    image: "사진파일.jpg" → 뉴스 썸네일
    body → 기사 본문
    줄바꿈은 \n, 문단 나누기는 \n\n
  */
  news: [
    {
      id: "news1",
      category: "연예",
      section: "뉴스",
      title: "PRISON, 새로운 무대 예고… 여기에 기사 제목을 입력해",
      source: "엔터뉴스",
      time: "1분 전",
      image: "",
      body: "여기에 기사 본문을 입력해.\n\n이렇게 문단을 나눌 수 있어.\n\n제목과 사진, 언론사 이름도 자유롭게 바꾸면 돼."
    },
    {
      id: "news2",
      category: "연예",
      section: "뉴스",
      title: "두 번째 뉴스 제목을 입력해 주세요",
      source: "스타데일리",
      time: "2분 전",
      image: "",
      body: "두 번째 기사 본문을 입력해."
    },
    {
      id: "news3",
      category: "연예",
      section: "뉴스",
      title: "세 번째 뉴스 제목… 목록에는 두 줄까지 표시됩니다",
      source: "뮤직타임즈",
      time: "2분 전",
      image: "",
      body: "세 번째 기사 본문을 입력해."
    },
    {
      id: "news4",
      category: "연예",
      section: "뉴스",
      title: "무대 뒤 이야기, 새로운 인터뷰 공개",
      source: "데일리엔터",
      time: "3분 전",
      image: "",
      body: "인터뷰 내용을 입력해."
    },
    {
      id: "news5",
      category: "연예",
      section: "뉴스",
      title: "오늘의 연예 소식… 기사 제목을 자유롭게 수정해 주세요",
      source: "엔터뉴스",
      time: "3분 전",
      image: "",
      body: "기사 내용을 입력해."
    },
    {
      id: "news6",
      category: "연예",
      section: "포토",
      title: "[포토] 여기에 사진 기사 제목을 입력해",
      source: "포토뉴스",
      time: "10분 전",
      image: "",
      body: "사진에 대한 설명을 입력해."
    },
    {
      id: "news7",
      category: "뉴스",
      section: "뉴스",
      title: "일반 뉴스 제목 예시",
      source: "데일리뉴스",
      time: "5분 전",
      image: "",
      body: "일반 뉴스 본문을 입력해."
    },
    {
      id: "news8",
      category: "스포츠",
      section: "뉴스",
      title: "스포츠 뉴스 제목 예시",
      source: "스포츠데일리",
      time: "8분 전",
      image: "",
      body: "스포츠 기사 본문을 입력해."
    }
  ],

  photos: [
    // 아래처럼 추가하면 사진 앱에 나타남
    // { image: "photo1.jpg", caption: "사진 설명" },
    // { image: "photo2.png", caption: "사진 설명" }
  ]
};
</script>

<style>
* {
  box-sizing: border-box;
}

[hidden] {
  display: none !important;
}

body {
  margin: 0;
  background: #e8e5e9;
  color: #111;
  font-family: -apple-system, BlinkMacSystemFont,
    "Segoe UI", sans-serif;
}

button,
input,
textarea {
  font: inherit;
}

button {
  padding: 0;
  border: 0;
  background: none;
  color: inherit;
  cursor: pointer;
  -webkit-tap-highlight-color: transparent;
}

button:focus-visible,
input:focus-visible,
textarea:focus-visible {
  outline: 2px solid #007aff;
  outline-offset: 3px;
}

svg {
  display: block;
  width: 24px;
  height: 24px;
  flex-shrink: 0;
}

#stage {
  position: relative;
  margin: auto;
}

#phone {
  position: absolute;
  top: 0;
  left: 0;
  width: 390px;
  height: 844px;
  overflow: hidden;
  isolation: isolate;
  transform-origin: top left;
  border-radius: 42px;
  background: #b9adb9;
  box-shadow:
    0 0 0 6px #252429,
    0 24px 80px #392b4433;
}

#wallpaper {
  position: absolute;
  inset: 0;
  z-index: -1;
  background: linear-gradient(145deg, #b1a4b1, #c5b9c5);
  background-size: cover;
  background-position: center;
}

/* 上部ではなく、上段のステータス表示 */
#status {
  position: absolute;
  top: 18px;
  left: 49px;
  right: 28px;
  height: 19px;
  z-index: 40;
  display: flex;
  align-items: center;
  justify-content: space-between;
  color: var(--status-color, #fff);
  pointer-events: none;
}

.carrier {
  font-size: 16px;
  font-weight: 500;
  letter-spacing: -.5px;
}

.status-right {
  position: relative;
  display: flex;
  align-items: center;
  gap: 7px;
}

.signal {
  width: 20px;
  height: 16px;
}

.wifi {
  width: 21px;
  height: 16px;
}

.status-right::after {
  content: "";
  position: absolute;
  top: 27px;
  right: 10px;
  width: 55px;
  height: 2.5px;
  border-radius: 5px;
  background: currentColor;
  opacity: .8;
}

.battery {
  position: relative;
  width: 27px;
  height: 15px;
  border-radius: 4px;
  background: var(--battery-empty, #ffffff55);
}

.battery::after {
  content: "";
  position: absolute;
  right: -3px;
  top: 5px;
  width: 2px;
  height: 5px;
  background: currentColor;
  opacity: .4;
  border-radius: 0 2px 2px 0;
}

.battery-fill {
  height: 100%;
  border-radius: 4px 0 0 4px;
  background: currentColor;
}

.battery-number {
  position: absolute;
  inset: 0;
  display: grid;
  place-items: center;
  color: var(--battery-number, #b9adb9);
  font-family: Arial, sans-serif;
  font-size: 13px;
  font-weight: 400;
  line-height: 1;
}

#main {
  position: absolute;
  inset: 0;
}

/* 잠금화면 */
.lock {
  position: relative;
  height: 100%;
  color: var(--lock-color, #fff);
}

.lock-symbol {
  position: absolute;
  top: 56px;
  left: 189px;
  width: 13px;
  height: 18px;
}

.lock-date {
  position: absolute;
  top: 89px;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 12px;
  font-size: 22px;
  font-weight: 500;
  letter-spacing: -.6px;
}

.lock-date svg {
  width: 20px;
  height: 20px;
}

.lock-clock {
  position: absolute;
  top: 114px;
  left: 0;
  right: 0;
  text-align: center;
  font-family: Georgia, "Times New Roman", serif;
  font-size: 105px;
  font-weight: 400;
  line-height: 1.12;
  letter-spacing: -5px;
}

.lock-widgets {
  position: absolute;
  top: 230px;
  left: 34px;
  right: 34px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 18px;
}

.music-widget {
  display: flex;
  align-items: center;
  gap: 8px;
  text-align: left;
}

.music-disc {
  display: grid;
  place-items: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: #ffffff29;
  flex-shrink: 0;
}

.music-disc svg {
  width: 27px;
  height: 25px;
}

.music-copy {
  font-size: 15px;
  line-height: 1.35;
}

.music-copy strong {
  display: block;
  font-size: 14px;
}

.music-copy span {
  display: block;
  margin-top: 3px;
}

.battery-widget {
  font-size: 16px;
  line-height: 1.25;
}

.battery-widget-top {
  display: flex;
  align-items: center;
  gap: 9px;
}

.battery-widget-top svg {
  width: 13px;
  height: 18px;
}

.battery-widget > span {
  display: block;
  margin-top: 2px;
}

.battery-track {
  height: 8px;
  margin-top: 7px;
  overflow: hidden;
  border-radius: 10px;
  background: #ffffff33;
}

.battery-track div {
  height: 100%;
  border-radius: inherit;
  background: currentColor;
}

.lock-shortcuts {
  position: absolute;
  bottom: 50px;
  left: 46px;
  right: 46px;
  display: flex;
  justify-content: space-between;
}

.lock-shortcut {
  display: grid;
  place-items: center;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  color: #fff;
  background: #0004;
  backdrop-filter: blur(12px);
}

.lock-shortcut.active {
  color: #222;
  background: #fff;
}

.lock-shortcut svg {
  width: 26px;
  height: 28px;
}

.unlock-hint {
  position: absolute;
  bottom: 32px;
  left: 0;
  right: 0;
  text-align: center;
  font-size: 10px;
  opacity: .65;
}

.lock-notifications {
  position: absolute;
  top: 335px;
  left: 15px;
  right: 15px;
}

.lock-notification {
  width: 100%;
  padding: 15px;
  border-radius: 20px;
  background: #ffffffbb;
  backdrop-filter: blur(20px);
  color: #242128;
  text-align: left;
}

.lock-notification small,
.lock-notification strong {
  display: block;
  margin-bottom: 5px;
}

.lock-notification small {
  font-size: 10px;
  color: #777;
}

.lock-notification strong {
  font-size: 14px;
}

.lock-notification p {
  margin: 0;
  font-size: 13px;
  line-height: 1.5;
}

#homebar {
  position: absolute;
  bottom: 0;
  left: 50%;
  z-index: 45;
  transform: translateX(-50%);
  width: 160px;
  height: 30px;
}

#homebar::after {
  content: "";
  position: absolute;
  left: 10px;
  right: 10px;
  bottom: 8px;
  height: 5px;
  border-radius: 9px;
  background: var(--bar-color, #fff);
}

/* 홈 화면 */
.home {
  height: 100%;
  padding: 74px 25px 130px;
  color: #fff;
}

.home-widgets {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
  margin-bottom: 30px;
}

.home-widget {
  height: 143px;
  overflow: hidden;
  padding: 18px;
  border-radius: 24px;
  background: #ffffff35;
  backdrop-filter: blur(15px);
  text-align: left;
}

.home-widget small {
  font-size: 11px;
}

.home-widget h2 {
  margin: 10px 0 5px;
  font-size: 28px;
  letter-spacing: -1px;
}

.home-widget p {
  margin: 5px 0;
  font-size: 12px;
  line-height: 1.6;
}

.note-widget {
  color: #5d5034;
  background: #fff4dbe8;
}

.note-widget h2 {
  margin-top: 17px;
  font-size: 17px;
}

.apps {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 25px 12px;
}

.app-button {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 6px;
  color: #fff;
  font-size: 11px;
}

.app-tile {
  position: relative;
  display: grid;
  place-items: center;
  width: 59px;
  height: 59px;
  border-radius: 15px;
  box-shadow: 0 3px 8px #0001;
}

.app-tile svg {
  width: 36px;
  height: 36px;
}

.app-tile.messages,
.app-tile.phone {
  background: linear-gradient(#64ed79, #1cbd40);
  color: #fff;
}

.app-tile.twitter {
  color: #fff;
  background: #17181b;
}

.app-tile.notes {
  color: #c4c4c4;
  background: linear-gradient(#ffd850 26%, #eee 26%, #fff 29%);
}

.app-tile.notes svg {
  width: 39px;
  height: 28px;
  margin-top: 10px;
}

.app-tile.internet {
  color: #098cff;
  background: #fff;
}

.app-tile.photos {
  background: #fff;
}

.app-tile.settings {
  color: #57585b;
  background: #c8c9ce;
}

.badge {
  position: absolute;
  top: -7px;
  right: -7px;
  display: grid;
  place-items: center;
  min-width: 21px;
  height: 21px;
  padding: 0 5px;
  border-radius: 20px;
  background: #ff3b30;
  color: #fff;
  font-size: 12px;
}

.dock {
  position: absolute;
  left: 14px;
  right: 14px;
  bottom: 33px;
  display: flex;
  justify-content: space-around;
  padding: 15px 8px;
  border-radius: 29px;
  background: #ffffff3b;
  backdrop-filter: blur(25px);
}

.home-lock {
  position: absolute;
  right: 20px;
  bottom: 135px;
  font-size: 12px;
}

/* 앱 공통 */
.app {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  min-height: 0;
  padding: 64px 0 30px;
  background: #fff;
}

.app.dark {
  color: #f4f4f5;
  background: #1c1d20;
}

.appbar {
  display: flex;
  align-items: center;
  gap: 9px;
  flex-shrink: 0;
  min-height: 47px;
  padding: 5px 16px;
  border-bottom: 1px solid #0000000c;
}

.appbar h1 {
  flex: 1;
  margin: 0;
  font-size: 17px;
}

.appbar button {
  display: flex;
  align-items: center;
  gap: 2px;
  padding: 7px 0;
  color: #007aff;
  font-size: 15px;
}

.appbar svg {
  width: 21px;
  height: 21px;
}

.scroll {
  flex: 1;
  min-height: 0;
  overflow-y: auto;
  overscroll-behavior: contain;
  scrollbar-width: none;
}

.scroll::-webkit-scrollbar {
  display: none;
}

.large-title {
  margin: 17px 20px 14px;
  font-size: 32px;
  font-weight: 750;
  letter-spacing: -1px;
}

.search-wrap {
  padding: 0 16px 12px;
}

.search {
  width: 100%;
  padding: 10px 13px;
  border: 0;
  border-radius: 11px;
  background: #eeeef0;
  color: inherit;
  font-size: 14px;
}

.dark .search {
  background: #303135;
}

.empty {
  padding: 40px 25px;
  color: #89898f;
  text-align: center;
  font-size: 14px;
  line-height: 1.8;
}

.list-row {
  display: flex;
  align-items: center;
  gap: 12px;
  width: 100%;
  padding: 16px 18px;
  border-bottom: 1px solid #eee;
  text-align: left;
}

.avatar {
  display: grid;
  place-items: center;
  width: 43px;
  height: 43px;
  border-radius: 50%;
  background: #eeeef3;
  font-size: 23px;
  flex-shrink: 0;
}

.row-copy {
  flex: 1;
  min-width: 0;
}

.row-title {
  display: flex;
  align-items: center;
  gap: 7px;
  font-size: 15px;
  font-weight: 650;
}

.row-preview {
  margin-top: 5px;
  overflow: hidden;
  color: #929296;
  font-size: 13px;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.tiny {
  margin-left: auto;
  color: #999;
  font-size: 11px;
  font-weight: 400;
}

.unread-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #007aff;
  flex-shrink: 0;
}

/* 문자 */
.chat-content {
  padding: 16px 14px;
}

.chat-day {
  margin: 3px 0 20px;
  text-align: center;
  color: #93939a;
  font-size: 10px;
}

.bubble-wrap {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-bottom: 12px;
}

.bubble-wrap.me {
  align-items: flex-end;
}

.bubble {
  max-width: 82%;
  padding: 9px 13px;
  border-radius: 18px;
  background: #e9e9eb;
  font-size: 14px;
  line-height: 1.6;
  white-space: pre-wrap;
  overflow-wrap: anywhere;
}

.me .bubble {
  color: #fff;
  background: #007aff;
}

.bubble-time {
  margin: 4px 5px 0;
  color: #999;
  font-size: 9px;
}

.composer {
  display: flex;
  align-items: center;
  gap: 8px;
  flex-shrink: 0;
  padding: 9px 12px;
  border-top: 1px solid #eee;
}

.composer input {
  flex: 1;
  min-width: 0;
  width: 0;
  padding: 9px 12px;
  border: 1px solid #ddd;
  border-radius: 22px;
  font-size: 16px;
}

.send {
  width: 34px;
  height: 34px;
  border-radius: 50%;
  background: #007aff;
  color: #fff;
  font-size: 23px;
}

/* 메모 */
.notes-app,
.settings-app {
  background: #f4f3f0;
}

.note-list {
  margin: 0 15px 15px;
  overflow: hidden;
  border-radius: 12px;
  background: #fff;
}

.note-row {
  display: block;
  width: 100%;
  padding: 16px;
  border-bottom: 1px solid #eee;
  text-align: left;
}

.note-row strong,
.note-row span {
  display: block;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.note-row strong {
  font-size: 15px;
}

.note-row span {
  margin-top: 7px;
  color: #999;
  font-size: 12px;
}

.note-editor {
  display: flex;
  flex-direction: column;
  flex: 1;
  min-height: 0;
  padding: 13px 20px;
}

.note-editor input {
  width: 100%;
  padding: 10px 0;
  border: 0;
  background: none;
  font-size: 25px;
  font-weight: 700;
}

.note-editor textarea {
  flex: 1;
  min-height: 100px;
  width: 100%;
  padding: 9px 0;
  border: 0;
  resize: none;
  background: none;
  font-size: 16px;
  line-height: 1.9;
}

.save-state {
  padding: 5px;
  color: #999;
  text-align: center;
  font-size: 10px;
}

/* 트위터 */
.social-tabs {
  display: flex;
  flex-shrink: 0;
  border-bottom: 1px solid #eee;
}

.social-tabs button {
  flex: 1;
  padding: 13px 5px;
  border-bottom: 3px solid transparent;
  color: #999;
  font-size: 13px;
}

.social-tabs .selected {
  border-color: #139cf5;
  color: #111;
  font-weight: 700;
}

.post {
  padding: 17px 16px;
  border-bottom: 1px solid #e9e9ec;
}

.post-head {
  display: flex;
  align-items: center;
  gap: 9px;
}

.post-head strong {
  font-size: 13px;
}

.handle {
  margin-top: 3px;
  color: #929298;
  font-size: 11px;
}

.post-text {
  margin: 12px 0;
  font-size: 14px;
  line-height: 1.7;
  white-space: pre-wrap;
  overflow-wrap: anywhere;
}

.post-image {
  width: 100%;
  max-height: 230px;
  object-fit: cover;
  border-radius: 12px;
}

.post-actions {
  display: flex;
  justify-content: space-between;
  margin-top: 10px;
  color: #8c8d95;
}

.post-actions button {
  display: flex;
  align-items: center;
  gap: 6px;
  padding: 4px;
  font-size: 11px;
}

.post-actions svg {
  width: 17px;
  height: 17px;
}

.post-actions .liked {
  color: #e54b80;
}

.post-actions .saved {
  color: #008bff;
}

.tweet-form {
  padding: 15px;
  border-bottom: 1px solid #eee;
}

.tweet-form textarea {
  width: 100%;
  height: 95px;
  padding: 10px;
  border: 0;
  resize: vertical;
  font-size: 16px;
  line-height: 1.6;
}

.primary {
  padding: 9px 17px;
  border-radius: 20px;
  color: #fff;
  background: #007aff;
  font-size: 13px;
}

.tweet-form .primary {
  display: block;
  margin-left: auto;
}

/* 전화 앱 */
.tabbar {
  display: flex;
  justify-content: space-around;
  flex-shrink: 0;
  padding: 8px 5px 2px;
  border-top: 1px solid #eee;
}

.tabbar button {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3px;
  min-width: 60px;
  color: #999;
  font-size: 10px;
}

.tabbar .selected {
  color: #007aff;
}

.tabbar svg {
  width: 22px;
  height: 22px;
}

.keypad-number {
  height: 55px;
  padding-top: 12px;
  text-align: center;
  font-size: 29px;
  letter-spacing: 2px;
}

.keypad {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 13px 22px;
  padding: 5px 49px 18px;
}

.key {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 68px;
  height: 68px;
  border-radius: 50%;
  background: #eeeef0;
  font-size: 30px;
}

.key small {
  font-size: 9px;
  letter-spacing: 2px;
}

.dial-actions {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 5px 0 18px;
}

.dial-call {
  display: grid;
  place-items: center;
  width: 65px;
  height: 65px;
  border-radius: 50%;
  color: #fff;
  background: #32c75a;
}

.dial-delete {
  position: absolute;
  left: calc(50% + 70px);
}

/* 인터넷 앱 */
.browser-address {
  display: flex;
  align-items: center;
  gap: 8px;
  flex-shrink: 0;
  margin: 4px 14px 13px;
  padding: 9px 12px;
  border-radius: 12px;
  color: #ddd;
  background: #303135;
  font-size: 12px;
}

.browser-address > svg {
  width: 13px;
  height: 13px;
}

.browser-address span {
  flex: 1;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.browser-address button svg {
  width: 17px;
  height: 17px;
}

.portal-head {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 16px 16px 19px;
  border-bottom: 1px solid #303135;
}

.portal-logo {
  display: grid;
  place-items: center;
  width: 30px;
  height: 30px;
  border-radius: 10px;
  color: #fff;
  background: conic-gradient(
    #00b394, #2194ff, #a452ed,
    #ff5386, #ffd941, #00b394
  );
  font-size: 25px;
  font-weight: 850;
}

.portal-head strong {
  font-size: 23px;
  letter-spacing: -1px;
}

.portal-cats {
  display: flex;
  flex: 1;
  gap: 10px;
}

.portal-cats button {
  color: #a7a7ab;
  font-size: 15px;
}

.portal-nav {
  display: flex;
  justify-content: space-around;
  gap: 5px;
  padding: 0 16px;
  border-bottom: 8px solid #131416;
}

.portal-nav button {
  position: relative;
  padding: 21px 4px 24px;
  color: #aaa;
  font-size: 17px;
  font-weight: 650;
  white-space: nowrap;
}

.portal-nav .selected {
  color: #fff;
}

.portal-nav .selected::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 4px;
  right: 4px;
  height: 3px;
  border-radius: 3px;
  background: #fff;
}

.news-search {
  padding: 14px 16px 0;
}

.news-heading {
  margin: 20px 16px 25px;
  font-size: 20px;
  letter-spacing: -.6px;
}

.news-row {
  display: flex;
  align-items: center;
  gap: 17px;
  width: calc(100% - 32px);
  min-height: 97px;
  margin: 0 16px;
  padding: 12px 0;
  border-top: 1px solid #343538;
  text-align: left;
}

.news-copy {
  flex: 1;
  min-width: 0;
}

.news-title {
  display: -webkit-box;
  overflow: hidden;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  font-size: 17px;
  font-weight: 400;
  line-height: 1.5;
  letter-spacing: -.35px;
}

.news-meta {
  margin-top: 9px;
  color: #85858a;
  font-size: 13px;
}

.news-thumb {
  width: 108px;
  height: 73px;
  object-fit: cover;
  border-radius: 9px;
  flex-shrink: 0;
}

.news-placeholder {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 5px;
  color: #dfd7ed;
  background: linear-gradient(135deg, #464052, #252d40);
  font-size: 11px;
}

.news-placeholder svg {
  opacity: .7;
}

.article {
  padding: 23px 19px 40px;
}

.article-back {
  display: flex;
  align-items: center;
  gap: 4px;
  margin-bottom: 22px;
  color: #9ebdff;
  font-size: 14px;
}

.article-label,
.article-meta {
  color: #a1a1a8;
  font-size: 12px;
}

.article h2 {
  margin: 14px 0;
  font-size: 25px;
  line-height: 1.5;
  letter-spacing: -.8px;
}

.article-meta {
  margin: 15px 0 25px;
}

.article img {
  width: 100%;
  margin-bottom: 15px;
  border-radius: 10px;
}

.article-body {
  font-size: 16px;
  line-height: 1.95;
  white-space: pre-wrap;
  overflow-wrap: anywhere;
}

.browser-bottom {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-shrink: 0;
  padding: 10px 20px 4px;
  border-top: 1px solid #36363a;
  color: #b5caff;
  background: #242528;
}

.browser-bottom button {
  padding: 2px;
}

.browser-bottom button:disabled {
  opacity: .25;
}

.browser-bottom svg {
  width: 23px;
  height: 23px;
}

/* 사진 */
.photos-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2px;
}

.photo {
  overflow: hidden;
  aspect-ratio: 1;
  background: #f1f1f4;
}

.photo img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.photo-view {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

/* 설정 */
.settings-group {
  margin: 15px;
  overflow: hidden;
  border-radius: 13px;
  background: #fff;
}

.setting-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  padding: 16px;
  border-bottom: 1px solid #eee;
  text-align: left;
  font-size: 14px;
}

.setting-row input {
  width: 20px;
  height: 20px;
  accent-color: #34c759;
}

.setting-help {
  margin: 15px 22px;
  color: #888;
  font-size: 12px;
  line-height: 1.8;
}

.danger {
  color: #ff453a !important;
}

/* 문자 알림 */
#notification {
  position: absolute;
  top: 58px;
  left: 10px;
  right: 10px;
  z-index: 60;
  padding: 13px 15px;
  border-radius: 22px;
  color: #222;
  background: #f3f1f2ed;
  backdrop-filter: blur(20px);
  box-shadow: 0 7px 30px #0002;
  text-align: left;
}

#notification small,
#notification strong,
#notification span {
  display: block;
}

#notification small {
  margin-bottom: 6px;
  color: #777;
  font-size: 10px;
}

#notification strong {
  margin-bottom: 3px;
  font-size: 14px;
}

#notification span {
  overflow: hidden;
  font-size: 13px;
  white-space: nowrap;
  text-overflow: ellipsis;
}

/* 통화 */
#call {
  position: absolute;
  inset: 0;
  z-index: 80;
  padding: 115px 24px 30px;
  color: #fff;
  background: linear-gradient(160deg, #424151, #191d2c);
  text-align: center;
}

.call-avatar {
  display: grid;
  place-items: center;
  width: 80px;
  height: 80px;
  margin: 0 auto 20px;
  border-radius: 50%;
  background: #ffffff15;
  font-size: 40px;
}

.call-name {
  margin-bottom: 9px;
  font-size: 31px;
}

.call-state {
  color: #bfc1cb;
  font-size: 14px;
}

.call-script {
  max-height: 280px;
  margin: 35px 6px 0;
  overflow-y: auto;
  scrollbar-width: none;
}

.call-script p {
  margin: 0 0 13px;
  font-size: 16px;
  line-height: 1.7;
  white-space: pre-wrap;
}

.call-actions {
  position: absolute;
  bottom: 80px;
  left: 50px;
  right: 50px;
  display: flex;
  justify-content: space-around;
}

.call-action button {
  display: grid;
  place-items: center;
  width: 72px;
  height: 72px;
  margin: 0 auto 10px;
  border-radius: 50%;
}

.call-action span {
  font-size: 12px;
}

.call-action svg {
  width: 29px;
  height: 29px;
}

.call-reject {
  background: #ff453a;
}

.call-reject svg {
  transform: rotate(135deg);
}

.call-answer {
  background: #30d158;
}

/* 확인창 */
#dialog {
  position: absolute;
  inset: 0;
  z-index: 100;
  display: grid;
  place-items: center;
  background: #0005;
  backdrop-filter: blur(4px);
}

.dialog-card {
  width: 285px;
  padding: 22px;
  border-radius: 22px;
  color: #222;
  background: #f7f7f9;
  text-align: center;
}

.dialog-card p {
  margin: 10px 0 20px;
  font-size: 14px;
  line-height: 1.7;
}

.dialog-actions {
  display: flex;
  justify-content: center;
  gap: 10px;
}

.dialog-actions button {
  padding: 10px 16px;
  border-radius: 12px;
  color: #007aff;
  background: #e8e8ed;
}

#toast {
  position: absolute;
  bottom: 42px;
  left: 35px;
  right: 35px;
  z-index: 95;
  padding: 12px 16px;
  border-radius: 13px;
  color: #fff;
  background: #222e;
  text-align: center;
  font-size: 12px;
  line-height: 1.6;
}

#flashlightGlow {
  position: absolute;
  inset: 0;
  z-index: -1;
  background: radial-gradient(
    ellipse at bottom,
    #ffffff66,
    transparent 70%
  );
  pointer-events: none;
}

@media (max-width: 450px) {
  body {
    background: #1d1c21;
  }

  #phone {
    border-radius: 0;
    box-shadow: none;
  }
}
</style>
</head>

<body>
<div id="stage">
  <div id="phone">

    <div id="wallpaper"></div>
    <div id="flashlightGlow" hidden></div>

    <div id="status">
      <span class="carrier" id="carrier"></span>

      <div class="status-right">
        <svg class="signal" viewBox="0 0 22 18"
          aria-label="통신 신호">
          <rect x="0" y="12" width="4" height="6"
            rx="1.3" fill="currentColor"/>
          <rect x="6" y="8" width="4" height="10"
            rx="1.3" fill="currentColor"/>
          <rect x="12" y="4" width="4" height="14"
            rx="1.3" fill="currentColor"/>
          <rect x="18" y="0" width="4" height="18"
            rx="1.3" fill="currentColor" opacity=".3"/>
        </svg>

        <svg class="wifi" viewBox="0 0 24 19"
          aria-label="와이파이">
          <path d="M2 5Q12-3 22 5M5.5 10Q12 4.5 18.5 10"
            fill="none" stroke="currentColor"
            stroke-width="3.4"/>
          <path d="M9 14Q12 11.5 15 14L12 18Z"
            fill="currentColor"/>
        </svg>

        <div class="battery" id="batteryIcon"
          role="img" aria-label="배터리">
          <div class="battery-fill" id="batteryFill"></div>
          <span class="battery-number" id="batteryNumber"></span>
        </div>
      </div>
    </div>

    <main id="main"></main>

    <button id="homebar" aria-label="잠금 해제"></button>

    <button id="notification" hidden></button>

    <section id="call" role="dialog"
      aria-modal="true" aria-label="전화" hidden></section>

    <section id="dialog" role="dialog"
      aria-modal="true" aria-labelledby="dialogTitle" hidden></section>

    <div id="toast" role="status" hidden></div>

  </div>
</div>

<script>
/* ==================================================
   아래는 작동 코드
   ================================================== */

const $ = id => document.getElementById(id);

function esc(value) {
  return String(value ?? "").replace(/[&<>"']/g, c => ({
    "&": "&amp;",
    "<": "&lt;",
    ">": "&gt;",
    '"': "&quot;",
    "'": "&#39;"
  }[c]));
}

function safeURL(value) {
  if (!value) return "";
  try {
    const url = new URL(value, location.href);
    return ["http:", "https:", "file:"].includes(url.protocol)
      ? url.href : "";
  } catch {
    return "";
  }
}

function img(src, className = "", alt = "") {
  return `<img src="${esc(safeURL(src))}"
    class="${className}" alt="${esc(alt)}" loading="lazy">`;
}

const SHAPES = {
  back: `<path d="m15 5-7 7 7 7"/>`,

  forward: `<path d="m9 5 7 7-7 7"/>`,

  lock: `
    <rect x="5" y="10" width="14" height="12"
      rx="2" fill="currentColor" stroke="none"/>
    <path d="M8 10V6a4 4 0 0 1 8 0v4"/>
  `,

  messages: `
    <path d="M21 11c0 5-5 9-10 9l-6 2 1-5
      C1 13 2 6 7 4c6-3 14 0 14 7Z"
      fill="currentColor" stroke="none"/>
  `,

  phone: `
    <path d="M7 3 4 4c-3 3 1 9 5 13s10 7 12 3
      l1-3-6-3-2 3c-3-1-6-4-7-7l3-2-3-5Z"
      fill="currentColor" stroke="none"/>
  `,

  twitter: `
    <path d="M22 5a8 8 0 0 1-2.4.7A4 4 0 0 0 21.4 3
      a8 8 0 0 1-2.6 1A4 4 0 0 0 12 7.6
      C8.6 7.4 5.6 5.8 3.6 3.3
      2.5 5.2 3 7.5 4.7 8.7
      A4 4 0 0 1 3 8.2c0 2 1.4 3.8 3.3 4.2
      a4 4 0 0 1-1.8 0c.5 1.7 2 2.9 3.8 2.9
      A8 8 0 0 1 2 17.1
      11.3 11.3 0 0 0 19.4 7.5V7
      A8 8 0 0 0 22 5Z"
      fill="currentColor" stroke="none"/>
  `,

  notes: `<path d="M3 8h18M3 12h18M3 16h18M3 20h12"/>`,

  internet: `
    <circle cx="12" cy="12" r="10"
      fill="#149cfa" stroke="none"/>
    <path d="m16.5 7.5-3 6-6 3 3-6Z"
      fill="#fff" stroke="none"/>
    <path d="m16.5 7.5-3 6-3-3Z"
      fill="#ff5d56" stroke="none"/>
  `,

  settings: `
    <circle cx="12" cy="12" r="9"/>
    <circle cx="12" cy="12" r="4"/>
    <path d="M12 1v4M12 19v4M1 12h4M19 12h4
      M4 4l3 3M17 17l3 3M4 20l3-3M17 7l3-3"/>
  `,

  edit: `
    <path d="M14 4H4v16h16V10
      M10 14l1-5 8-8 4 4-8 8-5 1Z"/>
  `,

  trash: `
    <path d="M3 6h18M9 6V3h6v3
      M5 6l1 15h12l1-15M10 10v7M14 10v7"/>
  `,

  heart: `
    <path d="M20 4c-3-2-6-1-8 2-2-3-5-4-8-2
      -5 5 1 11 8 16 7-5 13-11 8-16Z"/>
  `,

  comment: `
    <path d="M21 11a9 9 0 0 1-9 9H4
      l1-5a9 9 0 1 1 16-4Z"/>
  `,

  bookmark: `<path d="M6 3h12v19l-6-4-6 4V3Z"/>`,

  clock: `
    <circle cx="12" cy="12" r="9"/>
    <path d="M12 6v6l4 2"/>
  `,

  contacts: `
    <circle cx="12" cy="7" r="4"/>
    <path d="M4 22v-3a8 8 0 0 1 16 0v3"/>
  `,

  keypad: `
    <path d="M5 4h.1M12 4h.1M19 4h.1
      M5 11h.1M12 11h.1M19 11h.1
      M5 18h.1M12 18h.1M19 18h.1"
      stroke-width="4"/>
  `,

  delete: `
    <path d="M8 5h14v14H8l-7-7 7-7Z
      M12 9l6 6m0-6-6 6"/>
  `,

  refresh: `<path d="M20 8a9 9 0 1 0 1 7M20 2v6h-6"/>`,

  news: `
    <rect x="3" y="3" width="18" height="18" rx="2"/>
    <path d="M7 7h10M7 11h4M7 15h4M14 11h3v6h-3Z"/>
  `,

  camera: `
    <path d="M3 6h5l2-3h4l2 3h5v15H3Z"
      fill="currentColor" stroke="none"/>
    <circle cx="12" cy="13" r="4"
      fill="none" stroke="#888" stroke-width="2"/>
  `,

  torch: `
    <path d="M7 2h10v3H7ZM7 7h10l-3 5v9h-4v-9Z"
      fill="currentColor" stroke="none"/>
    <path d="M12 13v3" stroke="#888"/>
  `,

  mute: `
    <path d="M5 10v6l-2 2h15M8 6a5 5 0 0 1 9 3v5
      M10 21h4M2 2l20 20"/>
  `,

  music: `
    <path d="M2 13v6M5 10v11M8 7v14M11 5v16"/>
    <path d="M14 21V6a7 7 0 0 1 10 5
      5 5 0 0 1 0 10Z"
      fill="currentColor" stroke="none"/>
  `,

  device: `
    <rect x="6" y="2" width="12" height="20" rx="3"/>
    <path d="M10 4h4M10 19h4"/>
  `,

  home: `<path d="m2 11 10-9 10 9M5 9v13h14V9M9 22v-8h6v8"/>`
};

function icon(name, className = "") {
  if (name === "photos") {
    const colors = [
      "#ff6869", "#ffae4b", "#f7da53", "#92cb5d",
      "#56bfc4", "#688de5", "#a078d0", "#e680b4"
    ];

    return `<svg class="${className}" viewBox="0 0 24 24"
      aria-hidden="true">
      ${colors.map((color, i) => `
        <ellipse cx="12" cy="6.7" rx="3.1" ry="5.2"
          fill="${color}" fill-opacity=".85"
          transform="rotate(${i * 45} 12 12)"/>
      `).join("")}
    </svg>`;
  }

  return `<svg class="${className}" viewBox="0 0 24 24"
    fill="none" stroke="currentColor" stroke-width="1.8"
    stroke-linecap="round" stroke-linejoin="round"
    aria-hidden="true">${SHAPES[name] || SHAPES.news}</svg>`;
}

const STORAGE_KEY = "prison-iphone-final-1";
const clone = value => JSON.parse(JSON.stringify(value));

function initialState() {
  return {
    chats: clone(CONFIG.chats),
    notes: clone(CONFIG.notes),
    posts: clone(CONFIG.posts),
    unread: {},
    likes: [],
    bookmarks: [],
    calls: [],
    completedEvents: [],
    liveClock: CONFIG.liveClock
  };
}

let state = initialState();

try {
  const saved = JSON.parse(localStorage.getItem(STORAGE_KEY) || "null");

  if (saved && Array.isArray(saved.notes) && Array.isArray(saved.posts)) {
    state = { ...state, ...saved };
  }
} catch {}

let storageWarned = false;

function save() {
  try {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(state));
  } catch {
    if (!storageWarned) {
      storageWarned = true;
      toast("이 브라우저에서는 변경 내용이 저장되지 않을 수 있어.");
    }
  }
}

let view = { app: "lock" };
let started = false;
let eventTimers = [];
let replyTimers = [];
let pendingCalls = [];
let activeCall = null;
let callAudio = null;
let callFocus = null;
let flash = false;
let dial = "";
let notificationTarget = null;
let notificationTimer;
let toastTimer;
let dialogCallback = null;
let dialogFocus = null;

let browserHistory = [
  {
    page: "list",
    category: "연예",
    section: "뉴스",
    query: ""
  }
];

let browserIndex = 0;

const APPS = [
  { id: "messages", name: "메시지" },
  { id: "twitter", name: "트위터" },
  { id: "notes", name: "메모" },
  { id: "internet", name: "인터넷" },
  { id: "phone", name: "전화" },
  { id: "photos", name: "사진" },
  { id: "settings", name: "설정" }
];

function uid(prefix) {
  return prefix + "-" + Date.now() + "-" +
    Math.random().toString(36).slice(2, 7);
}

function contact(id) {
  return CONFIG.contacts.find(c => c.id === id) || {
    id,
    name: id,
    emoji: "👤",
    number: id,
    callLines: []
  };
}

function avatar(person) {
  return `<span class="avatar">${esc(person.emoji || "👤")}</span>`;
}

function nowTime() {
  return new Date().toLocaleTimeString("ko-KR", {
    hour: "2-digit",
    minute: "2-digit",
    hour12: false
  });
}

function getChat(id) {
  if (!Array.isArray(state.chats[id])) {
    state.chats[id] = [];
  }
  return state.chats[id];
}

function fit() {
  const mobile = innerWidth <= 450;
  const margin = mobile ? 0 : 40;

  const scale = Math.max(.1, Math.min(
    (innerWidth - margin) / 390,
    (innerHeight - margin) / 844
  ));

  $("stage").style.width = 390 * scale + "px";
  $("stage").style.height = 844 * scale + "px";
  $("stage").style.marginTop =
    Math.max(0, (innerHeight - 844 * scale) / 2) + "px";

  $("phone").style.transform = `scale(${scale})`;
}

addEventListener("resize", fit);
fit();

$("phone").style.setProperty("--lock-color", CONFIG.lockColor);
$("carrier").textContent = CONFIG.carrier;

const battery = Math.max(0, Math.min(100, Number(CONFIG.battery) || 0));

$("batteryNumber").textContent = battery;
$("batteryFill").style.width = battery + "%";
$("batteryIcon").setAttribute("aria-label", `배터리 ${battery}퍼센트`);

if (CONFIG.wallpaper) {
  $("wallpaper").style.backgroundImage =
    `url(${JSON.stringify(safeURL(CONFIG.wallpaper))})`;
}

function clockParts() {
  if (!state.liveClock) {
    return { time: CONFIG.time, date: CONFIG.date };
  }

  const d = new Date();

  return {
    time: d.toLocaleTimeString("en-US", {
      hour: "numeric",
      minute: "2-digit",
      hour12: true
    }).replace(/\s?(AM|PM)/, ""),

    date: `${d.getDate()}일 (${"일월화수목금토"[d.getDay()]})`
  };
}

function updateClock() {
  const c = clockParts();

  if ($("lockTime")) $("lockTime").textContent = c.time;
  if ($("lockDate")) $("lockDate").textContent = c.date;
}

setInterval(updateClock, 1000);

function updateChrome() {
  const light = ["home", "lock"].includes(view.app);
  const dark = view.app === "internet";

  $("phone").style.setProperty(
    "--status-color",
    light ? CONFIG.statusColor : dark ? "#fff" : "#111"
  );

  $("phone").style.setProperty(
    "--bar-color",
    light ? CONFIG.lockColor : dark ? "#fff" : "#111"
  );

  $("phone").style.setProperty(
    "--battery-empty",
    light ? "#ffffff55" : dark ? "#777" : "#aaa"
  );

  $("phone").style.setProperty(
    "--battery-number",
    light ? "#b9adb9" : dark ? "#777" : "#aaa"
  );

  $("homebar").setAttribute(
    "aria-label",
    view.app === "lock" ? "잠금 해제" : "홈 화면"
  );
}

function go(app, extra = {}) {
  if (activeCall) return;

  view = { app, ...extra };
  render();
}

function appbar(title, backAction = "home", right = "") {
  return `
    <header class="appbar">
      <button data-action="${backAction}" aria-label="뒤로">
        ${icon("back")}${backAction === "home" ? "홈" : "뒤로"}
      </button>
      <h1>${esc(title)}</h1>
      ${right}
    </header>
  `;
}

function render() {
  updateChrome();

  const screens = {
    lock: renderLock,
    home: renderHome,
    messages: renderMessages,
    notes: renderNotes,
    twitter: renderTwitter,
    phone: renderPhone,
    internet: renderInternet,
    photos: renderPhotos,
    settings: renderSettings
  };

  $("main").innerHTML = screens[view.app]();

  if (view.app === "lock") updateClock();

  if (view.app === "messages" && view.id) {
    scrollChat();
  }
}

/* 잠금화면 */

function renderLock() {
  const ids = Object.keys(state.unread)
    .filter(id => state.unread[id] > 0);

  const latest = ids.at(-1);
  const message = latest ? getChat(latest).at(-1) : null;

  return `
    <section class="lock" id="lockScreen">

      ${icon("lock", "lock-symbol")}

      <div class="lock-date">
        <span id="lockDate"></span>
        ${icon("mute")}
      </div>

      <div class="lock-clock" id="lockTime"></div>

      <div class="lock-widgets">
        <button class="music-widget" data-action="music"
          aria-label="음악 위젯">
          <span class="music-disc">${icon("music")}</span>
          <span class="music-copy">
            <strong>${esc(CONFIG.musicTitle)}</strong>
            <span>${esc(CONFIG.musicArtist)}</span>
          </span>
        </button>

        <div class="battery-widget">
          <div class="battery-widget-top">
            ${icon("device")}
            <strong>${battery}%</strong>
          </div>
          <span>iPhone</span>
          <div class="battery-track">
            <div style="width:${battery}%"></div>
          </div>
        </div>
      </div>

      <div class="lock-notifications">
        ${latest ? `
          <button class="lock-notification"
            data-action="open-chat" data-id="${esc(latest)}">
            <small>메시지 · 지금</small>
            <strong>${esc(contact(latest).name)}</strong>
            <p>${esc(message?.text || "새 메시지")}</p>
          </button>
        ` : ""}
      </div>

      <div class="lock-shortcuts">
        <button class="lock-shortcut ${flash ? "active" : ""}"
          data-action="flash"
          aria-label="손전등 효과"
          aria-pressed="${flash}">
          ${icon("torch")}
        </button>

        <button class="lock-shortcut"
          data-action="lock-camera" aria-label="사진 열기">
          ${icon("camera")}
        </button>
      </div>

      <div class="unlock-hint">
        위로 쓸어올리거나 하단 막대를 눌러 잠금 해제
      </div>

    </section>
  `;
}

/* 홈 화면 */

function appButton(app, dock = false) {
  const unread = Object.values(state.unread)
    .reduce((sum, n) => sum + n, 0);

  return `
    <button class="app-button"
      data-action="app" data-app="${app.id}"
      aria-label="${app.name}">

      <span class="app-tile ${app.id}">
        ${icon(app.id)}
        ${app.id === "messages" && unread ? `
          <span class="badge">${unread}</span>
        ` : ""}
      </span>

      ${dock ? "" : `<span>${app.name}</span>`}
    </button>
  `;
}

function renderHome() {
  const note = state.notes[0];
  const c = clockParts();

  return `
    <section class="home">
      <div class="home-widgets">

        <div class="home-widget">
          <small>${esc(CONFIG.owner)}의 iPhone</small>
          <h2>${esc(c.time)}</h2>
          <p>${esc(c.date)}<br>오늘도 좋은 하루.</p>
        </div>

        <button class="home-widget note-widget"
          data-action="app" data-app="notes">
          <small>메모</small>
          <h2>${esc(note?.title || "새로운 메모")}</h2>
          <p>${esc((note?.body || "생각을 기록해 봐.").slice(0, 45))}</p>
        </button>

      </div>

      <div class="apps">
        ${APPS.map(app => appButton(app)).join("")}
      </div>

      <button class="home-lock" data-action="lock">잠금</button>

      <div class="dock">
        ${["phone", "internet", "messages", "twitter"]
          .map(id => appButton(APPS.find(a => a.id === id), true))
          .join("")}
      </div>
    </section>
  `;
}

/* 메시지 */

function openChat(id) {
  startExperience();
  state.unread[id] = 0;
  save();

  $("notification").hidden = true;
  go("messages", { id });
}

function messageRows(query = "") {
  const q = query.toLowerCase();

  const matches = CONFIG.contacts.filter(c => {
    const all = c.name + " " +
      getChat(c.id).map(m => m.text).join(" ");

    return all.toLowerCase().includes(q);
  });

  return matches.map(c => {
    const last = getChat(c.id).at(-1);

    return `
      <button class="list-row"
        data-action="open-chat" data-id="${esc(c.id)}">

        ${state.unread[c.id] ? '<span class="unread-dot"></span>' : ""}

        ${avatar(c)}

        <div class="row-copy">
          <div class="row-title">
            ${esc(c.name)}
            <span class="tiny">${esc(last?.time || "")}</span>
          </div>
          <div class="row-preview">
            ${esc(last?.text || "대화 없음")}
          </div>
        </div>

        <span style="color:#bbb">›</span>
      </button>
    `;
  }).join("") || '<div class="empty">검색 결과가 없어.</div>';
}

function bubbleHTML(message) {
  return `
    <div class="bubble-wrap ${message.me ? "me" : ""}">
      <div class="bubble">${esc(message.text)}</div>
      <span class="bubble-time">${esc(message.time || "")}</span>
    </div>
  `;
}

function renderMessages() {
  if (view.id) {
    const c = contact(view.id);

    return `
      <section class="app">
        ${appbar(c.name, "message-list", `
          <button data-action="call-contact"
            data-id="${esc(c.id)}" aria-label="전화 걸기">
            ${icon("phone")}
          </button>
        `)}

        <div class="scroll chat-content" id="chatContent">
          <div class="chat-day">메시지</div>
          ${getChat(view.id).map(bubbleHTML).join("")}
        </div>

        <form class="composer" id="messageForm">
          <input name="message" id="messageInput"
            placeholder="iMessage" aria-label="메시지 입력"
            autocomplete="off">
          <button class="send" aria-label="전송">↑</button>
        </form>
      </section>
    `;
  }

  return `
    <section class="app">
      ${appbar("메시지")}
      <h2 class="large-title">메시지</h2>

      <div class="search-wrap">
        <input class="search" data-search="messages"
          placeholder="검색" aria-label="문자 검색">
      </div>

      <div class="scroll" id="messageRows">
        ${messageRows()}
      </div>
    </section>
  `;
}

function scrollChat() {
  const box = $("chatContent");
  if (box) box.scrollTop = box.scrollHeight;
}

function sendMessage(text) {
  text = text.trim();
  if (!text || !view.id) return;

  const id = view.id;

  getChat(id).push({
    me: true,
    text,
    time: nowTime()
  });

  save();
  render();
  $("messageInput")?.focus();

  const reply = CONFIG.autoReplies[id];

  if (reply) {
    replyTimers.push(setTimeout(() => {
      receiveMessage(id, reply);
    }, 1900));
  }
}

function receiveMessage(id, text) {
  const message = {
    me: false,
    text,
    time: nowTime()
  };

  getChat(id).push(message);

  const reading =
    view.app === "messages" &&
    view.id === id &&
    !activeCall;

  if (!reading) {
    state.unread[id] = (state.unread[id] || 0) + 1;
  }

  save();

  if (reading) {
    const box = $("chatContent");
    const nearBottom =
      box.scrollHeight - box.scrollTop - box.clientHeight < 80;

    box.insertAdjacentHTML("beforeend", bubbleHTML(message));

    if (nearBottom) scrollChat();
    return;
  }

  showNotification(id, text);

  if (["lock", "home"].includes(view.app)) {
    render();
  } else if (view.app === "messages" && !view.id) {
    const query =
      document.querySelector('[data-search="messages"]')?.value || "";

    $("messageRows").innerHTML = messageRows(query);
  }
}

function showNotification(id, text) {
  notificationTarget = id;

  $("notification").innerHTML = `
    <small>메시지 · 지금</small>
    <strong>${esc(contact(id).name)}</strong>
    <span>${esc(text)}</span>
  `;

  $("notification").hidden = false;
  clearTimeout(notificationTimer);

  notificationTimer = setTimeout(() => {
    $("notification").hidden = true;
  }, 6500);
}

$("notification").onclick = () => {
  if (!activeCall) openChat(notificationTarget);
};

/* 메모 */

function noteRows(query = "") {
  const q = query.toLowerCase();

  return state.notes
    .filter(n => (n.title + " " + n.body).toLowerCase().includes(q))
    .map(n => `
      <button class="note-row"
        data-action="open-note" data-id="${esc(n.id)}">
        <strong>${esc(n.title || "새 메모")}</strong>
        <span>${esc(n.body.split("\n").find(Boolean) || "내용 없음")}</span>
      </button>
    `).join("") || `
      <div class="empty">
        메모가 없어.<br>오른쪽 위 버튼으로 작성해 봐.
      </div>
    `;
}

function renderNotes() {
  if (view.id) {
    const n = state.notes.find(n => n.id === view.id);

    if (!n) {
      view = { app: "notes" };
      return renderNotes();
    }

    return `
      <section class="app notes-app">
        ${appbar("메모", "note-list", `
          <button class="danger" data-action="delete-note"
            data-id="${esc(n.id)}" aria-label="메모 삭제">
            ${icon("trash")}
          </button>
        `)}

        <div class="note-editor">
          <input id="noteTitle" value="${esc(n.title)}"
            placeholder="제목" aria-label="메모 제목">

          <textarea id="noteBody" placeholder="내용을 입력해"
            aria-label="메모 내용">${esc(n.body)}</textarea>
        </div>

        <div class="save-state">자동 저장됨</div>
      </section>
    `;
  }

  return `
    <section class="app notes-app">
      ${appbar("메모", "home", `
        <button data-action="new-note" aria-label="새 메모">
          ${icon("edit")}
        </button>
      `)}

      <h2 class="large-title">메모</h2>

      <div class="search-wrap">
        <input class="search" data-search="notes"
          placeholder="검색" aria-label="메모 검색">
      </div>

      <div class="scroll">
        <div class="note-list" id="noteRows">${noteRows()}</div>
      </div>

      <div class="save-state">
        ${state.notes.length}개의 메모 · 이 브라우저에 저장됨
      </div>
    </section>
  `;
}

function persistNote() {
  const n = state.notes.find(n => n.id === view.id);
  if (!n) return;

  n.title = $("noteTitle").value;
  n.body = $("noteBody").value;
  save();
}

/* 트위터 */

function postHTML(post) {
  const liked = state.likes.includes(post.id);
  const saved = state.bookmarks.includes(post.id);

  return `
    <article class="post">
      <div class="post-head">
        ${avatar(post)}
        <div>
          <strong>${esc(post.name)}</strong>
          <div class="handle">
            ${esc(post.handle)} · ${esc(post.time)}
          </div>
        </div>
      </div>

      <p class="post-text">${esc(post.text)}</p>

      ${post.image ? img(post.image, "post-image", "게시물 사진") : ""}

      <div class="post-actions">
        <button data-action="open-post"
          data-id="${esc(post.id)}" aria-label="답글 보기">
          ${icon("comment")}${post.comments?.length || 0}
        </button>

        <button class="${liked ? "liked" : ""}"
          data-action="like" data-id="${esc(post.id)}"
          aria-label="좋아요" aria-pressed="${liked}">
          ${icon("heart")}${post.likes + (liked ? 1 : 0)}
        </button>

        <button class="${saved ? "saved" : ""}"
          data-action="bookmark" data-id="${esc(post.id)}"
          aria-label="북마크" aria-pressed="${saved}">
          ${icon("bookmark")}
        </button>
      </div>
    </article>
  `;
}

function postRows(query = "") {
  const q = query.toLowerCase();

  return state.posts
    .filter(p => {
      const tabMatches =
        view.tab !== "saved" || state.bookmarks.includes(p.id);

      const queryMatches =
        (p.name + " " + p.text).toLowerCase().includes(q);

      return tabMatches && queryMatches;
    })
    .map(postHTML)
    .join("") || '<div class="empty">표시할 게시물이 없어.</div>';
}

function renderTwitter() {
  if (view.post) {
    const p = state.posts.find(p => p.id === view.post);

    if (!p) {
      view = { app: "twitter" };
      return renderTwitter();
    }

    return `
      <section class="app">
        ${appbar("게시물", "twitter-list")}

        <div class="scroll">
          ${postHTML(p)}

          ${(p.comments || []).map(c => `
            <div class="post">
              <strong style="font-size:13px">${esc(c.name)}</strong>
              <p class="post-text">${esc(c.text)}</p>
            </div>
          `).join("")}
        </div>

        <form class="composer" id="commentForm">
          <input name="comment" placeholder="답글 작성"
            aria-label="답글 입력">
          <button class="send" aria-label="답글 전송">↑</button>
        </form>
      </section>
    `;
  }

  const tab = view.tab || "all";

  return `
    <section class="app">
      ${appbar("트위터", "home", `
        <button data-action="compose-post" aria-label="게시물 쓰기">
          ${icon("edit")}
        </button>
      `)}

      <div class="social-tabs">
        <button class="${tab === "all" ? "selected" : ""}"
          data-action="social-tab" data-tab="all">타임라인</button>

        <button class="${tab === "saved" ? "selected" : ""}"
          data-action="social-tab" data-tab="saved">북마크</button>
      </div>

      ${view.compose ? `
        <form class="tweet-form" id="tweetForm">
          <textarea name="post" placeholder="무슨 일이 일어나고 있나요?"
            aria-label="게시물 내용" maxlength="1000"></textarea>
          <button class="primary">게시하기</button>
        </form>
      ` : ""}

      <div class="search-wrap" style="padding-top:12px">
        <input class="search" data-search="posts"
          placeholder="게시물 검색" aria-label="게시물 검색">
      </div>

      <div class="scroll" id="postRows">${postRows()}</div>
    </section>
  `;
}

/* 전화 앱 */

function contactRows(query = "") {
  return CONFIG.contacts
    .filter(c => (c.name + c.number).includes(query))
    .map(c => `
      <button class="list-row"
        data-action="call-contact" data-id="${esc(c.id)}">
        ${avatar(c)}
        <div class="row-copy">
          <div class="row-title">${esc(c.name)}</div>
          <div class="row-preview">${esc(c.number)}</div>
        </div>
        ${icon("phone")}
      </button>
    `).join("") || '<div class="empty">연락처가 없어.</div>';
}

function renderPhone() {
  const tab = view.tab || "contacts";
  let body = "";

  if (tab === "keypad") {
    const keys = ["1", "2", "3", "4", "5", "6", "7", "8", "9", "*", "0", "#"];
    const letters = [
      "", "ABC", "DEF", "GHI", "JKL", "MNO",
      "PQRS", "TUV", "WXYZ", "", "+", ""
    ];

    body = `
      <div class="keypad-number" id="dialNumber">${esc(dial)}</div>

      <div class="keypad">
        ${keys.map((key, i) => `
          <button class="key" data-action="dial-key" data-key="${key}">
            ${key}<small>${letters[i] || "&nbsp;"}</small>
          </button>
        `).join("")}
      </div>

      <div class="dial-actions">
        <button class="dial-call"
          data-action="dial-call" aria-label="전화 걸기">
          ${icon("phone")}
        </button>

        <button class="dial-delete"
          data-action="dial-delete" aria-label="번호 지우기">
          ${icon("delete")}
        </button>
      </div>
    `;
  } else if (tab === "recents") {
    body = `
      <h2 class="large-title">최근 통화</h2>

      ${state.calls.map(c => `
        <button class="list-row"
          data-action="call-contact" data-id="${esc(c.id)}">
          ${avatar(contact(c.id))}
          <div class="row-copy">
            <div class="row-title"
              style="${c.missed ? "color:#ff453a" : ""}">
              ${esc(contact(c.id).name)}
            </div>
            <div class="row-preview">
              ${c.missed ? "부재중 전화" : c.incoming ? "수신 통화" : "발신 통화"}
            </div>
          </div>
          <span class="tiny">${esc(c.time)}</span>
        </button>
      `).join("") || '<div class="empty">최근 통화가 없어.</div>'}
    `;
  } else {
    body = `
      <h2 class="large-title">연락처</h2>

      <div class="search-wrap">
        <input class="search" data-search="contacts"
          placeholder="검색" aria-label="연락처 검색">
      </div>

      <div id="contactRows">${contactRows()}</div>
    `;
  }

  return `
    <section class="app">
      ${appbar("전화")}
      <div class="scroll">${body}</div>

      <nav class="tabbar">
        ${[
          ["recents", "clock", "최근 통화"],
          ["contacts", "contacts", "연락처"],
          ["keypad", "keypad", "키패드"]
        ].map(([id, image, label]) => `
          <button class="${tab === id ? "selected" : ""}"
            data-action="phone-tab" data-tab="${id}">
            ${icon(image)}${label}
          </button>
        `).join("")}
      </nav>
    </section>
  `;
}

/* 인터넷 앱 */

function browserPage() {
  return browserHistory[browserIndex];
}

function browserPush(page) {
  browserHistory = browserHistory.slice(0, browserIndex + 1);
  browserHistory.push(page);
  browserIndex++;
  render();
}

function newsRows(page) {
  const q = (page.query || "").toLowerCase();

  return CONFIG.news
    .filter(n => {
      const categoryMatches = n.category === page.category;
      const sectionMatches =
        page.section === "홈" || n.section === page.section;
      const searchMatches =
        (n.title + " " + n.body + " " + n.source)
          .toLowerCase().includes(q);

      return categoryMatches && sectionMatches && searchMatches;
    })
    .map(n => `
      <button class="news-row"
        data-action="article" data-id="${esc(n.id)}">

        <div class="news-copy">
          <div class="news-title">${esc(n.title)}</div>
          <div class="news-meta">
            ${esc(n.source)} · ${esc(n.time)}
          </div>
        </div>

        ${n.image
          ? img(n.image, "news-thumb", n.title)
          : `
            <span class="news-thumb news-placeholder">
              ${icon("news")}
              <span>${esc(n.source)}</span>
            </span>
          `}
      </button>
    `).join("") || `
      <div class="empty">
        표시할 기사가 없어.<br>
        CONFIG.news에 이 분류의 기사를 추가해 줘.
      </div>
    `;
}

function newsList(page) {
  return `
    <header class="portal-head">
      <span class="portal-logo">D</span>
      <strong>${esc(page.category)}</strong>

      <div class="portal-cats">
        ${["연예", "뉴스", "스포츠", "날씨"]
          .filter(category => category !== page.category)
          .map(category => `
            <button data-action="news-category"
              data-category="${category}">${category}</button>
          `).join("")}
      </div>
    </header>

    <nav class="portal-nav">
      ${["홈", "뉴스", "연재", "포토", "월간다음"]
        .map(section => `
          <button class="${page.section === section ? "selected" : ""}"
            data-action="news-section"
            data-section="${section}">${section}</button>
        `).join("")}
    </nav>

    <div class="news-search">
      <input class="search" data-search="news"
        placeholder="뉴스 검색" aria-label="뉴스 검색"
        value="${esc(page.query || "")}">
    </div>

    <h2 class="news-heading">
      ${page.section === "뉴스"
        ? "최신 뉴스"
        : page.section === "홈"
          ? "주요 뉴스"
          : esc(page.section)}
    </h2>

    <div id="newsRows">${newsRows(page)}</div>
  `;
}

function articleHTML(article) {
  return `
    <article class="article">
      <button class="article-back" data-action="browser-back">
        ${icon("back")}목록으로
      </button>

      <div class="article-label">
        ${esc(article.category)} · ${esc(article.source)}
      </div>

      <h2>${esc(article.title)}</h2>

      <div class="article-meta">
        ${esc(article.source)} · ${esc(article.time)}
      </div>

      ${article.image ? img(article.image, "", article.title) : ""}

      <div class="article-body">${esc(article.body)}</div>
    </article>
  `;
}

function renderInternet() {
  const page = browserPage();

  const article = CONFIG.news.find(n => n.id === page.id);
  const articleOpen = page.page === "article" && article;

  return `
    <section class="app dark">

      <div class="browser-address">
        ${icon("lock")}
        <span>
          ${articleOpen
            ? "news.prison.local/article/" + esc(page.id)
            : "news.prison.local"}
        </span>

        <button data-action="browser-refresh" aria-label="새로고침">
          ${icon("refresh")}
        </button>
      </div>

      <div class="scroll">
        ${articleOpen ? articleHTML(article) : newsList(page)}
      </div>

      <nav class="browser-bottom">
        <button data-action="browser-back"
          aria-label="이전 페이지"
          ${browserIndex === 0 ? "disabled" : ""}>
          ${icon("back")}
        </button>

        <button data-action="browser-forward"
          aria-label="다음 페이지"
          ${browserIndex === browserHistory.length - 1 ? "disabled" : ""}>
          ${icon("forward")}
        </button>

        <button data-action="browser-start" aria-label="뉴스 첫 화면">
          ${icon("home")}
        </button>

        <button data-action="home" aria-label="휴대폰 홈">
          ${icon("internet")}
        </button>
      </nav>

    </section>
  `;
}

/* 사진 앱 */

function renderPhotos() {
  const selected = view.index !== undefined
    ? CONFIG.photos[view.index] : null;

  return `
    <section class="app">
      ${appbar(
        selected ? selected.caption || "사진" : "사진",
        selected ? "photo-list" : "home"
      )}

      <div class="scroll">
        ${selected
          ? img(selected.image, "photo-view", selected.caption)
          : CONFIG.photos.length
            ? `
              <div class="photos-grid">
                ${CONFIG.photos.map((p, index) => `
                  <button class="photo" data-action="open-photo"
                    data-index="${index}">
                    ${img(p.image, "", p.caption)}
                  </button>
                `).join("")}
              </div>
            `
            : `
              <div class="empty">
                아직 사진이 없어.<br>
                CONFIG.photos에 사진 파일 이름을 추가해 줘.
              </div>
            `}
      </div>
    </section>
  `;
}

/* 설정 */

function renderSettings() {
  return `
    <section class="app settings-app">
      ${appbar("설정")}

      <div class="scroll">
        <h2 class="large-title">설정</h2>

        <div class="settings-group">

          <label class="setting-row">
            실제 현재 시간 표시
            <input type="checkbox" id="clockToggle"
              ${state.liveClock ? "checked" : ""}>
          </label>

          <button class="setting-row" data-action="replay-events">
            자동 문자·전화 다시 재생
            <span>›</span>
          </button>

          <button class="setting-row danger" data-action="reset">
            데이터 초기화
            <span>›</span>
          </button>

        </div>

        <p class="setting-help">
          문자, 메모, 게시물과 통화 기록은 이 브라우저에 저장돼.
          다른 방문자와 공유되지는 않아.
          <br><br>
          CONFIG에서 초기 문자·메모·게시물을 바꿨다면
          데이터 초기화를 눌러 새 내용을 적용해 줘.
          <br><br>
          전화와 인터넷은 사이트 안에서 작동하는 가상 화면이야.
          뉴스 내용은 CONFIG.news에서 직접 작성하면 돼.
        </p>
      </div>
    </section>
  `;
}

/* 자동 이벤트 */

function startExperience() {
  if (started) return;
  started = true;

  CONFIG.events.forEach((event, index) => {
    if (state.completedEvents.includes(index)) return;

    const timer = setTimeout(() => {
      state.completedEvents.push(index);
      save();

      if (event.type === "message") {
        receiveMessage(event.contact, event.text);
      }

      if (event.type === "call") {
        if (activeCall || !$("dialog").hidden) {
          pendingCalls.push(event.contact);
        } else {
          startCall(event.contact, true);
        }
      }
    }, Math.max(0, event.after) * 1000);

    eventTimers.push(timer);
  });
}

function unlock() {
  startExperience();
  go("home");
}

$("homebar").onclick = () => {
  if (activeCall || !$("dialog").hidden) return;

  if (view.app === "lock") unlock();
  else go("home");
};

let swipeStart = null;

$("main").addEventListener("pointerdown", event => {
  if (view.app === "lock" && !event.target.closest("button")) {
    swipeStart = {
      x: event.clientX,
      y: event.clientY
    };
  }
});

$("main").addEventListener("pointerup", event => {
  if (
    swipeStart &&
    view.app === "lock" &&
    swipeStart.y - event.clientY > 45 &&
    Math.abs(swipeStart.x - event.clientX) < 100
  ) {
    unlock();
  }

  swipeStart = null;
});

$("main").addEventListener("pointercancel", () => {
  swipeStart = null;
});

/* 통화 */

function blockUnderlay(block) {
  $("main").inert = block;
  $("homebar").inert = block;
  $("notification").inert = block;
}

function startCall(id, incoming) {
  if (activeCall) return;

  if (!$("dialog").hidden) {
    if (incoming) pendingCalls.push(id);
    return;
  }

  const c = contact(id);

  activeCall = {
    id,
    incoming,
    connected: false,
    logged: false,
    seconds: 0,
    timers: [],
    interval: null
  };

  callFocus = document.activeElement;

  $("notification").hidden = true;
  $("call").hidden = false;
  blockUnderlay(true);

  $("call").innerHTML = `
    <div class="call-avatar">${esc(c.emoji)}</div>
    <div class="call-name">${esc(c.name)}</div>
    <div class="call-state" id="callState">
      ${incoming ? "iPhone · 전화 수신 중" : "전화 거는 중…"}
    </div>

    <div class="call-script" id="callScript" aria-live="polite"></div>

    <div class="call-actions">
      <div class="call-action">
        <button class="call-reject" data-action="end-call"
          aria-label="${incoming ? "거절" : "종료"}">
          ${icon("phone")}
        </button>
        <span id="endCallLabel">${incoming ? "거절" : "종료"}</span>
      </div>

      <div class="call-action" id="answerAction"
        ${incoming ? "" : "hidden"}>
        <button class="call-answer" data-action="answer-call"
          aria-label="전화 받기">
          ${icon("phone")}
        </button>
        <span>받기</span>
      </div>
    </div>
  `;

  $("call").querySelector("button").focus();

  if (incoming) {
    activeCall.timers.push(
      setTimeout(() => endCall(true), 25000)
    );
  } else {
    activeCall.timers.push(
      setTimeout(() => {
        if (CONFIG.contacts.some(c => c.id === id)) {
          answerCall();
        } else {
          $("callState").textContent = "연결할 수 없는 번호야.";
          activeCall.timers.push(
            setTimeout(() => endCall(false), 2200)
          );
        }
      }, 1800)
    );
  }
}

function logCall(missed) {
  if (!activeCall || activeCall.logged) return;

  activeCall.logged = true;

  state.calls.unshift({
    id: activeCall.id,
    incoming: activeCall.incoming,
    missed,
    time: nowTime()
  });

  state.calls = state.calls.slice(0, 60);
  save();
}

function answerCall() {
  if (!activeCall || activeCall.connected) return;

  activeCall.timers.forEach(clearTimeout);
  activeCall.timers = [];
  activeCall.connected = true;

  logCall(false);

  $("answerAction").hidden = true;
  $("endCallLabel").textContent = "종료";
  $("callState").textContent = "00:00";

  const endButton = $("call").querySelector(".call-reject");
  endButton.setAttribute("aria-label", "통화 종료");
  endButton.focus();

  activeCall.interval = setInterval(() => {
    if (!activeCall) return;

    activeCall.seconds++;

    const minutes = String(
      Math.floor(activeCall.seconds / 60)
    ).padStart(2, "0");

    const seconds = String(
      activeCall.seconds % 60
    ).padStart(2, "0");

    $("callState").textContent = minutes + ":" + seconds;
  }, 1000);

  const c = contact(activeCall.id);

  const lines = c.callLines?.length
    ? c.callLines
    : ["CONFIG.contacts에서 통화 대사를 입력해 줘."];

  lines.forEach((line, index) => {
    activeCall.timers.push(
      setTimeout(() => {
        if (!activeCall) return;

        const paragraph = document.createElement("p");
        paragraph.textContent = line;

        $("callScript").append(paragraph);
        $("callScript").scrollTop = $("callScript").scrollHeight;
      }, 700 + index * 3500)
    );
  });

  if (c.audio) {
    callAudio = new Audio(safeURL(c.audio));

    callAudio.play().catch(() => {
      toast("음성 파일 이름을 확인해 줘. 재생하지 못했어.");
    });
  }
}

function runPendingCall() {
  if (activeCall || !$("dialog").hidden || !pendingCalls.length) return;

  const id = pendingCalls.shift();

  setTimeout(() => {
    if (activeCall || !$("dialog").hidden) {
      pendingCalls.unshift(id);
    } else {
      startCall(id, true);
    }
  }, 800);
}

function endCall(missed = false) {
  if (!activeCall) return;

  const id = activeCall.id;
  const incoming = activeCall.incoming;

  logCall(missed);

  activeCall.timers.forEach(clearTimeout);
  clearInterval(activeCall.interval);

  if (callAudio) {
    callAudio.pause();
    callAudio = null;
  }

  activeCall = null;
  $("call").hidden = true;
  blockUnderlay(false);

  if (view.app === "phone" && view.tab === "recents") {
    render();
  }

  if (callFocus?.isConnected) {
    callFocus.focus();
  }

  if (missed && incoming) {
    toast(contact(id).name + " · 부재중 전화");
  }

  runPendingCall();
}

/* 확인창과 안내 */

function toast(text) {
  $("toast").textContent = text;
  $("toast").hidden = false;

  clearTimeout(toastTimer);

  toastTimer = setTimeout(() => {
    $("toast").hidden = true;
  }, 3200);
}

function ask(title, text, callback) {
  dialogFocus = document.activeElement;
  dialogCallback = callback;

  $("dialog").innerHTML = `
    <div class="dialog-card">
      <strong id="dialogTitle">${esc(title)}</strong>
      <p>${esc(text)}</p>
      <div class="dialog-actions">
        <button data-action="cancel-dialog">취소</button>
        <button data-action="confirm-dialog" class="danger">확인</button>
      </div>
    </div>
  `;

  $("dialog").hidden = false;
  blockUnderlay(true);
  $("dialog").querySelector("button").focus();
}

function closeDialog() {
  $("dialog").hidden = true;
  dialogCallback = null;
  blockUnderlay(false);

  if (dialogFocus?.isConnected) {
    dialogFocus.focus();
  }
}

function togglePostValue(key, id) {
  const list = state[key];
  const index = list.indexOf(id);

  if (index === -1) list.push(id);
  else list.splice(index, 1);

  save();

  const scroll = document.querySelector(".scroll");
  const position = scroll?.scrollTop || 0;
  const input = document.querySelector('[data-search="posts"]');
  const query = input?.value || "";

  render();

  if ($("postRows")) {
    document.querySelector('[data-search="posts"]').value = query;
    $("postRows").innerHTML = postRows(query);
  }

  const newScroll = document.querySelector(".scroll");
  if (newScroll) newScroll.scrollTop = position;
}

/* 클릭 처리 */

document.addEventListener("click", event => {
  const button = event.target.closest("[data-action]");

  if (!button || button.disabled || button.closest("[inert]")) return;

  if (activeCall && !button.closest("#call")) return;
  if (!$("dialog").hidden && !button.closest("#dialog")) return;

  const action = button.dataset.action;
  const id = button.dataset.id;

  switch (action) {
    case "home":
      go("home");
      break;

    case "app":
      startExperience();
      go(button.dataset.app);
      break;

    case "lock":
      go("lock");
      break;

    case "flash":
      flash = !flash;
      $("flashlightGlow").hidden = !flash;
      button.classList.toggle("active", flash);
      button.setAttribute("aria-pressed", String(flash));
      break;

    case "lock-camera":
      startExperience();
      go("photos");
      break;

    case "music":
      toast(CONFIG.musicTitle + " · " + CONFIG.musicArtist);
      break;

    case "open-chat":
      openChat(id);
      break;

    case "message-list":
      go("messages");
      break;

    case "note-list":
      go("notes");
      break;

    case "open-note":
      go("notes", { id });
      break;

    case "new-note": {
      const note = {
        id: uid("note"),
        title: "",
        body: ""
      };

      state.notes.unshift(note);
      save();
      go("notes", { id: note.id });
      $("noteTitle").focus();
      break;
    }

    case "delete-note":
      ask("메모 삭제", "이 메모를 삭제할까?", () => {
        state.notes = state.notes.filter(n => n.id !== id);
        save();
        go("notes");
      });
      break;

    case "twitter-list":
      go("twitter");
      break;

    case "social-tab":
      go("twitter", { tab: button.dataset.tab });
      break;

    case "compose-post":
      go("twitter", { compose: !view.compose });
      break;

    case "open-post":
      go("twitter", { post: id });
      break;

    case "like":
      togglePostValue("likes", id);
      break;

    case "bookmark":
      togglePostValue("bookmarks", id);
      break;

    case "phone-tab":
      go("phone", { tab: button.dataset.tab });
      break;

    case "call-contact":
      startCall(id, false);
      break;

    case "dial-key":
      if (dial.length < 20) {
        dial += button.dataset.key;
      }

      $("dialNumber").textContent = dial;
      break;

    case "dial-delete":
      dial = dial.slice(0, -1);
      $("dialNumber").textContent = dial;
      break;

    case "dial-call": {
      if (!dial) {
        toast("번호를 입력해 줘.");
        break;
      }

      const c = CONFIG.contacts.find(c => c.number === dial);
      startCall(c?.id || dial, false);
      break;
    }

    case "answer-call":
      answerCall();
      break;

    case "end-call":
      endCall(false);
      break;

    case "browser-back":
      if (browserIndex > 0) {
        browserIndex--;
        render();
      }
      break;

    case "browser-forward":
      if (browserIndex < browserHistory.length - 1) {
        browserIndex++;
        render();
      }
      break;

    case "browser-start":
      browserPush({
        page: "list",
        category: "연예",
        section: "뉴스",
        query: ""
      });
      break;

    case "browser-refresh":
      render();
      toast("새로고침했어.");
      break;

    case "news-category":
      browserPush({
        page: "list",
        category: button.dataset.category,
        section: "뉴스",
        query: ""
      });
      break;

    case "news-section":
      browserPush({
        ...browserPage(),
        page: "list",
        section: button.dataset.section,
        query: ""
      });
      break;

    case "article":
      browserPush({
        page: "article",
        id
      });
      break;

    case "open-photo":
      go("photos", { index: Number(button.dataset.index) });
      break;

    case "photo-list":
      go("photos");
      break;

    case "replay-events":
      eventTimers.forEach(clearTimeout);
      eventTimers = [];
      pendingCalls = [];
      state.completedEvents = [];
      save();
      started = false;
      startExperience();
      toast("지금부터 자동 이벤트를 다시 재생해.");
      break;

    case "reset":
      ask(
        "데이터 초기화",
        "메모·문자·게시물·통화 기록을 처음 상태로 되돌릴까?",
        () => {
          eventTimers.forEach(clearTimeout);
          replyTimers.forEach(clearTimeout);

          eventTimers = [];
          replyTimers = [];
          pendingCalls = [];

          state = initialState();
          save();

          started = false;
          flash = false;

          $("flashlightGlow").hidden = true;
          $("notification").hidden = true;

          clearTimeout(notificationTimer);
          go("lock");
        }
      );
      break;

    case "cancel-dialog":
      closeDialog();
      runPendingCall();
      break;

    case "confirm-dialog": {
      const callback = dialogCallback;
      closeDialog();
      callback?.();
      runPendingCall();
      break;
    }
  }
});

/* 입력 처리 */

document.addEventListener("input", event => {
  const input = event.target;

  if (input.id === "noteTitle" || input.id === "noteBody") {
    persistNote();
  }

  switch (input.dataset.search) {
    case "messages":
      $("messageRows").innerHTML = messageRows(input.value);
      break;

    case "notes":
      $("noteRows").innerHTML = noteRows(input.value);
      break;

    case "posts":
      $("postRows").innerHTML = postRows(input.value);
      break;

    case "contacts":
      $("contactRows").innerHTML = contactRows(input.value);
      break;

    case "news":
      browserPage().query = input.value;
      $("newsRows").innerHTML = newsRows(browserPage());
      break;
  }
});

document.addEventListener("change", event => {
  if (event.target.id === "clockToggle") {
    state.liveClock = event.target.checked;
    save();
  }
});

/* 전송 처리 */

document.addEventListener("submit", event => {
  const form = event.target;
  event.preventDefault();

  if (form.id === "messageForm") {
    sendMessage(String(new FormData(form).get("message") || ""));
  }

  if (form.id === "tweetForm") {
    const text = String(
      new FormData(form).get("post") || ""
    ).trim();

    if (!text) return;

    state.posts.unshift({
      id: uid("post"),
      ...CONFIG.profile,
      time: "지금",
      text,
      image: "",
      likes: 0,
      comments: []
    });

    save();
    go("twitter");
  }

  if (form.id === "commentForm") {
    const text = String(
      new FormData(form).get("comment") || ""
    ).trim();

    if (!text) return;

    const post = state.posts.find(p => p.id === view.post);
    if (!post) return;

    post.comments = post.comments || [];

    post.comments.push({
      name: CONFIG.profile.name,
      text
    });

    save();
    render();
  }
});

/* 확인창과 전화 화면 키보드 이동 */

document.addEventListener("keydown", event => {
  const modal = !$("dialog").hidden
    ? $("dialog")
    : !$("call").hidden
      ? $("call")
      : null;

  if (!modal) return;

  if (event.key === "Escape" && modal.id === "dialog") {
    closeDialog();
    runPendingCall();
    return;
  }

  if (event.key !== "Tab") return;

  const buttons = [...modal.querySelectorAll("button")]
    .filter(button => button.getClientRects().length > 0);

  const first = buttons[0];
  const last = buttons.at(-1);

  if (event.shiftKey && document.activeElement === first) {
    event.preventDefault();
    last.focus();
  } else if (!event.shiftKey && document.activeElement === last) {
    event.preventDefault();
    first.focus();
  }
});

/* 잘못된 이미지 파일은 깨진 아이콘 대신 숨기기 */

document.addEventListener("error", event => {
  if (event.target.tagName === "IMG") {
    event.target.style.visibility = "hidden";
    event.target.parentElement.setAttribute(
      "aria-label",
      "이미지 파일 이름을 확인해 주세요"
    );
  }
}, true);

render();
</script>
</body>
</html>
