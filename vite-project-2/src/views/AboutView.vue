<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
  {{ data }}
</template>
<script>
export default {
  data() {
    return {
      data: {},
    };
  },
  mounted() {
    const apiUrl = import.meta.env.VITE_PATH;
    //console.log(import.meta.env.VITE_PATH);
    this.$http.get(apiUrl).then((res) => {
      console.log(res.data);
      this.data = res.data.results[0];
      console.log(this.data);
    });
  },
};
</script>
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
