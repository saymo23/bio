<template>
  <div id="app">
    <sidebar>
      <div id="profile">
        <div class="foto"></div>
      </div>
      <div id="nav">
        <router-link to="/">About Me</router-link>
        <router-link to="/about">About</router-link>
      </div>
    </sidebar>
    <router-view/>
    <div id="breadcrumbs">Migajas</div>
  </div>
</template>

<style lang="scss">
body{
  background-color: #17354a;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: grid;
  width: 100%;
  height: 100vh;
  grid-template-columns: 25% 75%;
  grid-template-rows: 80px auto;
  grid-template-areas: "sidebar head"
                       "sidebar content";
}
sidebar{
  grid-area: sidebar;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
#profile{
  grid-area: sidebar;
  .foto{
    background-image: url(/img/foto.jpg);
    background-size: contain;
    background-repeat: no-repeat;
    width: 200px;
    height: 200px;
    border: 3px solid #42b983;
    border-radius: 200px;
    
  }
}
#breadcrumbs{
  grid-area: head;
}
router-view{
  grid-area: content;
}
#nav {
  display: flex;
  flex-direction: column;
  padding: 30px;
  a {
    font-weight: bold;
    color: #9acdff;
    padding-bottom: 1rem;
    text-decoration: none;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
