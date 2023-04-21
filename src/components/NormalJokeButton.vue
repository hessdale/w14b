<template>
  <div>
    <button>Normal</button>
    <p>{{ joke }}</p>
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
      this.joke = undefined;
      this.joke = joke;
    },
  },
  mounted() {
    this.$root.$on(`joke_request`, this.JokeDisplay);
  },
};
</script>

<style scoped>
p {
  text-transform: lowercase;
}
</style>