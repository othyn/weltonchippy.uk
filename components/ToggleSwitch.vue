<template>
  <div>
    <div
      class="relative inline-block w-10 mr-2 align-middle select-none transition duration-200 ease-in mt-"
    >
      <input
        :id="name"
        v-model="checked"
        type="checkbox"
        :name="name"
        class="toggle-checkbox absolute block w-6 h-6 rounded-full bg-white border-4 appearance-none cursor-pointer"
      />
      <label
        :for="name"
        class="toggle-label block overflow-hidden h-6 rounded-full cursor-pointer"
      ></label>
    </div>
    <label v-if="label" :for="name" class="text-md text-white">{{
      label
    }}</label>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    value: {
      type: Boolean,
      default: false,
    },
    label: {
      type: String,
      required: false,
      default: 'Set a label',
    },
  },
  data() {
    return {
      checked: this.value,
    }
  },
  watch: {
    checked(newValue) {
      this.$emit('input', newValue)
    },
  },
}
</script>
<style lang="scss">
/* CHECKBOX TOGGLE SWITCH */
/* @apply rules for documentation, these do not work as inline style */
.toggle-checkbox:checked {
  @apply right-0 border-gray-500;
  right: 0;
}
.toggle-checkbox {
  right: calc(100% - theme('width.6'));
  transition: right;
  .mode-dark & {
    @apply border-gray-600;
  }
  .mode-dark &:checked {
    @apply border-gray-700;
  }
  &:focus {
    outline: none;
    box-shadow: 0 0 0 1px theme('colors.blue.300');
  }
}
.toggle-checkbox,
.toggle-label {
  @apply duration-100 ease-out;
}
.toggle-label {
  @apply bg-gray-300;
  .mode-dark & {
    @apply bg-gray-600;
  }
}
.toggle-checkbox:focus + .toggle-label {
}
.toggle-checkbox:checked + .toggle-label {
  @apply bg-gray-500;
  .mode-dark & {
    @apply bg-gray-700;
  }
}
</style>
