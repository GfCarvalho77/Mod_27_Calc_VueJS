<template>
  <div>
    <input 
      type="number" 
      :value="num1" 
      @input="updateNum1($event.target.value)" 
      placeholder="Número 1" 
    />
    <input 
      type="number" 
      :value="num2" 
      @input="updateNum2($event.target.value)" 
      placeholder="Número 2" 
    />
  </div>
</template>

<script>
export default {
  props: ['num1', 'num2'],
  methods: {
    updateNum1(value) {
      this.$emit('update:num1', parseFloat(value));
    },
    updateNum2(value) {
      this.$emit('update:num2', parseFloat(value));
    }
  }
}
</script>