<template>
    <section class='seeAlso'>
        <h2> See Also</h2>
        <div class='seeAlsoContainer'>
        <vueper-slides
            class="no-shadow"
            :visible-slides="4"
            :gap="3"
            :slide-ratio="1 / 4"
            :dragging-distance="200"
            :breakpoints="breakpoints">
            <template #arrow-left>
                <img src="https://res.cloudinary.com/risidio/image/upload/v1633609469/RisidioMarketplace/Icon_ionic-md-arrow-dropleft-circle_v37pyt.svg" alt="wallet" class="arrow"/>
            </template>
            <template #arrow-right>
                <img src="https://res.cloudinary.com/risidio/image/upload/v1633609474/RisidioMarketplace/Icon_ionic-md-arrow-dropleft-circle-1_oclpff.svg" alt="wallet" class="arrow"/>
            </template>
            <vueper-slide v-for="i in 10" :key="i" :title="i" />
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
  data: () => ({
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
  })
}
</script>

<style lang="scss" scoped>
.seeAlso{
    min-height: 60vh;
    margin: 0 50px;
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
.vueperslide{
  background-color:rgba(226, 226, 226, 0.8);
  border-radius: 30px;
}
.vueperslides__arrow .arrow{
  width: 23px;
  height: 23px;
}

</style>
