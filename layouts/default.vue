<template>
  <div class="leading-normal tracking-normal text-white gradient">
    <site-header />
    <nuxt />
    <site-footer :dark-mode="darkMode" @toggle-dark-mode="darkMode = $event" />
  </div>
</template>

<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    'site-header': Header,
    'site-footer': Footer,
  },
  data() {
    return {
      darkMode: false,
    }
  },
  watch: {
    darkMode(value) {
      document.querySelector('body').classList.toggle('mode-dark', value)
      localStorage.setItem('weltonChippyDarkMode', value)
    },
  },
  mounted() {
    this.darkMode = localStorage.getItem('weltonChippyDarkMode') === 'true'
  },
}
</script>
