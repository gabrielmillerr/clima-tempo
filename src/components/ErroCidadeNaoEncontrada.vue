<script>
  export default {
    name: "erroCidadeNaoEncontrada"
  }
</script>

<template>
  <div>
    <div class="descricao">
      <h2>A cidade não foi encontrada.</h2>
      <p>Verique e tente novamente.</p>
    </div>
    <div>
      <img class="naoEncotrado" src="@/assets/img/naoEncontrado.svg">
    </div>
  </div>
</template>

<style scoped>
  .descricao {
    margin: 30px 0 30px 0;
  }
  .naoEncotrado {
    width: 100%;
    max-width: 350px;
    height: 250px;
    margin-left: 20px;
  }
</style>