<template>
  <div>
    <!-- click event listener with function to change text -->
    <button @click="joke_normal">Normal</button>
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
    //function for lowercasing with emmited data from joke api component on event listener click
    JokeDisplay: function (joke) {
      this.joke = joke.toLowerCase();
    },
    //function for event listener click that $emits data to for display to listen for
    joke_normal: function () {
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