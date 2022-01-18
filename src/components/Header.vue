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
  background-color: #2d3a46;
  display: flex;
  height: 55px;
  .container-img {
    width: 10%;
    img {
      width: 35%;
      padding: 0.5em;
    }
  }
}
</style>
