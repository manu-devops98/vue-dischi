<template>
  <header>
    <div class="container-img">
      <img src="../assets/img/spotify-logo.png" alt="" />
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style lang="scss">
header {
  //   height: 50px;
  background-color: #2e3a46;
  display: flex;
  .container-img {
    width: 10%;
    img {
      width: 25%;
    }
  }
}
</style>
