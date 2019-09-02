<template>
  <div class="counter">
    
    <button v-on:click="add">+</button>
    <span>{{number}}</span>
    <button v-on:click="reduce">-</button>
  </div>
</template>

<script>
export default {
  name: "Counter",
  data() {
    return {
      number: 0
    };
  },
  methods: {
    beforeCreate: function() {
      window.console.log("beforeCreate");
    },
    created: function() {
      window.console.log("created");
    },
    beforeMount: function() {
       window.console.log("created");
    },
    mounted: function() {
       window.console.log("mounted");
    },
    beforeUpdate: function() {
       window.console.log("beforeUpdate");
    },
    updated: function() {
       window.console.log("updated");
    },
    beforeDestroy() {
       window.console.log("beforeDestory");
    },
    destroyed: function() {
       window.console.log("destoryed");
    },
    add: function() {
      this.number++;
    },
    reduce: function() {
      this.number--;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
