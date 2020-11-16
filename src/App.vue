<template>
  <div id="nav">
    <router-link to="/"></router-link> 
    <router-link to="/about"></router-link>
  </div>
  <router-view />
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

::selection {
  background-color: rgb(6, 39, 73);
  color: white;
}
::-webkit-scrollbar {
  width: 1rem;

}
::-webkit-scrollbar-track {
  background: #eee;
  box-shadow: inset 0 0 1rem #bbb;
  border-radius: .3rem;
}
::-webkit-scrollbar-thumb {
  background: rgb(16, 46, 102);
  border-radius: .3rem;
}
::-webkit-scrollbar-thumb:hover {
  background: rgb(47, 100, 96);
}
::-webkit-scrollbar-thumb:hover ::-webkit-scrollbar-track {
  background: rgb(47, 100, 96);
  box-shadow: inset 0 0 .4rem rgb(16, 46, 102);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.clearfix {
  content: "";
  display: table;
  clear: both;
}
.float {
  float: left;
}

html {
  font-family: 62.5%;
}
body {
  cursor: auto;
  
  background-size: 100%;
  background-repeat: no-repeat;
  background-image: linear-gradient(to right bottom, rgb(16, 46, 102) , rgb(47, 100, 96));
}

</style>
