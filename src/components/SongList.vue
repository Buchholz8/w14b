<template>
  <div>
    <h4>Songs:</h4>
    <section>
      <p>{{ song[`title`] }}</p>
      <p>{{ song[`artist`] }}</p>
      <img :src="song.image_url" alt="Music Covers" />
      <button @click="playlist">+ To Playlist</button>
      <button @click="select_song">Play</button>
    </section>
  </div>
</template>
//is this hidden
<script>
export default {
  methods: {
    playlist() {
      this.$root.$emit(`playlist`, this.song);
    },
    select_song() {
      this.$root.$emit(`select_song`, this.song[`title`] , this.song[`artist`] , this.song.image_url );
    },
  },
  props: {
    song: Object,
  },
};
</script>

<style scoped>
</style>