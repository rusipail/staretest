<script lang="ts">
  let blind: boolean = false;
  const menuBarOverCheck = () => {
    blind = true;
  };
  const menuBarOutCheck = () => {
    blind = false;
  };
</script>

<main id="mainContainer">
  <div id="menuBar">
    <span id="logo">
      <a href="/main">STARE</a>
    </span>
    <div id="searchingBar">
      <input type="search" id="search" autocomplete="off" />
      <span class="readingGlass"> 돋보기 svg </span>
    </div>
    <div id="signContainer">
      <span id="signIn">
        <a href="sign_in">sign in</a>
      </span>
      <span id="signUp">
        <a href="sign_up">sign up</a>
      </span>
    </div>
  </div>
  <div
    id="subMenuBar"
    on:focus
    on:mouseover={menuBarOverCheck}
    on:mouseleave={menuBarOutCheck}
  >
    <div>Introduction</div>
    <div>Leture</div>
    <div>Mini Game</div>
    <div>Issue</div>
    <div>CTF</div>
    <div>Notice</div>
  </div>
  <div
    id="openMenuBar"
    class={blind ? " " : "blind"}
    on:focus
    on:mouseover={menuBarOverCheck}
    on:mouseleave={menuBarOutCheck}
  >
    <div class="introduction">
      <div class="subOptions">동아리 소개</div>
      <div class="subOptions">사이트 소개</div>
    </div>
    <div class="lenture">
      <div class="subOptions">수업</div>
      <div class="subOptions">용어정리</div>
      <div class="subOptions">각 분야 공부 사이트</div>
    </div>
    <div class="miniGame">
      <div class="subOptions">Hack the Dimi(쉬운 미니게임)</div>
    </div>
    <div class="issue">
      <div class="subOptions">보안이슈 정리</div>
    </div>
    <div class="CTF">
      <div class="subOptions">CTF 대회 정리</div>
    </div>
    <div class="notice">
      <div class="subOptions">공지 Q&A</div>
    </div>
  </div>
  <div id="centerLogo">STARE</div>
</main>

<style>
  a {
    text-decoration: none;
    color: black;
  }
  main {
    overflow-x: hidden;
    height: 200vh;
    margin-top: 120px;
    z-index: 3;
  }
  #menuBar {
    width: calc(100% - 15px);
    border: 1px solid black;
    margin: 0px;
    display: flex;
    position: fixed;
    top: 0px;
    border-collapse: collapse;
    justify-content: space-between;
    background-color: white;
    z-index: 3;
  }
  #subMenuBar {
    width: calc(100% - 25px);
    border: 1px solid black;
    margin: 0px;
    display: flex;
    position: fixed;
    top: 55px;
    justify-content: space-between;
    border-collapse: collapse;
    padding: 5px;
    background-color: white;
    z-index: 3;
  }
  #subMenuBar > div {
    padding: 10px 30px;
  }
  #openMenuBar {
    width: calc(100% - 15px);
    position: fixed;
    display: flex;
    justify-content: space-between;
    top: 108px;
    border: 1px solid black;
    z-index: 2;
    background-color: white;
    transition: all 0.3s;
  }
  .subOptions {
    padding: 20px 30px;
    z-index: 2;
  }
  #mainContainer > .blind {
    transform: translateY(-200px);
    transition: all 0.3s;
  }
  #centerLogo {
    font-size: 400px;
    font-weight: bolder;
    z-index: -1;
    text-align: center;
  }
  #logo {
    font-size: x-large;
    font-weight: bold;
    padding: 10px 50px;
    border: 1px solid black;
    border-collapse: collapse;
  }
  #search {
    border-radius: 25px 0px 0px 25px;
    width: calc(85% - 2px);
    height: 53px;
    font-size: large;
  }
  #search:focus-visible {
    outline-offset: 0px;
    outline: 0;
  }
  .readingGlass {
    float: right;
    padding: 15px 0px;
    border: 1px solid black;
    border-radius: 0px 25px 25px 0px;
    width: 15%;
  }
  #searchingBar {
    width: 600px;
    /* border: 1px solid gray; */
    border-radius: 25px;
  }
  #signContainer {
    padding: 15px 0px;
  }
  #signIn,
  #signUp {
    border: 1px solid black;
    padding: 7.5px 15px;
    border-radius: 15px;
  }
</style>
