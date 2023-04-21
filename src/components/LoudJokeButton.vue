<template>
  <div>
    <button @click="joke_loud">Loud</button>
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
      this.joke = joke.toUpperCase();
    },
    joke_loud: function () {
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