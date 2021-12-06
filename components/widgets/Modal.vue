<template>
  <div
    v-if="open"
    class="fixed w-full h-full top-0 left-0 flex items-center justify-center z-10"
  >
    <div
      class="absolute w-full h-full bg-gray-900 opacity-50"
      @click="close"
    ></div>

    <div class="absolute max-h-96" :class="maxWidth">
      <div class="container bg-white overflow-hidden md:rounded">
        <div
          class="px-4 py-4 leading-none flex justify-between items-center font-bold text-sm bg-gray-100 text-gray-800 border-b select-none"
        >
          <h3>{{ title }}</h3>
          <div
            class="text-2xl hover:text-gray-600 cursor-pointer"
            @click="close"
          >
            &#215;
          </div>
        </div>

        <div class="max-h-96 px-4 py-4 overflow-y-auto">
          <slot></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: '',
    },
    header: {
      type: String,
      required: false,
      default: '',
    },
    width: {
      type: String,
      default: 'full',
      validator: (value) => ['xs', 'sm', 'md', 'lg', 'full'].includes(value),
    },
  },
  data() {
    return {
      open: true,
    }
  },
  computed: {
    maxWidth() {
      switch (this.width) {
        case 'xs':
          return 'max-w-lg'
        case 'sm':
          return 'max-w-xl'
        case 'md':
          return 'max-w-2xl'
        case 'lg':
          return 'max-w-3xl'
        case 'full':
          return 'max-w-full'
        default:
          return 'max-w-full'
      }
    },
  },
  mounted() {
    const onEscape = (e) => {
      if (e.key === 'Esc' || e.key === 'Escape') {
        this.close()
      }
    }

    document.addEventListener('keydown', onEscape)

    this.$once('hook:beforeDestroy', () => {
      document.removeEventListener('keydown', onEscape)
    })
  },
  methods: {
    close() {
      this.open = false
      this.$emit('close')
    },
  },
}
</script>
