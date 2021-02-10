<template>
  <label v-if="label">{{ label }}</label>
  <input
    v-bind="$attrs"
    :value="modelValue"
    :placeholder="label"
    @input="$emit('update:modelValue', $event.target.value)"
    class='field'
  />
</template>

<script>
export default {
  // Props for template
  props: {
    label: {
      type: String,
      defaul: ''
    },
    // Value for input
    modelValue: {
      type: [String, Number], // Hello or 30
      default: ''
    }
  }
}
</script>
