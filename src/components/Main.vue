<template>
  <main>
    <div class="container-cards">
      <Cards
        v-for="(card, index) in cards"
        :key="index"
        :image="card.poster"
        :imageAlt="card.title"
        :title="card.title"
        :author="card.author"
        :date="card.year"
      />
      <!-- <div class="cards">
        <div class="container-img">
          <img src="../assets/img/spotify-logo.png" alt="" />
        </div>
        <h1>New Jersey</h1>
        <h3>Bon Jovi</h3>
        <h4>1997</h4>
      </div> -->
    </div>
  </main>
</template>

<script>
import axios from "axios";
import Cards from "./Cards.vue";
export default {
  name: "Main",
  components: {
    Cards,
  },
  data() {
    return {
      cards: null,
      queryApi: "https://flynn.boolean.careers/exercises/api/array/music",
    };
  },
  mounted() {
    axios
      .get(this.queryApi)
      .then((result) => {
        console.log(result);
        this.cards = result.data.response;
        console.log(this.cards);
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>

<style lang="scss">
main {
  background-color: #1d2c3b;
  height: 100vh;
  .container-cards {
    display: flex;
    flex-wrap: wrap;
    width: 70%;
    margin: 0 auto;
    padding: 4em;
    // .cards {
    //   background-color: #2d3a46;
    //   width: calc(100% / 5 - 20px);
    //   text-align: center;
    //   padding: 2em;
    //   .container-img {
    //     img {
    //       width: 100%;
    //       margin-bottom: 1em;
    //     }
    //   }
    //   h1 {
    //     font-size: 1.2em;
    //     color: white;
    //     text-transform: uppercase;
    //     margin-bottom: 0.5em;
    //   }
    //   h3 {
    //     font-size: 1em;
    //     color: #817d73;
    //   }
    //   h4 {
    //     font-size: 0.8em;
    //     color: #817d73;
    //   }
    // }
  }
}
</style>
