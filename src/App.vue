<template>
  <div id="app">
    <header>
      <div class="fake-logo"></div>
    </header>
    <main>
      <select-option @choose="selectGenre"/>
      <main-container :discs="discsFiltered"/>
    </main>
  </div>
</template>

<script>
import axios from "axios"
import MainContainer from "./components/MainContainer.vue"
import SelectOption from "./components/SelectOption.vue"

export default {
  name: 'App',
  components: {
    MainContainer,
    SelectOption,
  },
  data() {
    return {
      discs: [],
      discsFiltered: [],
    }
  },
  mounted() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((response) => {
      this.discs = response.data.response;
      this.discsFiltered = response.data.response;
    })
  },
  methods: {
    selectGenre(selected) {
      if (selected === 'any') {
        this.discsFiltered = this.discs;
      } else {
        this.discsFiltered = this.discs.filter((discs) => {
          return discs.genre.toLowerCase().includes(selected);
        });
      }
    }
  }
}
</script>

<style lang="scss">
@import "./style/main.scss";

  header {
    height: 75px;
    background-color: #2e3a46;
    padding-top: 12px;

      .fake-logo {
        width: 50px;
        height: 50px;
        background-color: #1ed760;
        margin-left: 20px;
        border-radius: 50%;

      }
  }

  main {
    height: calc(100vh - 75px);
    background-color: #1e2d3b;
  }

</style>
