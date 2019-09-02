<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div>
      <input type="text" v-model="inputnum" />
      <div v-if="parseInt(inputnum)">
        <Counter
          v-on:count="count"
          v-for="n in parseInt(inputnum)"
          v-bind:key="n"
          v-bind:index="n"
          v-bind:sum="sum"
        />
        <p>sum is :{{sum}}</p>
      </div>
      <div v-else>
        <p>请输入正整数</p>
      </div>
    </div>
  </div>
</template>

<script>
import Counter from "./components/Counter.vue";

export default {
  name: "app",
  components: {
    Counter
  },
  data: function() {
    return {
      index: Number,
      inputnum: 0,
      sum: 0
    };
  },
  methods: {
    count: function(e) {
      this.sum = this.sum + e;
      // console.log(e);
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
  margin-top: 60px;
}
</style>
