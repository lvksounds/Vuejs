<template>
  <div class="hello">
    <input type="text" v-model="input_data">
    <button v-on:click="enviaDados" value="enviar">Enviar</button>
    <p>{{ name }}</p>
  </div>
</template>

<script>
export default {
  name: 'pageBody',
  props: {
    msg: String
  },
  data () {
    return {
      name: "",
      input_data: "",
    }
  },
  methods: {
    enviaDados(event){
      event.preventDefault(); 
      
      this.name = this.input_data
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
