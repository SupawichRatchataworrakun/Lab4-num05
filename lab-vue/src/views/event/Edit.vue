<template>
  <p>Edit the event here</p>
  <button @click="editer">EDIT ME!</button>
</template>
<script>
export default {
  props: ['event'],
  inject: ['GStore'],
  methods: {
    editer() {
      this.GStore.flashMessage =
        'You are seccessfully edited for ' + this.event.title
      setTimeout(() => {
        //After 3 seconds remove it
        this.GStore.flashMessage = ''
      }, 5000)
      //Set a flash message to appear on the next page loaded which says
      this.$router.push({
        name: 'Home',
        params: { id: this.event.id }
      })
    }
  }
}
</script>
