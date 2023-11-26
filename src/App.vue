<script>
import BuscarApiVue from "@/components/BuscarApi.vue";
import ImagemClima from "@/components/ImagemClima.vue";
import DetalhesClima from "@/components/DetalhesClima.vue";
import ErroCidadeNaoEncontrada from "@/components/ErroCidadeNaoEncontrada.vue";

export default {
  name: "App",
  components: {
    BuscarApiVue,
    ImagemClima,
    DetalhesClima,
    ErroCidadeNaoEncontrada,
  },
  data() {
    return {
      resultadoBusca: null,
      mostrarErro: false,
    };
  },
  methods: {
    pegarResultadoBusca(resultado) {
      this.mostrarErro = resultado.cod === "404";
      this.resultadoBusca = this.mostrarErro ? null : resultado;
    },
  },
};
</script>

<template>
  <div class="container">
    <BuscarApiVue @resultadoBusca="pegarResultadoBusca" />
    <div v-if="resultadoBusca">
      <ImagemClima :descricaoDoTempo="resultadoBusca?.weather[0].main" />
      <DetalhesClima :dadosClima="resultadoBusca" />
    </div>
    <ErroCidadeNaoEncontrada v-if="mostrarErro" />
  </div>
</template>

<style scoped>
.container {
  width: 90%;
  max-width: 470px;
  background: var(--bg-app);
  border-radius: 20px;
  color: var(--white);
  margin: 100px auto 0;
  padding: 40px 35px;
  text-align: center;
}
</style>
