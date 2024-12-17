<template>
  <CoreContentBlock title="Opening Times">
    <div class="flex flex-col">
      <div class="-my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
        <div class="inline-block min-w-full py-2 align-middle sm:px-6 lg:px-8">
          <p class="mb-5 text-gray-500">
            <span class="font-bold">Please note:</span> We will be closed for
            Christmas and New Year from Sunday, 22 December 2024, and will
            reopen on Thursday, 2 January 2025.
          </p>

          <div
            class="overflow-hidden border-b border-gray-200 shadow sm:rounded-lg"
          >
            <table class="min-w-full divide-y divide-gray-200">
              <thead class="bg-gray-50">
                <tr>
                  <th></th>
                  <th
                    scope="col"
                    class="px-6 py-3 text-sm font-medium tracking-wider text-left text-gray-500 uppercase"
                  >
                    Lunch
                  </th>
                  <th
                    scope="col"
                    class="px-6 py-3 text-sm font-medium tracking-wider text-left text-gray-500 uppercase"
                  >
                    Tea
                  </th>
                </tr>
              </thead>
              <tbody class="bg-white divide-y divide-gray-200">
                <tr v-for="day in timetable" :key="day.name">
                  <td
                    class="px-6 py-4 font-bold text-gray-500 whitespace-nowrap text-md"
                  >
                    {{ day.name }}
                  </td>
                  <td
                    class="px-6 py-4 font-medium text-gray-500 whitespace-nowrap text-md"
                  >
                    {{ day.times.lunch.open }}
                    <span v-if="day.times.lunch.close">
                      - {{ day.times.lunch.close }}
                    </span>
                  </td>
                  <td
                    class="px-6 py-4 font-medium text-gray-500 whitespace-nowrap text-md"
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
        </div>
      </div>
    </div>
  </CoreContentBlock>
</template>

<script>
const timetable = [
  {
    name: 'Monday',
    times: {
      lunch: { open: 'Closed', close: '' },
      dinner: { open: '16:30', close: '20:00' },
    },
  },
  {
    name: 'Tuesday',
    times: {
      lunch: { open: '11:30', close: '13:30' },
      dinner: { open: '16:30', close: '20:00' },
    },
  },
  {
    name: 'Wednesday',
    times: {
      lunch: { open: '11:30', close: '13:30' },
      dinner: { open: '16:30', close: '20:00' },
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
