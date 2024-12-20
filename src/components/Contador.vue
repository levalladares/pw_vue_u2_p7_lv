<template>
  <h2>{{ encabezado }} : {{ valor2 }}</h2>
  <p>{{ numero }} <sup>2</sup> ={{ calcularCuadradoComputado }} </p>
  <p>{{ numero }} <sup>2</sup> ={{ calcularCuadradoComputado }} </p>
  <div>
    <button v-on:click="incrementar()">+1</button>
    <button @:click="decrementar()">-1</button>
  </div>
  <div v-if="esVerdad">
    <h1>Feliz Navidad</h1>
  </div>
  <hr>
</template>

<script>
export default {
  data() {
    return {
      numero: this.valor,
      titulo: 'Contador'
    }
  },
  methods: {
    calcularCuadraro() {
      console.log('entro a calcular');
      return this.numero * this.numero;
    },
    incrementar() {
      this.numero++;
    },
    decrementar() {
      this.numero--;
    }
  },
  computed: {
    calcularCuadradoComputado() {
      console.log('entro a calcular Computado');
      return this.numero * this.numero;
    }
  },
  //PRIMERA FORMADE DECLARAR PROPS
  //props:['encabezado','valor']
  //SEGUNDA FORMA DE DECLARAR PROPS
  props: {
    encabezado: String,
    valor: Number,
    valor2: {
      type: Number,
      required: false,
      default: 77,
      validator(value){
        //programo mi validacion bajo mi criterio y retorno true(cuando es valido) o false
        return value <= 77;
      }
    },
    //validar que el encabezado no tenga la letra a 
    encabezado: {
      type: String,
      required: true,
      validator(value){
        return value.indexOf('a') < 0;
      }
    },
    esVerdad: {
      type: Boolean,
      required: true,
    },
    arreglo: Array,
    fecha: Date,
    objetoPersona: Object,
  }
};
</script>

<style>
button {
  background-color: #64b687;
  border-radius: 5px;
  border: 1px solid black;
  color: white;
  cursor: pointer;
  margin: 0px 5px;
  padding: 5px 15px;
}

button:hover {
  background-color: #5AA67B;
}
</style>