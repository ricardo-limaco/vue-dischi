<template>
  <div class="_card-container">
    <img class="_card-img" :src="poster" alt="">
    <h4 class="_card-title">{{ title }}</h4>
    <h5 class="_card-author">{{ author }}</h5>
    <p class="_card-year">{{ year }}</p>
  </div>
</template>




<script>
export default {
  name: "CharacterCard",
  props: ["poster", "title", "author", "year"],
};
</script>