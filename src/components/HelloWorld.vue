<template>
  <div class="hello">
    <div :key="index" v-for="(pays, index) in pays">
      <!--<h1>Le nom du pays est : {{ pays.name.common }}</h1>-->
      <h1>Le nom du pays est : {{ pays.translations.fra.common }}</h1>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "HelloWorld",
  data() {
    return {
      pays: null,
    };
  },
  mounted() {
    axios.get("https://restcountries.com/v3.1/all").then((response) => {
      this.pays = response.data;
      console.log(this.pays);
    });
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
