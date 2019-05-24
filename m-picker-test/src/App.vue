<template>
  <div id="app">
    <button @click="toShow">开启</button>
    <lw-picker
            :show="show"
            :link="link"
            @cancel="close"
            @confirm="confirmFn"></lw-picker>
  </div>
</template>

<script>
import LwPicker from './components/LwPicker.vue'

export default {
  name: 'app',
  data(){
    return {
      show: false,
      columns: 3,
      link:true
    }
  },
  methods:{
    close() {
      this.show = false
    },
    toShow() {
      this.show = true
    },
    confirmFn(val) {
      console.log(val,"val");
      this.show = false

    }
  },
  components: {
    LwPicker
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
