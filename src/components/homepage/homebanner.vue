<template>
    <section class="bannerContainer">
        <img class="banner" src="https://res.cloudinary.com/risidio/image/upload/v1633609373/RisidioMarketplace/Group_-304_ofssmk.svg" alt="">
        <div v-if=" profile.loggedIn" class="if">
            <div class="loggedBanner">
                <div class="vueSlideContainer">
                  <vueper-slides
                  :infinite="true"
                  fixed-height="true"
                  class="no-shadow"
                  arrows-outside
                  :gap="3"
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
                            <div v-if="slide.id==1" class = "slideContainer">
                                <div class="slideImage">

                                </div>
                                <div class="slideText">
                                  <h2>Collection</h2>
                                  <p> lorem ipsum dolor sit amet<br>
                                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                                  Dolor animi natus officiis sint, neque nisi consequuntur,
                                  magni commodi est delectus facere! Eius modi animi dignissimos itaque
                                  facere iste neque architecto!</p>
                                  <button class="button"> See The Collection </button>
                                </div>
                            </div>
                            <div v-if="slide.id==2" class = "slideContainer">
                                <div class="slideImage">

                                </div>
                                <div class="slideText">
                                  <h2>Collection</h2>
                                  <p> lorem ipsum dolor sit amet<br>
                                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                                  Dolor animi natus officiis sint, neque nisi consequuntur,
                                  magni commodi est delectus facere! Eius modi animi dignissimos itaque
                                  facere iste neque architecto!</p>
                                  <button class="button"> See The Collection </button>
                                </div>
                            </div>
                            <div v-if="slide.id==3" class = "slideContainer">
                                <div class="slideImage">

                                </div>
                                <div class="slideText">
                                  <h2>Collection</h2>
                                  <p> lorem ipsum dolor sit amet<br>
                                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                                  Dolor animi natus officiis sint, neque nisi consequuntur,
                                  magni commodi est delectus facere! Eius modi animi dignissimos itaque
                                  facere iste neque architecto!</p>
                                  <button class="button"> See The Collection </button>
                                </div>
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
    </section>
</template>

<script>
import { APP_CONSTANTS } from '@/app-constants'
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'
const STX_CONTRACT_ADDRESS = process.env.VUE_APP_STACKS_CONTRACT_ADDRESS
const STX_CONTRACT_NAME = process.env.VUE_APP_STACKS_CONTRACT_NAME

export default {
  name: 'Homebanner',
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
.bannerContainer{
  min-height: 50vh;
}
h2{
  margin-bottom: 30px;
  letter-spacing: 1px;
  font-size: 40px;
  font-weight: 400;
}
.banner{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 60vh;
  object-fit: cover;
  z-index: -10;
  transform: rotate(180deg);
}
.vueperslide{
  background-color:rgba(255, 255, 255, 0.8);
  border-radius: 30px;
}

.vueperslides--fixed-height {
  height: 40vh;
  max-width: 90%;
  margin-left: auto;
  margin-right: auto;
}
.loggedBanner, .blurBackground{
  min-height: 40vh;
  position: relative;
  z-index: 2;
  max-width: 1500px;
  margin: 35px auto;
  border-radius: 30px;
}

.vueperslides__arrow .arrow{
  width: 35px;
  height: 35px;
}
.slideContainer{
  display: flex;
  flex-wrap: wrap;
  height:100%;
  padding: 40px;
  gap: 5%;
}
.slideContainer > *:nth-child(1){
  flex: 1 1 40%;
  min-width: 400px;
}
.slideContainer > *:nth-child(2){
  flex: 1 1 55%;
  min-width: 400px;
}
.button{
  margin-top: 20px;
  padding: 15px 30px;
  border-radius: 100px;
  border: none;
  background-color: rgb(0, 177, 201);
  font-size: 14px;
  font-weight:700;
  color: white;
}

</style>
