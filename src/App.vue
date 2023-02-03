<template>
  <section>
    <nav>
      <router-link :to="{ name: 'home' }">Home</router-link> |
      <router-link :to="{ name: 'todo' }">ToDo</router-link> |
      <router-link :to="{ name: 'products' }">Products</router-link>
    </nav>
    <div class="body">
      <router-view />
    </div>
    <footer>This is a footer</footer>
  </section>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

section {
  display: flex;
  flex-flow: column;
  height: 100vh;
  position: relative;
}

.body {
  flex: 2;
  background: gold;
  overflow: auto;
}

footer {
  width: 100%;
  background-color: #2c3e50;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100px;

}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
