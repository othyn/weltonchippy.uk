<template>
  <div>
    <button
      class="text-md font-bold leading-tight font-bold hover:underline"
      @click="showModal = true"
    >
      Please see our full terms & conditions.
    </button>

    <modal
      v-if="showModal"
      title="Terms & Conditions"
      @close="showModal = false"
    >
      <div class="text-left text-gray-800">
        <h3 class="font-bold text-xl pb-1">Offer T&C's</h3>

        <ul class="list-disc pl-4">
          <li>
            Offer can only be redeemed <b>once</b> per order, <b>once</b> per
            customer, <b>once</b> per day.
          </li>
          <li>
            Offer can only be redeemed on <b>one</b> redeemable food item or
            <b>one</b> set of items in an order, unless stated otherwise. e.g.
            "Buy one Fish & Chips, get the SECOND Half Price" applies to only
            <b>one</b> set of "Fish & Chips" in the order, the set of items in
            this case consisting of one portion of "chips" (item 1) and one
            "fish" (item 2). It <b>cannot</b> be used to discount multiple items
            or sets of items on the same order. This applies for any food item,
            offer item and offer discount.
          </li>
          <li>Offer is <b>not</b> valid on Fridays.</li>
          <li>
            Offer is non-negotiable and <b>cannot</b> be used in conjunction
            with any other offers.
          </li>
          <li>
            Offer can be printed or displayed on an electronic device (e.g.
            smart phone), but <b>must</b> be presented to the member of staff
            taking your order at checkout in order to be redeemed.
          </li>
          <li>
            Offer is only valid during the displayed dates and/or time periods.
          </li>
          <li>
            Offer is only valid for/on <b>regular</b> portion sizes, unless
            otherwise specified and <b>cannot</b> be negotiated.
          </li>
          <li>All offers are subject to availability.</li>
        </ul>

        <h3 class="font-bold text-xl mt-8 pb-1">General T&C's</h3>

        <p class="pb-1">
          This is only a very brief abstract of our full terms and conditions.
          If you wish to see our full terms and conditions, please speak to a
          manager.
        </p>

        <ul class="list-disc pl-4">
          <li>
            We will do our best to facilitate dietary requirements and allergen
            accomodation, but it is the customers responsibility to inform us of
            any dietary requirements or allergens prior to ordering. We do not
            accept responsibility or liability for any impact this may cause. We
            have an allergy folder on site, for your reference. Our cooking
            practices may not suit all dietary or allergen requiremnts, please
            speak to the manager on shift should you have any questions.
          </li>
          <li>
            For events and special occasions, we require the following notice
            periods;
          </li>
          <ul class="list-disc pl-8">
            <li>&lt; 10: Food readily available via walk-in</li>
            <li>10-20: 24 to 48 hours notice given of the order in full</li>
            <li>
              20-50: A deposit may be required and a minimum of 72 hours notice
              given of the order in full
            </li>
            <li>
              50+: A 30% non-refundable deposit is required and a minimum of 2
              weeks notice given of the order in full
            </li>
            <li>
              Fridays are exempt from the outlined, for reasons provided in
              figure 3
            </li>
            <li>
              A minimum of 48 hours notice is required to cancel a given order
            </li>
            <li>Changes to orders are at managers discretion</li>
          </ul>
          <li>
            Friday nights, due to regular increased demand, we reserve the right
            to withhold phone ordering, dietary/allergen requirements and event
            and special occasion ordering/facilitation. This is due to increased
            staffing allocation and stock management needing to be planned in
            advance.
          </li>
        </ul>
      </div>
    </modal>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showModal: false,
    }
  },
}
</script>
