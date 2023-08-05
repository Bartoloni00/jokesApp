<template>
  <nav>
    <router-link to="/">Inicio</router-link> |
    <router-link to="/about">Bromas</router-link>
  </nav>
  <main>
    <router-view/>
  </main>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #F5F5F5;
  /* background: #041424; */
background: #1A183E;
background: radial-gradient(at center bottom, #0c0a2c, #051424);
  min-height: 100vh;
}
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

nav {
  padding: 10px;
  background-color: #0b335c55;
  margin-bottom: 2em;
}

nav a {
  text-decoration: none;
  padding: 5px 10px;
  font-weight: bold;
  color: #F5F5F5;
  transition: all .3s;
}
nav a:hover{
  color: #FFA500;
}

nav a.router-link-exact-active {
  border-bottom: 2px solid #FFA500;
}
@media (max-width: 520px) {
        nav{
            padding: 20px;
        }
        nav a{
          padding: 10px 20px;
        }
    }
</style>
