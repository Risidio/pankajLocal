<template>
    <section class='seeAlso'>
        <h2> See Also</h2>
        <div class='seeAlsoContainer'>
        <vueper-slides
            class="no-shadow"
            :visible-slides="4"
            :gap="3"
            :slide-ratio="1 / 4"
            :dragging-distance="100"
            :breakpoints="breakpoints">
            <template #arrow-left>
                <img src="https://res.cloudinary.com/risidio/image/upload/v1633609469/RisidioMarketplace/Icon_ionic-md-arrow-dropleft-circle_v37pyt.svg" alt="wallet" class="arrow"/>
            </template>
            <template #arrow-right>
                <img src="https://res.cloudinary.com/risidio/image/upload/v1633609474/RisidioMarketplace/Icon_ionic-md-arrow-dropleft-circle-1_oclpff.svg" alt="wallet" class="arrow"/>
            </template>
            <vueper-slide v-for="(item, index) in placeHolderItems" :key="index" class="galleryItem" >
              <template #content>
                <div class="galleryContainer">
                  <img :src="item.coverImage" style="display: block; width: 100%; height:250px; margin:auto; border-radius:25px;box-shadow: 10px 10px 30px rgba(0, 0, 0, 0.18); border-radius: 5px;"/>
                  <p style="font-size: 1.5em;"> {{item.name}} <span style="float: right; font-size: 0.6em; margin-top: 10px;">$ {{item.price * 1.9}}</span></p>
                  <p>By <span style="font-weight:600">{{item.nFTArtist}}</span> <span style="float: right;">{{item.price}} STX</span></p>
                </div>
              </template>
            </vueper-slide>
        </vueper-slides>
        </div>
    </section>
</template>

<script>
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'

export default {
  name: 'homeSeeAlso',
  components: {
    VueperSlides,
    VueperSlide
  },
  data () {
    return {
      placeHolderItems: [],
      breakpoints: {
        1400: {
          visibleSlides: 3,
          slideRatio: 1 / 2.5
        },
        900: {
          visibleSlides: 2,
          slideRatio: 1 / 1.5
        },
        600: {
          visibleSlides: 1.1,
          slideRatio: 1,
          arrows: false
        }
      }
    }
  },
  mounted () {
    this.generateData()
    console.log(this.placeHolderItems)
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
      for (let i = 0; i < 10; ++i) {
        this.placeHolderItems.push(array)
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.seeAlso{
    min-height: 60vh;
    margin: 0 3%;
    h2{
        font-size: 40px;
        margin: 100px 20px 50px 20px;
        text-align: center;
    }
}
.seeAlsoContainer{
  max-width: 1600px;
  margin: auto;
}
.vueperslides{
  margin: 0 auto;
  max-width: 1500px;
}
.vueperslide{
  background-color:rgba(226, 226, 226, 0.8);
  min-height: 375px;
  border-radius: 30px;
}
.vueperslides__arrow .arrow{
  width: 23px;
  height: 23px;
}
.galleryItem{
  display: block;
  padding: 25px;
  margin: 0 auto;
  border-radius: 25px;
  background: rgba(129, 129, 129, 0.12) 0% 0% no-repeat padding-box;
  margin-bottom: 40px;
}
</style>
