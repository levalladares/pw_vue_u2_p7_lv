<template>
  <h2>{{ titulo }}</h2>
  <p>{{ numero }} <sup>2</sup> ={{ calcularCuadradoComputado }} </p>
  <p>{{ numero }} <sup>2</sup> ={{ calcularCuadradoComputado }} </p>
  <p>{{ numero }} <sup>2</sup> ={{ calcularCuadradoComputado }} </p>
  <p>{{ numero }} <sup>2</sup> ={{ calcularCuadradoComputado }} </p>
  <p>{{ numero }} <sup>2</sup> ={{ calcularCuadradoComputado }} </p>
  <div>
    <button v-on:click="incrementar()">+1</button>
    <button v-on:click="decrementar()">-1</button>
  </div>

</template>

<script>
export default {
  data() {
    return {
      numero: 10,
      titulo: 'Contador'
    }
  },
  methods: {
    calcularCuadraro(){
      console.log('entro a calcular');
      return this.numero * this.numero;
    },
    incrementar(){
      this.numero++;
    },
    decrementar(){
      this.numero--;
    }
  },
  computed:{
    calcularCuadradoComputado(){
      console.log('entro a calcular Computado');
      return this.numero * this.numero;
    }
  }
};
</script>

<style>
button{
  background-color: #64b687;
  border-radius: 5px;
  border: 1px solid black;
  color: white;
  cursor: pointer;
  margin: 0px 5px;
  padding: 5px 15px;
} 
button:hover{
  background-color: #5AA67B;
}
</style>