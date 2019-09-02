<template>
  <div class="counter"> 
    <div>
    <span>{{index}}:</span>
    <button v-on:click="add">+</button>
    <span>{{number}}</span>
    <button v-on:click="reduce">-</button>
    </div>
    
  </div>
</template>

<script>
export default {
  name: "Counter",
  props:{
    index: Number,
  },
  data() {
    return {
      number: this.index,
    };
  },
  created() {
    this.$emit('count',this.index)
  },
  destroyed() {
    this.$emit('count',-this.index)
  },
  methods: {
    add: function() {
      this.number++;
      this.$emit('count',1)
    },
    reduce: function() {
      this.number--;
      this.$emit('count',-1)
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
