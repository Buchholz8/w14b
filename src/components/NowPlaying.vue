<template>
  <div>
    <h4>Now Playing :</h4>
    <p>{{ playing }}</p>
  </div>
</template>

<script>
export default {
  methods: {
    handle_song: function(details) {
      this.playing = details;
    },
  },
  mounted() {
    this.$root.$on(`select_song`, this.handle_song);
  },
  data() {
    return{
        playing: `Pick A Song`
    }
  },
    props: {
    song: Object,
  },
};
</script>

<style scoped>
</style>