<template>
  <div class="about">
    <the-header logo="About logo" />
    <h1>This is an about page</h1>
  </div>
</template>
<script>
// @ is an alias to /src
import TheHeader from '@/components/TheHeader.vue'

export default {
  name: 'About',
  components: {
    TheHeader
  }
}
</script>
