<template>
  <div id="app">
    <screen :expression="expression"></screen>
    <handler :expression.sync="expression"></handler>
  </div>
</template>

<script>
import screen from './screen.vue';
import handler from './handler.vue';

export default {
  el: 'app',
  data () {
    return {
      expression: ''
    }
  },
  components: {screen, handler}
}
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  margin: 0;
  padding: 0;
  font-family: Helvetica, sans-serif;
}
#app {
  width: 300px;
  height: 300px;
  margin: 60px auto;
}
</style>
