<template>
  <section :class="bgClass" class="py-12 px-4" :id="title">
    <div class="container max-w-5xl mx-auto m-8">
      <h1
        class="w-full my-2 text-5xl font-bold leading-tight text-center text-gray-800"
      >
        {{ title }}
      </h1>

      <div class="w-full mb-16">
        <div
          class="h-1 mx-auto gradient w-64 opacity-25 my-0 py-0 rounded-t"
        ></div>
      </div>

      <slot />
    </div>
  </section>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: false,
    },
    secondary: {
      type: Boolean,
      default: false,
    },
    noBorder: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    bgClass() {
      return (
        (this.secondary ? 'bg-gray-50' : 'bg-white') +
        ' ' +
        (this.noBorder ? '' : 'border-b')
      )
    },
  },
}
</script>
