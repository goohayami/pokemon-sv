<template>
  <section>
    <div class="container">
      <div class="resipe">
        <h3>時短レシピ</h3>
        <img style="width: 101%" src="assets/spa1.png" alt="" />
        <img style="width: 101%" src="assets/spa2.png" alt="" />
        <img style="width: 101%" src="assets/spa3.png" alt="" />
        <img style="width: 101%" src="assets/spa4.png" alt="" />
      </div>
    </div>

    <br /><br /><br /><br />
  </section>
</template>

<style scoped>
h3 {
  margin-bottom: 0;
}

@media screen and (min-width: 830px) {
  .container {
    /* text-align: center; */
    justify-content: center;
    display: flex;
  }
  .resipe {
    width: 70%;
  }
  h3 {
    font-size: 32px;
    color: rgb(49, 121, 108);
  }
}
</style>
