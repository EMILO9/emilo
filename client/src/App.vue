<template>
  <div id="app">
    <div class="scrollToTop" v-if="!hide" @click="scrollToTop">Go back to top!</div>
    <div class="Header"></div>
    <div class="Content" @scroll="checkScroll()">
      <transition name="fade">
      <router-view />
      </transition>
    </div>
    <div class="Footer"></div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      hide: true
    }
  },
  methods: {
    checkScroll() {
      let element = document.querySelector('.Content')
      if (element.scrollTop === 0) this.hide = true
      else this.hide = false
    },
    scrollToTop () {
      let element = document.querySelector('.Content')
      element.scrollTop = 0;
    }
  }
}
</script>

<style>

</style>
