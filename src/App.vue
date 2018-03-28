<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    Add Item <input type="text" v-on:keyup.enter="addItem()" v-model="text">
    <ul>
      <li 
        is="item-detalhe"
        v-for="(item, index) in list"
        v-bind:item="item" 
        v-on:remove="list.splice(index, 1)"></item-detalhe>
      </li>
    </ul>
  </div>
</template>

<script>
  import ItemDetalhe from './item-detalhe.vue'

  export default {
    name: 'app',
    data () {
      return {
        text: '',
        msg: 'Teste Vue.js',
        list: []
      }
    },
    components: { ItemDetalhe },
    methods: {
      addItem () {
        this.list.push({text: this.text})
        this.text = ''
      }
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  a {
    color: #42b983;
  }
</style>
