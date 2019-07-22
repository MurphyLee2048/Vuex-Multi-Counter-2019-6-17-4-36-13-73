<template>
  <div>
    <input type="number" v-model.number="number" placeholder="CounterNumber">
    <Counter v-for="n in number" v-on:reSum="reSum"></Counter>
    <button>Sum: {{sum}}</button>
  </div>
</template>

<script>
  import Counter from "./Counter.vue"
  export default {
    name: "CounterGroup",
    data() {
      return {
        number: 1,
      }
    },
    computed: {
      sum() {
        return this.$store.state.sum;
      }
    },
    components: {Counter},
    methods: {
      reSum(sum) {
        this.$store.state.sum = sum;
      }
    },
  }
</script>

<style scoped>
</style>
