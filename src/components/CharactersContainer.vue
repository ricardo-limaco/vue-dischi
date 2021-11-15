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

  </div>
</template>




<script>
import axios from "axios";
import CharacterCard from "./CharacterCard.vue";

export default {
  name: "CharactersContainer",
  components: { CharacterCard },
  data() {
    return {
      charactersList: [],
      loading: true,
    };
  },
  methods: {
    fetchData(url) {
      this.loading = true;

      axios.get(url).then((resp) => {
        this.charactersList = resp.data.response;
      });
    },
  },
  mounted() {
    this.fetchData("https://flynn.boolean.careers/exercises/api/array/music");
  },
};
</script>