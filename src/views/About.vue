<template>
  <div>
    <MainNavbar/>

  </div>
</template>

<script>

import MainNavbar from '../components/layout/MainNavbar.vue'
import { APP_CONSTANTS } from '@/app-constants'

export default {
  name: 'Gallery',
  components: {
    MainNavbar
  },
  data () {
    return {

    }
  },
  methods: {
    changeModel (name) {
      this.currentModel = this.rootPath + name
    }
  },
  computed: {
    sectionDimensions () {
      const height = this.$store.getters[APP_CONSTANTS.KEY_SECTION_HEIGHT]
      return 'min-height: ' + height + 'px; width: auto;'
    },
    content () {
      const content = this.$store.getters[APP_CONSTANTS.KEY_CONTENT_ABOUT]
      return content
    }
  }
}
</script>

<style>

</style>
