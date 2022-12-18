<template>
  <section>
    <h3>スカーレット・バイオレット</h3>
    <p>発売3日間で販売本数1000万本突破</p>
    <p>
      物語の舞台はパルデア地方となり、伝説のポケモンに乗って冒険。背中に飛び乗り、草原や空、海、あらゆる場所を駆け巡る。
    </p>
    <p>
      また、冒険の始まりは学校でプレイヤーは生徒として入学し、課外授業のテーマは”宝探し”。自分だけの宝物を探す旅に出るストーリー。
    </p>
  </section>
  <div class="img">
    <img style="width: 75%" src="assets/sv_01.png" alt="" />
  </div>
  <br /><br /><br />
</template>

<style>
.img {
  display: flex;
  justify-content: center;
  margin-right: 20px;
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
