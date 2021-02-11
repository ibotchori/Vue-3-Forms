<template>
  <label v-if="label">{{label}}</label> 
  <select 
  class="field" 
  :value="modelValue"
  v-bind="{
      ...$attrs,
      onChange: ($event) => { $emit('update:modelValue', $event.target.value) }
    }"
  >
    <option
      v-for="option in options"
      :value="option"
      :key="option"
      :selected="option === modelValue"
    >{{ option }}</option>
  </select>
</template>

<script>
export default {
  // Props for template
  props: {
    label: {
      type: String,
      default: ''
    },
    // Value for select
    modelValue: {
      type: [String, Number],
      default: ''
    },
    // Array for select options
    options: {
      type: Array,
      required: true
    }
  }
}
</script>
