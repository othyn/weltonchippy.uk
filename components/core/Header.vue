<template>
  <nav :class="headerClassList" class="fixed w-full z-30 top-0">
    <div
      class="w-full container mx-auto flex flex-wrap items-center justify-between mt-0 py-2"
    >
      <div class="pl-4 flex items-center">
        <ContentLogo :is-stickable="true" :is-sticky="isSticky" />
      </div>
      <div class="block lg:hidden pr-4">
        <button
          class="flex items-center p-1 text-primary hover:text-gray-900"
          @click.prevent.stop="onToggleClick"
        >
          <svg
            class="fill-current h-6 w-6"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <title>Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
          </svg>
        </button>
      </div>

      <div
        :class="navContentClassList"
        class="w-full flex-grow lg:flex lg:items-center lg:w-auto lg:block mt-2 lg:mt-0 bg-white lg:bg-transparent p-4 lg:p-0 z-20"
      >
        <ul class="list-reset lg:flex justify-end flex-1 items-center">
          <li class="mr-3">
            <a
              class="inline-block font-bold no-underline hover:text-gray-800 hover:underline py-2 px-4"
              href="#Opening Times"
              >Opening Times</a
            >
          </li>
          <li class="mr-3">
            <a
              class="inline-block font-bold no-underline hover:text-gray-800 hover:underline py-2 px-4"
              href="#How To Find Us"
              >How To Find Us</a
            >
          </li>
          <li class="mr-3">
            <a
              class="inline-block font-bold no-underline hover:text-gray-800 hover:underline py-2 px-4"
              href="#Current Offer"
              >Current Offer</a
            >
          </li>
          <li class="mr-3">
            <a
              class="inline-block font-bold no-underline hover:text-gray-800 hover:underline py-2 px-4"
              href="#FAQ's"
              >FAQ's</a
            >
          </li>
        </ul>
        <!-- <a
          :class="navActionClassList"
          class="mx-auto lg:mx-0 hover:underline font-bold rounded-full mt-3 lg:mt-0 py-3 px-6 shadow opacity-75"
          href="https://order.weltonchippy.uk"
        >
          Order
        </a> -->
      </div>
    </div>
    <hr class="border-b border-gray-100 opacity-25 my-0 py-0" />
  </nav>
</template>

<script>
export default {
  data() {
    return {
      scrollY: 0,
      isOpen: false,
    }
  },
  computed: {
    isSticky() {
      return this.scrollY > 10
    },
    headerClassList() {
      return this.isSticky ? 'bg-white shadow' : ''
    },
    navActionClassList() {
      return this.isSticky ? 'gradient text-white' : 'bg-white text-gray-800'
    },
    navContentClassList() {
      let classList = this.isSticky
        ? 'bg-white text-primary'
        : 'bg-gray-100 text-white'

      if (!this.isOpen) {
        classList += ' hidden'
      } else if (!this.isSticky) {
        classList += ' text-primary'
      }

      return classList
    },
  },
  mounted() {
    this.scrollY = window.scrollY
    document.addEventListener('click', this.onClick)
    document.addEventListener('scroll', this.onScroll)
  },
  beforeDestroy() {
    document.removeEventListener('click', this.onClick, true)
    document.removeEventListener('scroll', this.onScroll, true)
  },
  methods: {
    onClick() {
      this.isOpen = false
    },
    onScroll() {
      this.scrollY = window.scrollY
    },
    onToggleClick() {
      this.isOpen = !this.isOpen
    },
  },
}
</script>
