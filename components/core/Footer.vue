<template>
  <div>
    <img src="~assets/img/wave/footer.svg?inline" alt="footer wave" />

    <section class="container mx-auto text-center py-6 text-white">
      <p class="w-full mt-4 text-md font-medium leading-tight">
        <span class="font-bold">PJ Interests Ltd</span><br />VAT Number
        <span class="font-bold">679 2307 07</span><br />Registered in England &
        Wales <span class="font-bold">3250662</span><br />Registered Office
        <span class="font-bold">8 Beckhall, Welton, Lincoln, LN2 3LJ</span>
      </p>

      <div class="w-full my-4 text-center">
        <ContentTermsAndConditions />
      </div>

      <div class="w-full my-8">
        <div
          class="h-1 mx-auto bg-white w-1/6 opacity-25 my-0 py-0 rounded-t"
        ></div>
      </div>

      <div class="">
        <p
          class="w-full mt-4 text-md font-medium leading-tight text-white inline"
        >
          <a
            class="font-bold hover:underline"
            href="https://github.com/othyn/weltonchippy.uk/releases"
            >v1.0</a
          >
          <span class="mx-4">|</span>
        </p>
        <WidgetsToggleSwitch
          name="dark-mode"
          class="inline"
          :value="darkMode"
          label=""
          @input="$emit('toggle-dark-mode', $event)"
        />
      </div>
      <p class="w-full mt-4 text-md font-medium leading-tight text-white">
        made with ♥️ by othyn.
      </p>
    </section>
  </div>
</template>

<script>
export default {
  props: {
    darkMode: {
      type: Boolean,
      required: false,
    },
  },
}
</script>
