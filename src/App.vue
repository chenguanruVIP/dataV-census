<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
*{
    margin:0px;
    padding:0px
}
body,html{
    width: 100%;
    height: 100%;
    background: #000000;
}
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    width: 100%;
    height: 100%;
}

</style>
