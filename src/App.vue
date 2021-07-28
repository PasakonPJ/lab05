<template>
  <div id="flashMessage" v-if="GStore.flashMessage">
    {{ GStore.flashMessage }}
  </div>
  <div id="flash_editMessage" v-if="GStore.flash_editMessage">
    {{ GStore.flash_editMessage }}
  </div>

  <div id="nav">
    <router-link :to="{ name: 'EventList' }">Home</router-link> |
    <router-link :to="{ name: 'About' }">About</router-link>
  </div>

  <!-- new element -->
  <router-view />
</template>
<script>
export default {
  inject: ['GStore']
}
</script>

<style>
@keyframes yellowfade {
  from {
    background: #42b983;
  }
  to {
    background: transparent;
  }
}

@keyframes orangefade {
  from {
    background: #b99942;
  }
  to {
    background: transparent;
  }
}
#flashMessage {
  animation-name: yellowfade;
  animation-duration: 3s;
}

#flash_editMessage {
  animation-name: orangefade;
  animation-duration: 3s;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
h4 {
  font-size: 20px;
}
</style>
