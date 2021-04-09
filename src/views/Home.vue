<template>
  <div class="home">
    <h1 ref="titolo">{{ text }}</h1>
    <h2 ref="subtitolo">{{ wind_gb }}/100</h2>
    <items className="box2">
      <item v-for="item in items" :key="item.message">
        {{ item.message }}
      </item>
    </items>  
  </div>
</template>

<script>
// @ is an alias to /src
// https://vuejs.org/v2/guide/single-file-components.html
import Items from '@/components/Items.vue'
import Item from '@/components/Item.vue'
export default {
  name: 'Home',
  components: {
    Items,
    Item,
  },
  computed: {
    wind_gb: function () {
      /**
       * commento documentale JSDoc
       * {@link https://jsdoc.app}
       */
      if (this.wind) {
        console.log(this.wind.lines[0].options[2])

        return this.wind.lines[0].options[2].dataInsight.available;
      } else {
        return ''
      }
    },
  },
  data () {
    return {
      text : 'Sono una variabile data',
      wind: null,
      items: [
        { message: 'Foo' },
        { message: 'Bar' }
      ]
    }
  },
  methods: {
    init () {
      console.log('Method init')
      const VUE = this
      fetch(`data/wind.json`)
        .then(function(response){
          return response.json()
        })
        .then(function(payload){
          console.log(payload)
          VUE.wind = payload
        })
    }
  },
  created() {
    console.log('Home component created')
    this.text = "Essendo variabile cambio 1"
    this.init()
    console.log('VUE', this)

  },
  mounted() {
    const VUE = this
    console.log('Home component mounted')
    VUE.text = "Essendo variabile cambio 2"
    console.log(VUE.$refs)
  }

}
</script>
<style scoped>

</style>
