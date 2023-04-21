<template>
  <div></div>
</template>

<script>
//importing axios
import axios from "axios";
export default {
  methods: {
    //function that emits joke to other components
    sendJoke(joke) {
      joke;
      this.$root.$emit(`joke_request`, this.joke);
    },
  },
  data() {
    return {
      joke: undefined,
    };
  },
  mounted() {
    axios
      .request({
        url: `https://ron-swanson-quotes.herokuapp.com/v2/quotes`,
      })
      //response that takes returned data and uses function to send it to other components
      .then((response) => {
        response;
        this.joke = response.data[0];
        this.sendJoke();
        console.log(`request success`);
      })
      //error function
      .catch((error) => {
        error;
        console.log(`request error`);
      });
  },
};
</script>

<style scoped>
</style>