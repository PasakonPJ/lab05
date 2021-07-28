<template>
  <p>Edit the event here</p>
  <button @click="Edit">Edit Me >.3.></button>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'], //<==== inject the Global store
  methods: {
    Edit() {
      //Assuming successful API call to register then
      //Set a flash message to appear on the next page loaded which says
      this.GStore.flash_editMessage =
        'The data has been updated' 
      setTimeout(() => {
        //After 3 secs remove it
        this.GStore.flash_editMessage = ''
      }, 3000)
      this.$router.push({
        name: 'EventDetails'
      })
    }
  }
}
</script>
