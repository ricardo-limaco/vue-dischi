<template>
  <div class="spinner-border text-light _loader" role="status">
    <span class="visually-hidden">Loading...</span>
  </div>
</template>

<script>
export default {
  name: "Loader",
};
</script>


<style>
._loader {
  position: fixed;
  top: calc(50% - 12px);
  left: calc(50% - 12px);
}
</style>
