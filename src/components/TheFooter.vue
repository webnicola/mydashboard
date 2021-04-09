<template>
  <div class="footer">
      <p>{{ logo }}</p>
      <p>Copy...</p>
  </div>
</template>

<script>
export default {
  name: 'TheFooter',
  props: {
    logo: {
        type: String,
        default: ''
    }
    
  }
}
</script>
<style scoped>
  
</style>