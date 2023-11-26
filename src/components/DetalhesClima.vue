<script>
  export default {
    name: "detalhesClima",
    props: {
      dadosClima: Object,
    }
  }
</script>

<template>
  <div class="clima">
    <h1 class="temperatura"> {{ dadosClima?.main.temp.toString().substring(0, 2) }}°c</h1>
    <h2 class="cidade"> {{ dadosClima?.name }} </h2>
    <div class="detalhes">
      <div class="coluna">
        <img src="@/assets/img/humidity.png">
        <div>
          <p class="humidade"> {{ dadosClima?.main.humidity }}%</p>
          <p>humidade</p>
        </div>
      </div>
      <div class="coluna">
        <img src="@/assets/img/wind.png">
        <div>
            <p class="vento">{{ dadosClima?.wind.speed }}km/h</p>
            <p>Velocidade do vento</p>
          </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.clima .temperatura {
  font-size: 80px;
  font-weight: 500;
}
.clima .cidade {
  font-size: 45px;
  font-weight: 500;
  margin-top: -10px;
}
.detalhes {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 20px;
  margin-top: 50px;
}
.coluna {
  display: flex;
  align-items: center;
  text-align: left;
}
.coluna img {
  width: 40px;
  height: 40px;
  margin-right: 10px;
}
.humidade,
.vento {
  font-size: 28px;
  margin-top: 6px;
}
</style>