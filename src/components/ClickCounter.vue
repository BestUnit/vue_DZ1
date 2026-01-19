<template>
  <div class="counter">
    <h2 :style="counterTitleColor">{{ title }}</h2>
    <div>Count: {{ count }}</div>
    <div>DoubleCount: {{ doubleCount }}</div>
  </div>
  <button @:click="count++">increment++</button>
  <button @:click="decrement">Decrement--</button>
  <button @:click="reset">Reset</button>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      count: 0,
    }
  },
  props: {
    title: {
      type: String,
      default: 'Default counter title',
    },
  },
  emits: ['decrement'],
  computed: {
    doubleCount() {
      return 2 * this.count
    },
    counterTitleColor() {
      return { color: this.count > 5 ? 'red' : 'black' }
    },
  },
  methods: {
    reset() {
      this.count = 0
    },
    showDecrement() {
      console.log('decrement')
    },
    decrement() {
      this.count--
      this.$emit('decrement', this.count)
    },
  },
  watch: {
    count: {
      handler(newValue, oldValue) {
        console.log('newValue', newValue)
        console.log('oldValue', oldValue)
        // if (newValue === 0) alert('Значение равно 0')
      },
      immediate: true,
      deep: true,
    },
  },
})
</script>

<style scoped>
button {
  padding: 5px 10px;
  border: none;
  background-color: aqua;
  border-radius: 5px;
  margin-right: 5px;
}
</style>
