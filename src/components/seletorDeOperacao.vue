<template>
  <select :value="operation" @change="updateOperation($event.target.value)">
    <option value="add">+</option>
    <option value="subtract">-</option>
    <option value="multiply">*</option>
    <option value="divide">/</option>
  </select>
</template>

<script>
export default {
  props: ['operation'],
  methods: {
    updateOperation(value) {
      this.$emit('update:operation', value);
    }
  }
}
</script>