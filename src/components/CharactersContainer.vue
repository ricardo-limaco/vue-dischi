<template>
  <div>

    <header>
      <img src="../assets/Logo.png" alt="logo">
    </header>

    <div class="container pt-5">
      <div class="row justify-content-between gy-4">
        <CharacterCard v-for="(character, i) in charactersList" :key="i"
        :poster="character.poster"
        :title="character.title"
        :author="character.author"
        :year="character.year"
        ></CharacterCard>
      </div>
    </div>

    <Loader v-if="loading === true"></Loader>
  </div>
</template>




<script>
import axios from "axios";
import CharacterCard from "./CharacterCard.vue";
import Loader from "./Loader.vue";


export default {
  name: "CharactersContainer",
  components: { CharacterCard, Loader },
  data() {
    return {
      charactersList: [],
      loading: true,
      api: "https://flynn.boolean.careers/exercises/api/array/music"
    };
  },

  methods: {
    fetchData() {
      this.loading = true;

      axios.get(this.api).then((resp) => {
        this.charactersList = resp.data.response;
        this.loading = false;

      });
    },
  },

  mounted() {
    setTimeout(this.fetchData, 500);
  },
};
</script>