<template>
  <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
  <p>{{ event.description }}</p>
   <div id="flash_editMessage" v-if="GStore.flash_editMessage">
    {{ GStore.flash_editMessage }}
  </div>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore']
}
</script>

<style scoped>
@keyframes orangefade {
  from {
    background: #b99942;
  }
  to {
    background: transparent;
  }
}

#flash_editMessage {
  animation-name: orangefade;
  animation-duration: 3s;
}
</style>
