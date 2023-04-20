<template>
  <div>
    <h4>Now Playing :</h4>
    <p>{{ playing }}</p>
  </div>
</template>

<script>
export default {
  methods: {
    handle_song(name){
      this.playing = name
    },
  },
  mounted () {
      this.$root.$on(`select_song` , this.song[`title`])
    },
};
</script>

<style scoped>
</style>