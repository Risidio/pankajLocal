<template>
    <div>
        <img class="banner" src="https://res.cloudinary.com/risidio/image/upload/v1633609373/RisidioMarketplace/Group_-304_ofssmk.svg" alt="">
        <div v-if=" profile.loggedIn">
            <div class="loggedBanner">
                <div class="vueSlideContainer">
                  <vueper-slides
                  :infinite="true"
                  fixed-height="true"
                  class="no-shadow"
                  arrows-outside
                  autoplay
                  >
                    <template #arrow-left>
                      <img src="https://res.cloudinary.com/risidio/image/upload/v1633609469/RisidioMarketplace/Icon_ionic-md-arrow-dropleft-circle_v37pyt.svg" alt="wallet" class="arrow"/>
                    </template>
                    <template #arrow-right>
                      <img src="https://res.cloudinary.com/risidio/image/upload/v1633609474/RisidioMarketplace/Icon_ionic-md-arrow-dropleft-circle-1_oclpff.svg" alt="wallet" class="arrow"/>
                    </template>
                    <vueper-slide
                    v-for="(slide) in slide"
                    :key="slide.id"
                    :title="slide.title">
                        <template #content>
                            <div v-if="slide.id==1" class = "container">
                                <h1>Lorem ipsum dolor, sit amet </h1>
                            </div>
                            <div v-if="slide.id==2" class = "container">
                            </div>
                            <div v-if="slide.id==3" class = "container">
                            </div>
                        </template>
                    </vueper-slide>
                  </vueper-slides>
                </div>
            </div>
        </div>
        <div v-else>
            <div class="container section1">
                <div class="market_introduction_text">
                    <p class="market_intro_Ex">Explore the New Era of Digital Art</p>
                    <h1 class="market_intro_h1"> Risidio Marketplace</h1>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { APP_CONSTANTS } from '@/app-constants'
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'
const STX_CONTRACT_ADDRESS = process.env.VUE_APP_STACKS_CONTRACT_ADDRESS
const STX_CONTRACT_NAME = process.env.VUE_APP_STACKS_CONTRACT_NAME

export default {
  name: 'MarketPlace',
  components: {
    VueperSlides,
    VueperSlide
  },
  data: () => ({
    slide: [
      {
        id: '1',
        text: 'Upload Your Item'
      },
      {
        id: '2',
        text: 'Mint the Bitcoin'
      },
      {
        id: '3',
        text: 'Set Your Royalties'
      }
    ],
    return: {
      resultSet: [],
      loaded: false
    }
  }),
  mounted () {
    this.findAssets()
  },
  methods: {
    findAssets () {
      this.$store.dispatch('rpaySearchStore/findByProjectId', STX_CONTRACT_ADDRESS + '.' + STX_CONTRACT_NAME).then((results) => {
        this.resultSet = results.filter(result => result.attributes.artworkFile.fileUrl !== null)
      })
    }
  },
  computed: {
    content () {
      const content = this.$store.getters[APP_CONSTANTS.KEY_CONTENT_MARKET]
      return content
    },
    profile () {
      const profile = this.$store.getters[APP_CONSTANTS.KEY_PROFILE]
      return profile
    }
  }
}
</script>

<style scoped>
.banner{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 55vh;
  object-fit: cover;
  z-index: -10;
  transform: rotate(180deg);
}
.vueperslide {
  background-color:rgba(255, 255, 255, 0.8);
  border-radius: 30px;
}
.vueperslides--fixed-height {
  height: 40vh;
  max-width: 100%;
}
.loggedBanner{
  max-width: 1500px;
  margin: 10px auto;
}
.vueperslides__arrow .arrow{
  width: 35px;
  height: 35px;
}
 /* @media only screen and (max-width: 770px)  {
  .vueperslides--fixed-height {height: 80vh;}
} */
/*
@media only screen and (max-width: 500px)  {
  .vueperslides--fixed-height {height: 120vh;}
} */
</style>
