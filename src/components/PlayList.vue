<template>
    <div>
        <h4>Favorite Songs:</h4>
        <section>
      <p>{{ song[`title`] }}</p>
      <p>{{ song[`artist`] }}</p>
      <img :src="song.image_url" alt="Music Covers" />
      <button>+ To Playlist</button>
      <button @click="select_song">Play</button>
    </section>
    </div>
</template>

<script>
    export default {
          methods: {
    handle_playlist(name) {
      this.playing = name;
    },
  },
  mounted() {
    this.$root.$on(`playlist`, this.song);
  },
    props: {
    song: Object,
  },
    }
</script>

<style scoped>

</style>