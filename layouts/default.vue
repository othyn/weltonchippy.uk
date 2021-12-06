<template>
  <div class="leading-normal tracking-normal text-white gradient">
    <CoreHeader />
    <nuxt />
    <CoreFooter :dark-mode="darkMode" @toggle-dark-mode="darkMode = $event" />
  </div>
</template>

<script>
export default {
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
