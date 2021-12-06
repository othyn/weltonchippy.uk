<template>
  <CoreContentBlock title="Opening Times">
    <div class="shadow overflow-hidden border-b border-gray-200 sm:rounded-lg">
      <table class="min-w-full divide-y divide-gray-200">
        <thead class="bg-gray-50">
          <tr>
            <th></th>
            <th
              scope="col"
              class="px-6 py-3 text-left text-sm font-medium text-gray-500 uppercase tracking-wider"
            >
              Lunch
            </th>
            <th
              scope="col"
              class="px-6 py-3 text-left text-sm font-medium text-gray-500 uppercase tracking-wider"
            >
              Tea
            </th>
          </tr>
        </thead>
        <tbody class="bg-white divide-y divide-gray-200">
          <tr v-for="day in timetable" :key="day.name">
            <td
              class="px-6 py-4 whitespace-nowrap text-md font-bold text-gray-500"
            >
              {{ day.name }}
            </td>
            <td
              class="px-6 py-4 whitespace-nowrap text-md font-medium text-gray-500"
            >
              {{ day.times.lunch.open }}
              <span v-if="day.times.lunch.close">
                - {{ day.times.lunch.close }}
              </span>
            </td>
            <td
              class="px-6 py-4 whitespace-nowrap text-md font-medium text-gray-500"
            >
              {{ day.times.dinner.open }}
              <span v-if="day.times.dinner.close">
                - {{ day.times.dinner.close }}
              </span>
            </td>
          </tr>
        </tbody>
      </table>
    </div>

    <p class="w-full my-12 text-sm font-medium leading-tight text-gray-400">
      <span class="font-bold">Please note:</span><br />Between January and
      March, we are under winter closing hours, which override the normal
      opening hours. This means the shop will close at 8:30pm, unless otherwise
      specified to close sooner.
    </p>
  </CoreContentBlock>
</template>

<script>
const timetable = [
  {
    name: 'Monday',
    times: {
      lunch: { open: '11:30', close: '13:30' },
      dinner: { open: '16:30', close: '20:00' },
    },
  },
  {
    name: 'Tuesday',
    times: {
      lunch: { open: '11:30', close: '13:30' },
      dinner: { open: '16:30', close: '20:30' },
    },
  },
  {
    name: 'Wednesday',
    times: {
      lunch: { open: '11:30', close: '13:30' },
      dinner: { open: '16:30', close: '20:30' },
    },
  },
  {
    name: 'Thursday',
    times: {
      lunch: { open: '11:30', close: '13:30' },
      dinner: { open: '16:30', close: '20:30' },
    },
  },
  {
    name: 'Friday',
    times: {
      lunch: { open: '11:30', close: '13:30' },
      dinner: { open: '16:30', close: '20:30' },
    },
  },
  {
    name: 'Saturday',
    times: {
      lunch: { open: '11:30', close: '13:30' },
      dinner: { open: '16:30', close: '20:00' },
    },
  },
  {
    name: 'Sunday',
    times: {
      lunch: { open: 'Closed', close: '' },
      dinner: { open: 'Closed', close: '' },
    },
  },
]

export default {
  data() {
    return {
      timetable,
    }
  },
}
</script>
