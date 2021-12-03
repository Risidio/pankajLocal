<template>
    <section class="homeMarket">
    <div>
      <b-nav class="galleryNav" >
        <div class="galleryNavContainer" >
          <b-nav-item class="galleryNavItem" @click="tabChange('Discover')">Discover</b-nav-item>
          <!-- <b-nav-item class="galleryNavItem" @click="tabChange('NFT')">Popular</b-nav-item> -->
          <b-nav-item class="galleryNavItem" @click="tabChange('Collections')">Collections</b-nav-item>
          <b-nav-item class="galleryNavItem" @click="tabChange('Your NFT')">Your NFT's</b-nav-item>
        </div>
      </b-nav>
    </div>
    <div class="homeMarketItems">
      <div class="galleryContainer" v-if="gaiaAssets && gaiaAssets.length > 0">
          <div  v-for="(item, index) in gaiaAssets" :key="index" class="galleryItem" >
              <div class="NFTbackgroundColour">
                 <MediaItemGeneral :classes="'nftGeneralView'" v-on="$listeners" :options="videoOptions" :mediaItem="item.attributes.artworkFile"/>
                <!-- <img :src="item.attributes.artworkFile" style="display: block; width: 100%; height:250px;margin:auto; border-radius:25px;box-shadow: 10px 10px 30px rgba(0, 0, 0, 0.18); border-radius: 5px;"/> -->
                 <p style="font-size: 1.5em;"> {{item.name}} <span style="float: right; font-size: 0.6em; margin-top: 10px;">$ {{item.price * 1.9}}</span></p>
                <p>By <span style="font-weight:600">{{item.artist}}</span> <span style="float: right;">{{item.price}} STX</span></p>
              </div>
          </div>
      </div>
            <button class="button"><router-link to="/gallery">See More Collectables</router-link></button>
    </div>
    </section>
</template>

<script>
import { APP_CONSTANTS } from '@/app-constants'
import MediaItemGeneral from '@/views/marketplace/components/media/MediaItemGeneral'
export default {
  name: 'Gallery',
  components: {
    MediaItemGeneral
  },
  data () {
    return {
      resultSet: [],
      loaded: false,
      placeHolderItems: []
    }
  },
  mounted () {
    this.generateData()
    this.findAssets()
  },
  methods: {
    tabChange (tab) {
      this.tab = tab
      console.log(this.tab)
    },
    showCollections () {
      const collection = document.getElementsByClassName('collectionsMenu')[0]
      const arrow = document.getElementsByClassName('arrow1')[0]
      collection.classList.toggle('active')
      arrow.classList.toggle('active')
    },
    showCategories () {
      const categories = document.getElementsByClassName('galleryCategories')[0]
      const arrow = document.getElementsByClassName('arrow2')[0]
      categories.classList.toggle('active')
      arrow.classList.toggle('active')
    },
    findAssets () {
      this.$store.dispatch('rpayStacksContractStore/fetchContractDataFirstEditions').then(() => {
        this.loaded = true
      })
    },
    generateData () {
      const array = {
        name: 'item1',
        coverImage: 'https://res.cloudinary.com/risidio/image/upload/v1634828295/RisidioMarketplace/Screenshot_2021-10-21_at_15.57.57_q7chjf.png',
        nFTArtist: 'unknown',
        price: 13,
        type: 'image'
      }
      for (let i = 0; i < 20; ++i) {
        this.placeHolderItems.push(array)
      }
    }
  },
  computed: {
    gaiaAssets () {
      const assets = this.$store.getters[APP_CONSTANTS.KEY_GAIA_ASSETS]
      return (assets) ? assets.reverse() : []
    }
  }
}

</script>

<style lang="scss" scoped>
p{padding:0; margin:0;}
.homeMarket{
  width: 100%;
  min-height: 80vh;
  margin-bottom: 10vh;
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
.galleryContainer{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  margin: auto;
}
.galleryItem{
  display: flex;
  margin: 4rem;
  border-radius: 25px;
  padding: 4rem;
    margin: auto;
}
.galleryItem > *{
  flex: 1 1 300px;
  padding: 30px;
  min-width: 300px;
  max-height: 400px;
}
.button{
  display:block;
  margin: 30px auto;
  padding: 15px 30px;
  border-radius: 100px;
  border: none;
  font-size: 14px;
  font-weight:500;
  background:#50B1B5;
  color: white;
}
</style>
