<template>
  <div>
    <h4>Favorite Songs:</h4>
    <p>{{ song[`title`] }}</p>
    <p>{{ song[`artist`] }}</p>
    <img :src="song.image_url" alt="Music Covers" />
  </div>
</template>

<script>
    export default {
        methods: {
    handle_fav: function(details) {
      this.song[`title`] = details[0]
      this.song[`artist`] = details[1]
      this.song.image_url = details[2]
    },
  },
  mounted() {
    this.$root.$on(`playlist`, this.handle_fav);
  },
    props: {
    song: Object,
  },
    }
</script>

<style scoped>
</style>