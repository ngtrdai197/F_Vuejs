<template>
  <div class="container">
    <div class="jumbotron">
      <h1 class="display-3">{{msg}}</h1>
      <hr class="my-2">

      <button v-on:click="onAdd">Click me</button>
      <p>Value is: {{count}}</p>

      <hr>
      <input type="text" v-model="message" @keyup="handleClick">
      <p>
        Message is:
        <span class="ms-v">{{message}}</span>
      </p>
      <button @click="handleClick">Click something</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: function() {
    return {
      count: 0,
      message: ""
    };
  },
  props: ["msg", "title"],
  methods: {
    onAdd: function() {
      this.count++;
    },
    handleClick: function() {
      this.$emit("clickedSomething", this.message);
    }
  },
  
};
</script>
<style scoped>
.ms-v {
  color: brown;
  font-weight: bold;
  text-transform: uppercase;
}
</style>
