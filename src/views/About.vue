<template>
  <div class="about">
    <the-header logo="About logo" />
    <h1>This is an about page</h1>
    <img src="@/assets/logo.png">
    <icon-base>
      <icon-write />
    </icon-base>
    <icon-base>
      <icon-ruler />
    </icon-base>
    <icon-base width="30" height="30" iconColor="lime">
      <icon-ruler />
    </icon-base>
    <items>
      <item v-for="item in items" :key="item.message">
        {{ item.message }}
      </item>
    </items>  

  </div>
</template>
<script>
// @ is an alias to /src
import TheHeader from '@/components/TheHeader.vue'
import IconBase from '@/components/icon/IconBase.vue'
import IconWrite from '@/components/icon/IconWrite.vue'
import IconRuler from '@/components/icon/IconRuler.vue'
import Items from '@/components/Items.vue'
import Item from '@/components/Item.vue'

export default {
  name: 'About',
  components: {
    TheHeader,
    IconBase,
    IconWrite,
    IconRuler,
    Items,
    Item,
  },
  data: function () {
    return {
      items: [
        { message: 'Foo' },
        { message: 'Bar' }
      ]
    }
  }
}
</script>
