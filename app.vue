<script setup>
  useHead({
    titleTemplate: 'Games Schedule',
    viewport: 'width=device-width, initial-scale=1, maximum-scale=1',
    charset: 'utf-8',
    meta: [
      { name: 'Site to keep track of kids game schedule.', content: 'Game schedule site.' }
    ],
    bodyAttrs: {
      class: 'bg-gray-100'
    }
  })
</script>
<template>
  <div>
    <Head>
      <Title>Games Schedule</Title>
    </Head>
    <div class="max-w-7xl mx-auto my-10 px-4 sm:px-6 lg:px-8">
    <div class="max-w-2xl mx-auto">
      <div>
        <h1 class="font-black text-black text-5xl mb-10">Schedule</h1>
        <ul role="list" class="divide-y divide-gray-200">
          <li v-for="date in groupedGames" :key="date.id" class="flex flex-col justify-between py-6">
            <div class="font-bold text-md mb-3">{{ formateDate(date[0].date) }}</div>
            <div v-for="game in date" :key="game.id" class="grid grid-cols-2 gap-5 bg-white p-5 rounded-xl mb-2">
              <div class="grid sm:grid-cols-2">
                <p class="whitespace-nowrap text-sm font-medium text-sky-600">{{ game.address }}</p>
                <p class="whitespace-nowrap text-sm font-medium text-sky-600">{{ game.time }}</p>
              </div>
              <div class="grid sm:grid-cols-2">
                <p class="whitespace-nowrap text-sm text-sky-600 font-medium">{{ game.name }}</p>
                <p class="whitespace-nowrap text-sm text-sky-600 font-medium">vs. {{ game.vs }}</p>
              </div>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
  </div>
</template>

<script>

const kaileeGames = [
{
  id: 1,
  name: 'Kailee',
  address: 'Janesville, WI',
  date: '2022-06-10',
  time: '10:30 AM',
  vs: 'Wisconsin Twisters',
},
{
  id: 2,
  name: 'Kailee',
  address: 'Janesville, WI',
  date: '2022-06-10',
  time: '1:30 PM',
  vs: 'ISA Silver',
},
{
  id: 3,
  name: 'Kailee',
  address: 'Janesville, WI',
  date: '2022-06-10',
  time: '7:30 PM',
  vs: 'Force Fastpitch',
}
]

const alissaGames = [
  {
  id: 1,
  name: 'Alissa',
  address: 'Crystal Lake, IL',
  date: '2022-06-12',
  time: '12:00 M',
  vs: 'CTW 11U',
}
]

const jakeGames = [
  {
    id: 20,
    name: 'Jake',
    address: 'McHenry, IL',
    date: '2022-06-08',
    time: '5:00 PM',
    vs: 'GRB Illinois',
  },
  {
    id: 21,
    name: 'Jake',
    address: 'McHenry, IL',
    date: '2022-06-13',
    time: '6:00 PM',
    vs: 'Rawling Tigers',
  },
  {
    id: 22,
    name: 'Jake',
    address: 'McHenry, IL',
    date: '2022-06-15',
    time: '6:00 PM',
    vs: 'Windy City',
  },
  {
    id: 23,
    name: 'Jake',
    address: 'Deerfield, IL',
    date: '2022-06-16',
    time: '5:00 PM',
    vs: 'TBD',
  },
  {
    id: 24,
    name: 'Jake',
    address: 'Deerfield, IL',
    date: '2022-06-17',
    time: '8:00 AM',
    vs: 'TBD',
  },
  {
    id: 25,
    name: 'Jake',
    address: 'Deerfield, IL',
    date: '2022-06-18',
    time: '8:00 AM',
    vs: 'TBD',
  },
  {
    id: 26,
    name: 'Jake',
    address: 'Deerfield, IL',
    date: '2022-06-19',
    time: '8:00 AM',
    vs: 'TBD',
  },
  {
    id: 27,
    name: 'Jake',
    address: 'McHenry, IL',
    date: '2022-06-21',
    time: '8:00 AM',
    vs: 'RBA',
  },
  {
    id: 28,
    name: 'Jake',
    address: 'Wisconsin Dells, WI',
    date: '2022-06-24',
    time: '5:00 PM',
    vs: 'TBD',
  },
  {
    id: 29,
    name: 'Jake',
    address: 'Wisconsin Dells, WI',
    date: '2022-06-25',
    time: '5:00 PM',
    vs: 'TBD',
  },
  {
    id: 30,
    name: 'Jake',
    address: 'Wisconsin Dells, WI',
    date: '2022-06-26',
    time: '5:00 PM',
    vs: 'TBD',
  },
  {
    id: 31,
    name: 'Jake',
    address: 'McHenry, IL',
    date: '2022-06-29',
    time: '6:00 PM',
    vs: 'TBD',
  },
  {
    id: 32,
    name: 'Jake',
    address: 'Woodridge, IL',
    date: '2022-06-30',
    time: '5:00 PM',
    vs: 'TBD',
  },
  {
    id: 33,
    name: 'Jake',
    address: 'Woodridge, IL',
    date: '2022-07-01',
    time: '5:00 PM',
    vs: 'TBD',
  },
  {
    id: 34,
    name: 'Jake',
    address: 'Woodridge, IL',
    date: '2022-07-02',
    time: '5:00 PM',
    vs: 'TBD',
  },
  {
    id: 35,
    name: 'Jake',
    address: 'Woodridge, IL',
    date: '2022-07-03',
    time: '5:00 PM',
    vs: 'TBD',
  },
  {
    id: 36,
    name: 'Jake',
    address: 'Woodridge, IL',
    date: '2022-07-04',
    time: '5:00 PM',
    vs: 'TBD',
  },
]

const allGames = alissaGames.concat(kaileeGames).concat(jakeGames);

const sortedGames = allGames.sort((a, b) => {
  return new Date(a.date) - new Date(b.date)
})

// Group sortedGames by date
const groupedGames = sortedGames.reduce((acc, curr) => {
  const date = curr.date;
  if (!acc[date]) {
    acc[date] = [];
  }
  acc[date].push(curr);
  return acc;
}, {});


export default {
  setup() {
    return {
      groupedGames
    }
  },
  methods: {
    formateDate(date) {
      const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
      return new Date(date.concat('T00:00:00')).toLocaleDateString('en-US', options);
    }
  }
}
</script>