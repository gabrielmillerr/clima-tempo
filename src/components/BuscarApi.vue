<script>
  export default {
    name: "buscarApi",
    data() {
      return {
        cidade: "",
      }
    },
    methods: {
      async buscarApi() {
        try {
        const keyAPI = "94a2eb4f9654911c1d5bd7215eef2a24";
        const apiUrl = `https://api.openweathermap.org/data/2.5/weather?q=${this.cidade}&appid=${keyAPI}`
        const response = await fetch(apiUrl);
        const data = await response.json();
        
        this.$emit('resultadoBusca', data)
      } catch (error) {
        console.error("Erro ao buscar dados da API:", error);
      }
    }
    }
  }
</script>

<template>
  <div class="buscar">
    <input type="text" placeholder="Qual cidade?" v-model="cidade" />
    <button @click="buscarApi"><img src="@/assets/img/search.png" /></button>
  </div>
</template>

<style scoped>
.buscar {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.buscar input {
  border: 0;
  outline: 0;
  background: var(--gray-light);
  color: var(--color-input);
  padding: 10px 25px;
  height: 60px;
  border-radius: 30px;
  flex: 1;
  margin-right: 16px;
  font-size: 18px;
}
.buscar button {
  border: 0;
  outline: 0;
  background: var(--gray-light);
  border-radius: 50%;
  width: 60px;
  height: 60px;
  cursor: pointer;
}
.buscar button img {
  width: 20px;
  height: 20px;
}
</style>