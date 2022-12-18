<template>
  <header>
    <nav>
      <div class="drawer">
        <div id="logo">POKE</div>
        <div class="Toggle"><span></span> <span></span><span></span></div>
      </div>

      <div class="menu">
        <ul>
          <li><router-link class="router" to="/">ポケモンとは</router-link></li>
          <li>
            <router-link class="router" to="/add1">ポケモン概説1</router-link>
          </li>
          <li>
            <router-link class="router" to="/add2">ポケモン概説2</router-link>
          </li>
          <li>
            <router-link class="router" to="/add3"
              >ポケットモンスターシリーズ</router-link
            >
          </li>
        </ul>
      </div>
    </nav>
    <div class="router-view">
      <router-view></router-view>
    </div>
  </header>
  <footer class="footer">
    <p>Copyrigh©2022 50過ぎてポケモンかよ Co.,Ltd. All Rights Reserved.</p>
  </footer>
</template>

<script>
$(function () {
  $(".Toggle").click(function () {
    $(this).toggleClass("active");
    $(".menu").toggleClass("open");
  });
});
$(function () {
  $(".menu").click(function () {
    $(".Toggle").toggleClass("active");
    $(this).toggleClass("open");
  });
});
</script>

<style>
body {
  font-family: "Noto Sans JP", sans-serif;
  margin: 0;
  padding: 0;
}

.router-view {
  margin-left: 16px;
  margin-right: 16px;
}

/* パソコン表示の時 */
@media screen and (min-width: 800px) {
  .router-view {
    margin-left: 104px;
    margin-right: 104px;
  }
  .footer {
    height: 40px;
    font-size: 12px;
    line-height: 1rem;
    /* background-color: red; */
  }
}

footer {
  padding: 0;
  margin: 0;
  position: fixed; /*←絶対位置*/
  bottom: 0; /*下に固定*/
  width: 100%;
  height: 70px;
  background: #f6f6f6;
  text-align: center;
}

nav {
  width: 100%;
  height: 70px;
  position: relative;
  background: #f6f6f6;
}

.drawer {
  background-color: rgba(225, 225, 225, 0.4);
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  position: relative;
  height: 70px;
  padding: 0 1em;
}

/*ナビゲーション部分*/
ul {
  padding: 0;
  margin: 0;
}

li {
  list-style: none;
}

a.router {
  margin-right: 60px;
}
.router {
  display: block;
  font-weight: bold;
  padding: 2em;
  border-bottom: 1px dotted #ccc;
  color: #333;
  text-decoration: none;
}

.router:hover {
  color: orange;
}

/* 出てくるメニューの大きさや速さ調節 */
.menu {
  text-align: center;
  background-color: rgba(225, 210, 70, 0.9);
  transition: 0.5s ease;
  -webkit-transform: translateX(-105%);
  transform: translateX(-105%);
}

.menu.open {
  -webkit-transform: translateX(0%);
  transform: translateX(0%);
}

.Toggle {
  display: block;
  position: fixed;
  width: 42px;
  height: 42px;
  cursor: pointer;
  z-index: 3;
  /* メニューボタン、ここで左右の指定 */
  right: 16px;
}

.Toggle span {
  display: block;
  position: absolute;
  width: 40px;
  border-bottom: solid 4px #333;
  /* ここも反応していないみたい */
  /* -webkit-transition: 0.35s ease-in-out;
  -moz-transition: 0.35s ease-in-out;
  transition: 0.35s ease-in-out; */
}

.Toggle span:nth-child(1) {
  top: 5px;
}
.Toggle span:nth-child(2) {
  top: 18px;
}
.Toggle span:nth-child(3) {
  top: 32px;
}
.Toggle.active span:nth-child(1) {
  top: 18px;
  -webkit-transform: rotate(-45deg);
  -moz-transform: rotate(-45deg);
  transform: rotate(-45deg);
}

.Toggle.active span:nth-child(2),
.Toggle.active span:nth-child(3) {
  top: 18px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  transform: rotate(45deg);
}

/* ここからメディアクエリなんだけど、Htmlのヘッドタグにレスポンシブかいたらここは反応していないみたいなの */
@media screen and (min-width: 600px) {
  header::after {
    display: none;
  }

  nav {
    display: flex;
  }

  .Toggle {
    display: none;
  }
  .menu {
    width: 100%;
    font-size: 0.9em;
    background-color: transparent;
    margin: 0 10px;
    -webkit-transform: translateX(0);
    transform: translateX(0);
  }
  .menu ul {
    height: 70px;
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-end;
    align-items: center;
  }
  .router {
    padding: 0 1em;
    border-bottom: none;
  }
  .router:hover {
    background-color: transparent;
  }
}
</style>
