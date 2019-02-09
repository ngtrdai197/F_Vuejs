<template>
  <div id="app">
    <Header></Header>
    <HelloWorld :msg="movie_name" title="Say what ?" @clickedSomething="handleClickInParent"/>

    <h2>
      App-Component message:
      <span v-if="checkType">Waiting for typing ...</span>
      {{message}}
    </h2>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header.vue";

export default {
  name: "app",
  components: {
    HelloWorld,
    Header
  },
  data: function() {
    return {
      message: "",
      checkType: true,
      movie_name: "Danh sách phim"
    };
  },
  methods: {
    handleClickInParent: function(value) {
      this.message = value;
      if (this.message !== "") {
        this.checkType = !this.checkType;
      }
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
