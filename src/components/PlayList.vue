<template>
  <div>
    <h4>Your Favorite :</h4>
    <p> {{fav_song}} </p>
  </div>
</template>

<script>
export default {
  methods: {
    handle_fav: function (details) {
      this.fav_song = details;
    },
  },
  mounted() {
    this.$root.$on(`playlist`, this.handle_fav);
  },
  data() {
    return {
      fav_song: `Pick A Fav`,
    };
  },
  props: {
    song: Object,
  },
};
</script>

<style scoped>
</style>