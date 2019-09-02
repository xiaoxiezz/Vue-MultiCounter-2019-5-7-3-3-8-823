<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div>
      <input type="text" v-model="num" />
      <div v-if="parseInt(num)">
        <Counter v-for="n in parseInt(num)" v-bind:key="n" v-bind:index="n" />
      </div>
      <div v-else>
        <p>请输入正整数</p>
      </div>
    </div>

    <p>sum is :{{sum}}</p>
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
      num: 0
    };
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
