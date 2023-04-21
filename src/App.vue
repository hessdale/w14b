<template>
  <div id="app">
    <display-joke-button></display-joke-button>
    <normal-joke-button></normal-joke-button>
    <snake-joke-button></snake-joke-button>
    <loud-joke-button></loud-joke-button>
    <get-joke-button></get-joke-button>
  </div>
</template>

<script>
import NormalJokeButton from "@/components/NormalJokeButton.vue";
import SnakeJokeButton from "@/components/SnakeJokeButton.vue";
import LoudJokeButton from "@/components/LoudJokeButton.vue";
import GetJokeButton from "@/components/GetJokeButton.vue";
import DisplayJokeButton from "@/components/DisplayJokeButton.vue";
export default {
  name: "App",
  components: {
    NormalJokeButton,
    SnakeJokeButton,
    LoudJokeButton,
    GetJokeButton,
    DisplayJoke,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
