<template>
  <div>
    <button @click="joke_normal">Normal</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      joke: undefined,
    };
  },

  methods: {
    JokeDisplay: function (joke) {
      this.joke = joke.toLowerCase();
    },
    joke_normal: function () {
      this.$root.$emit(`joke_selected`, this.joke);
    },
  },
  mounted() {
    this.$root.$on(`joke_request`, this.JokeDisplay);
  },
};
</script>

<style scoped>
</style>