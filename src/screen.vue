<template>
  <div id="screen">
    <h1>{{ expression }}</h1>
  </div>
</template>

<script>
export default {
  props: ['expression']
}
</script>

<style>
  #screen {
    color: aqua;
    overflow: hidden;
    width: 100%;
    height: 60px;
    text-align: right;
    background-color: #4A0909;
  }
</style>
