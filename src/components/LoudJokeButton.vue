<template>
  <div>
    <!-- click event listener with function to change text -->
    <button @click="joke_loud">Loud</button>
  </div>
</template>

<script>
export default {
  data() {
    //setting joke variable to undefined
    return {
      joke: undefined,
    };
  },

  methods: {
    //function for uppercasing with emmited data from joke api component on event listener click
    JokeDisplay: function (joke) {
      this.joke = joke.toUpperCase();
    },
    //function for event listener click that $emits data to for display to listen for
    joke_loud: function () {
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