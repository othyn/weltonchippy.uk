<template>
  <CoreContentBlock title="Opening Times">
    <div class="flex flex-col">
      <div class="-my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
        <div class="py-2 align-middle inline-block min-w-full sm:px-6 lg:px-8">
          <div
            class="shadow overflow-hidden border-b border-gray-200 sm:rounded-lg"
          >
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
