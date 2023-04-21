<template>
  <div>
    <!-- click event listener with function to change text -->
    <button @click="joke_snake">Snake</button>
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

  methods: {
    //function for replacing spaces with underscores with emmited data from joke api component
    JokeDisplay: function (joke) {
      this.joke = joke.replaceAll(` `, `_`);
    },
    //function for event listener click that $emits data to for display to listen for
    joke_snake: function () {
      this.$root.$emit(`joke_selected`, this.joke);
    },
  },
  //listening for emitted data from joke request component
  mounted() {
    this.$root.$on(`joke_request`, this.JokeDisplay);
  },
};
</script>

<style scoped>
</style>