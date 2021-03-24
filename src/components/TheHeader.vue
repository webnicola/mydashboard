<template>
  <div class="header">
      <p>{{ logo }}</p>
  </div>
</template>

<script>
export default {
  name: 'TheHeader',
  props: {
    logo: {
        type: String,
        default: 'LOGO'
    }
    
  }
}
</script>
<style scoped>
    p {
        color: red;
    }
</style>