<script>
export default {
  name: "ImagemClima",
  props: {
    descricaoDoTempo: String,
  },
  computed: {
    imagemClima() {
      switch (this.descricaoDoTempo) {
        case "Clear":
          return require("@/assets/img/clear.png");
        case "Clouds":
          return require("@/assets/img/clouds.png");
        case "Drizzle":
          return require("@/assets/img/drizzle.png");
        case "Humidity":
          return require("@/assets/img/humidity.png");
        case "Mist":
          return require("@/assets/img/mist.png");
        case "Rain":
          return require("@/assets/img/rain.png");
        case "Snow":
          return require("@/assets/img/snow.png");
        case "Wind":
          return require("@/assets/img/wind.png");
        default:
          return "";
      }
    },
  },
};
</script>

<template>
  <img :src="imagemClima" alt="Condição climática">
</template>

<style scoped>
</style>
