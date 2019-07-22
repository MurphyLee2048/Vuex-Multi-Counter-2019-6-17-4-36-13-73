<template>
  <div>
    <button v-on:click="decrease">-</button>
    <span>{{count}}</span>
    <button @click="increase">+</button>
  </div>
</template>

<script>
  export default {
    name: "Counter",
    data() {
      return {
        count: 0
      }
    },
    methods: {
      increase() {
        this.count++;
        this.$store.state.sum++;
      },
      decrease() {
        this.count--;
        this.$store.state.sum--;
      },
    },
    beforeDestroy: function () {
      this.$emit('reSum',  this.$store.state.sum - this.count);
    }
  }
</script>

<style scoped>

</style>
