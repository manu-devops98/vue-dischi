<template>
  <main>
    <Select @changeSelect="changeGenre($event)" />
    <div v-if="cards" class="container-cards">
      <Cards
        v-for="(card, index) in filteredAlbums"
        :key="index"
        :image="card.poster"
        :imageAlt="card.title"
        :title="card.title"
        :author="card.author"
        :date="card.year"
      />
    </div>
    <div v-else class="loading">
      <img src="../assets/img/spotify-logo.png" alt="" />
      <h1>Caricamento in corso ...</h1>
    </div>
  </main>
</template>

<script>
import axios from "axios";
import Cards from "./Cards.vue";
import Select from "./Select.vue";
// import { library } from "@fortawesome/fontawesome-svg-core";
// import { faUserSecret } from "@fortawesome/free-solid-svg-icons";
// import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

// library.add(faUserSecret);

export default {
  name: "Main",
  components: {
    Cards,
    Select,
    // FontAwesomeIcon,
  },
  data() {
    return {
      cards: null,
      filteredAlbums: null,
      queryApi: "https://flynn.boolean.careers/exercises/api/array/music",
      selectValue: "All",
    };
  },
  methods: {
    changeGenre(selected) {
      this.selectValue = selected;
      console.log("valore var. appoggio", this.selectValue);
      if (this.selectValue == "" || this.selectValue == "All") {
        this.filteredAlbums = this.cards;
      } else {
        this.filteredAlbums = this.cards.filter((album) => {
          return album.genre.toLowerCase() == this.selectValue;
        });
      }
    },
  },
  mounted() {
    axios
      .get(this.queryApi)
      .then((result) => {
        this.cards = result.data.response;
        this.filteredAlbums = this.cards;
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
  height: calc(100vh - 55px);
  .container-cards {
    display: flex;
    flex-wrap: wrap;
    width: 70%;
    margin: 0 auto;
    padding: 4em;
  }
  .loading {
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 5em;
    img {
      width: 30%;
    }
    h1 {
      color: white;
      font-size: 2em;
      margin-top: 2em;
    }
  }
}
</style>
