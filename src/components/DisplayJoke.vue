<template>
  <div>
    <!-- displaying joke variable -->
    <h1>{{ joke }}</h1>
  </div>
</template>

<script>
export default {
  //setting joke variable to undefined
  data() {
    return {
      joke: undefined,
    };
  },
  //function to take data $emitted from components and display it
  methods: {
    JokeDisplay(joke) {
      this.joke = undefined;
      this.joke = joke;
    },
  },
  //listening for emitted data from other comnponents
  mounted() {
    this.$root.$on(`joke_selected`, this.JokeDisplay);
  },
};
</script>

<style scoped>
</style>