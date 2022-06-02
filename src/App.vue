<template>
  <div class="">
    <h1>   {{inputText}} </h1>
    <h2 :class="clasePruebas" v-text="texto"></h2>
    <p v-html="textoHtml"></p>
    <input type="text" v-model="inputText">
    <img :src="img" alt="">
    <br>
    <br>
    <br>
    <button @click="incrementarContador()">
      Botón {{contador}}
    </button>
    <input type="text" @keyup="presionarTecla()" v-model="inputEvent">
    <select @change="cambiarColor()" v-model="colorContenedor">
      <option value="contenedor verde">verde</option>
      <option value="contenedor rojo">rojo</option>
      <option value="contenedor amarillo">amarillo</option>
    </select>
    <br>
    <div :class="contenedor" ></div>
    <br>
    <br>
    <form @submit="enviarFormulario" >
      <!-- <input type="text" v-model="inputForm"> -->
      <textarea cols="30" rows="10" v-model="inputForm"></textarea>
      <input type="submit" value="Enviar">
    </form>
    <input type="text" @input="cambiarParrafo" v-model="inputForm">
    <br>
    <p> {{parrafo}} </p>
  </div>
</template>
<script>
export default {
  name: "App",
  data() {
    return {
      mensaje: "vue",
      texto: 'Holamundo',
      textoHtml: '<a href="https://google.com"> Otra frase </a>',
      inputText: " Escribe un texto",
      img: "https://picsum.photos/300/300",
      clasePruebas: "texto-rojo",
      // clase 3
      contador: 0,
      inputEvent: "",
      contenedor: "contenedor azul",
      colorContenedor: "contenedor verde",
      inputForm: "",
      parrafo: "",
    }
  },
  methods: {
    incrementarContador() {
      this.contador++;
    },
    presionarTecla() {
      alert(this.inputEvent);
    },
    cambiarColor() {
      this.contenedor = this.colorContenedor;
    },
    enviarFormulario(){
      this.parrafo = this.inputForm;
    },
    cambiarParrafo(){
      this.parrafo = this.inputForm;
    }
  },
}
</script>
<style>
.texto-azul{
  color: blue;
}
.texto-rojo{
  color: red;
  background-color: black;
}
.contenedor{
  width: 100px;
  height: 100px;
}
.azul{
  background-color: blue;
}
.verde{
  background-color: green;
}
.rojo{
  background-color: red;
}
.amarillo{
  background-color: yellow;
}
</style>
