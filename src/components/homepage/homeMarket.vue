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

export default {
  name: 'homeMarket',
  data () {
    return {
      resultSet: [],
      loaded: false,
      placeHolderItems: [{
        name: 'item1',
        coverImage: 'https://res.cloudinary.com/risidio/image/upload/v1634828295/RisidioMarketplace/Screenshot_2021-10-21_at_15.57.57_q7chjf.png',
        nFTArtist: 'unknown',
        price: 50
      }
      ]
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
