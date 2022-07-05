<template>
  <div class="hello">
    <p>{{ input_name }}</p>
    <input type="text" v-model="input_name" placeholder="Insira se nome aqui">
    <input type="submit" value="Enviar" v-on:click="submitForm">
  </div>
</template>

<script>
export default {
  name: 'pageBody',
  props: {
    msg: String
  },
  data() {
    return {
      name: "",
      input_name:"" 
    }
  },
  methods: {
    submitForm(e) {
      e.preventDefault();

      this.name = this.input_name
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
