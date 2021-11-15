<template>
  <p aria-live="assertive" class="errorMessage">
    <slot />
  </p>
</template>

<script>
export default {}
</script>
<style scoped>
.errorMessage {
  color: red;
  font-size: 75%;
}
input + p.errorMessage {
  margin-bottom: 24px;
}
</style>
