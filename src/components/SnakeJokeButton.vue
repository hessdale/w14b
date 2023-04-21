<template>
  <div>
    <button @click="joke_snake">Snake</button>
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
      this.joke = joke.replaceAll(` `, `_`);
    },
    joke_snake: function () {
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