<template>
  <div class="home">
    <h1>{{ text }}</h1>
    <h2>{{ wind_gb }}/100</h2>
    <button type="button" class="btn btn-primary">Primary</button>
  </div>
</template>

<script>
// @ is an alias to /src
// https://vuejs.org/v2/guide/single-file-components.html
export default {
  name: 'Home',
  components: {},
  computed: {
    wind_gb: function () {
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
      wind: null
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

  },
  mounted() {
    const VUE = this
    console.log('Home component mounted')
    VUE.text = "Essendo variabile cambio 2"
  }

}
</script>
<style scoped>

</style>
