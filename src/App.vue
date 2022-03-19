<template>
<SingfupForm  />
</template>

<script>
import SingfupForm from './components/SingupForm.vue'
export default {
  name: 'App',
  components: {SingfupForm }
}
</script>


<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body {
  margin-top:0;
  background-color: whit;
}
</style>
