<template>
    <section class="homepage">
      <HomeBanner/>
      <HomeMarket/>
      <HomeInfo/>
      <HomeSeeAlso/>
    </section>
</template>

<script>
import HomeBanner from '@/components/homepage/homebanner'
import HomeMarket from '@/components/homepage/homeMarket'
import HomeInfo from '@/components/homepage/homeInfo'
import HomeSeeAlso from '@/components/homepage/homeSeeAlso'

export default {
  name: 'Homepage',
  components: {
    HomeBanner,
    HomeMarket,
    HomeInfo,
    HomeSeeAlso
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

<style lang="scss" scoped>

</style>
