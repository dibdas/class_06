<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <show-text v-bind:msg="message" ></show-text>
    <my-button v-on:myEvent="onClick"/>
  </div>
</template>

<script>
import axios from "axios"
import ShowText from './components/ShowText.vue'
import MyButton from './components/MyButton.vue'

export default {
  name: 'app',
  data(){
    return {
      message: "No Message"
    }
  },
  components: {
    ShowText,
    MyButton
  },
  methods: {
    onClick(){      
      axios.get("http://localhost:3000/goodbye")
      .then(response => {
        this.message = response.data
      })
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
</style>
