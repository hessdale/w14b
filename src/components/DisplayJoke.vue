<template>
  <div>
    <h1>{{ joke }}</h1>
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
    JokeDisplay(joke) {
      this.joke = undefined;
      this.joke = joke;
    },
    makelwr() {},
  },
  mounted() {
    this.$root.$on(`joke_request`, this.JokeDisplay);
  },
};
</script>

<style scoped>
h1 {
  text-transform: lowercase;
}
</style>