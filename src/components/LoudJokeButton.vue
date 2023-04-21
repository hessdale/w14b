<template>
  <div>
    <button @click="makeloudjoke">Loud</button>
    <p>{{ joke }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      joke: undefined,
      loudjoke: undefined,
    };
  },

  methods: {
    JokeDisplay: function (joke) {
      this.joke = undefined;
      this.joke = joke;
      console.log(joke);
    },
  },
  makeloudjoke: function () {
    let makejoke = this.joke;
    let loudjoke = makejoke.toUpperCase();
    console.log(loudjoke);
  },

  mounted() {
    this.$root.$on(`joke_request`, this.JokeDisplay);
  },
};
</script>

<style scoped>
</style>