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
      <div class="galleryContainer" v-if="placeHolderItems && placeHolderItems.length > 0">
          <div v-for="(item, index) in placeHolderItems" :key="index" class="galleryItem" >
              <div>
                <img :src="item.coverImage" style="display: block; width: 100%; height:250px;margin:auto; border-radius:25px;box-shadow: 10px 10px 30px rgba(0, 0, 0, 0.18); border-radius: 5px;"/>
                <p style="font-size: 1.5em;"> {{item.name}} <span style="float: right; font-size: 0.6em; margin-top: 10px;">$ {{item.price * 1.9}}</span></p>
                <p>By <span style="font-weight:600">{{item.nFTArtist}}</span> <span style="float: right;">{{item.price}} STX</span></p>
              </div>
          </div>
      </div>
      <button class="button">See More Collectables</button>
    </div>
    </section>
</template>

<script>

export default {
  name: 'homeMarket',
  data () {
    return {
      resultSet: [],
      loaded: false,
      placeHolderItems: []
    }
  },
  mounted () {
    this.generateData()
  },
  methods: {
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
}
.galleryItem{
  display: flex;
  margin: 0 auto;
  border-radius: 25px;
  background: rgba(129, 129, 129, 0.12) 0% 0% no-repeat padding-box;
  margin-bottom: 40px;
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
