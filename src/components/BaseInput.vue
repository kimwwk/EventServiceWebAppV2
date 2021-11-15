<template>
  <div>
    <label v-if="label">{{ label }}</label>
    <input
      class="field"
      :value="modelValue"
      @input="updateValue"
      v-bind="$attrs"
    />
    <BaseErrorMessage v-if="error">
      {{ error }}
    </BaseErrorMessage>
  </div>
</template>

<script>
export default {
  // inheritAttrs: false,
  props: {
    label: {
      type: String,
      default: ''
    },
    error: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number], // it could be a string or a number
      default: ''
    }
  },
  methods: {
    updateValue(event) {
      this.$emit('update:modelValue', event.target.value)
    }
  }
}
</script>
<style scoped>
.field {
  margin-bottom: 24px;
}
</style>
