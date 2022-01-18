<template>
  <div class="cards">
    <div class="container-img">
      <img :src="image" :alt="imageAlt" />
    </div>
    <h1>{{ title }}</h1>
    <h3>{{ author }}</h3>
    <h4>{{ date }}</h4>
  </div>
</template>

<script>
export default {
  name: "Cards",
  props: ["image", "imageAlt", "title", "author", "date"],
};
</script>

<style lang="scss">
.cards {
  background-color: #2d3a46;
  width: calc(100% / 5 - 20px);
  text-align: center;
  padding: 1em;
  margin: 0 10px 10px 10px;
  .container-img {
    width: 100%;
    img {
      width: 100%;
      margin-bottom: 1em;
    }
  }
  h1 {
    font-size: 1.2em;
    color: white;
    text-transform: uppercase;
    margin-bottom: 0.5em;
  }
  h3 {
    font-size: 1em;
    color: #817d73;
  }
  h4 {
    font-size: 0.8em;
    color: #817d73;
  }
}
</style>
