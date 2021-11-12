<template>
    <section class="homepage">
      <HomeBanner/>
      <HomeMarket/>
      <HomeInfo/>
    </section>
</template>

<script>
import HomeBanner from '@/components/homepage/homebanner'
import HomeMarket from '@/components/homepage/homeMarket'
import HomeInfo from '@/components/homepage/homeInfo.vue'

export default {
  name: 'Homepage',
  components: {
    HomeBanner,
    HomeMarket,
    HomeInfo
  },
  data () {
    return {
    }
  },
  mounted () {
    // this.findAssets()
  },
  methods: {
  },
  computed: {
  }
}
</script>

<style>
</style>
