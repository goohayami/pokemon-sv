<script setup>
Vue.onMounted(() => {
  const child = Vue.ref(document.querySelector(".child"));
  console.log(child.value);
  const cb = function (entries, observer) {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        console.log("inview");
        entry.target.classList.add("inview");
        document.querySelector(".pp").classList.add("inview");
        // observer.unobserve(entry.target);
      } else {
        console.log("outview");
        entry.target.classList.remove("inview");
        document.querySelector(".pp").classList.remove("inview");
      }
    });
    // alert("ok");
  };
  const io = new IntersectionObserver(cb);
  io.observe(child.value);
});
</script>

<template>
  <h3>スカーレット・バイオレット</h3>
  <p>発売3日間で販売本数1000万本突破</p>
  <p>
    物語の舞台はパルデア地方となり、伝説のポケモンに乗って冒険。背中に飛び乗り、草原や空、海、あらゆる場所を駆け巡る。
  </p>
  <p>
    また、冒険の始まりは学校でプレイヤーは生徒として入学し、課外授業のテーマは”宝探し”。自分だけの宝物を探す旅に出るストーリー。
  </p>

  <div class="img">
    <img style="width: 75%" src="assets/sv_01.png" alt="" />
  </div>
  <br />
  <h4>おじさんSVにはまる</h4>
  <p class="pp">
    ポケモンシリーズは前作の盾から参戦しているのだが、あまり面白味を感じられず、クリア後はそのまま放置し、ポケモンGoでジムレイドなどを楽しんでいる程度だった。<br />ポケモンGoをやっているおじさんは多い。
  </p>
  <p>
    今回のSVについては購入するつもりはなく、ダウンロードした理由も、ただなんとなく。<br />前作のこともあり期待しないではじめたのだが・・・しかし思いのほか楽しい。
  </p>
  <p>おかしい。非常に楽しい。というか辞め時がわからない。</p>
  <p>
    ジムを回り、ヌシを探し、スター団と戦う。<br />あっという間の3日でエンディングを迎え、またいつもの生活に戻る予定だったのだが、ここからの沼がひどかった。
  </p>

  <br /><br /><br /><br />
  <p class="child">kokokokokokokokoko</p>
  <br /><br /><br /><br />
</template>

<style>
.img {
  display: flex;
  justify-content: center;
  margin-right: 20px;
}
.inview {
  color: red;
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
  }
  .img {
    width: 40%;
    height: 40%;
    display: flex;
  }
}
</style>
