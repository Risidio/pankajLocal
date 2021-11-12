<template>
    <section class="homeMarket">
    <div>
      <b-nav class="galleryNav" >
        <div class="galleryNavContainer" >
          <b-nav-item class="galleryNavItem">Discover</b-nav-item>
          <b-nav-item class="galleryNavItem">Popular</b-nav-item>
          <b-nav-item class="galleryNavItem">Collections</b-nav-item>
          <b-nav-item class="galleryNavItem">Your NFT's</b-nav-item>
        </div>
      </b-nav>
    </div>
    <div class="homeMarketItems">

    </div>
    </section>
</template>

<script>
import { APP_CONSTANTS } from '@/app-constants'
const STX_CONTRACT_ADDRESS = process.env.VUE_APP_STACKS_CONTRACT_ADDRESS
const STX_CONTRACT_NAME = process.env.VUE_APP_STACKS_CONTRACT_NAME

export default {
  name: 'homeMarket',
  data () {
    return {
      resultSet: [],
      loaded: false
    }
  },
  mounted () {
    this.findAssets()
  },
  methods: {
    findAssets () {
      this.$store.dispatch('rpaySearchStore/findByProjectId', STX_CONTRACT_ADDRESS + '.' + STX_CONTRACT_NAME).then((results) => {
        this.resultSet = results.filter(result => result.attributes.artworkFile.fileUrl !== null)
      })
      console.log(this.resultSet)
    }
  },
  computed: {
    content () {
      const content = this.$store.getters[APP_CONSTANTS.KEY_CONTENT_MARKET]
      return content
    }
  }
}

</script>

<style lang="scss" scoped>
.homeMarket{
  min-height: 80vh;
}
.galleryNav{
  margin: auto;
  margin-bottom: 70px;
  width: 100%;
  justify-items: center;
  align-items: center;
  border-bottom: solid rgba(128, 128, 128, 0.112) 1px;
}
.galleryNavContainer{
  margin: auto;
  margin-bottom: -1px;
  max-width: 1200px;
  display: flex;
  flex-direction: row;
}
.galleryNavItem{
  font-size: 18px;

  max-width: 500px;
  padding: 5px;
  margin: auto;
  border: solid rgba(255, 255, 255, 0)  2px;
}
.galleryNavItem:hover{
  border-bottom: 2px solid #50B1B5;
}
</style>
