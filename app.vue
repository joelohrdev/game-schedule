<script setup>
  useHead({
    titleTemplate: 'Games Schedule',
    viewport: 'width=device-width, initial-scale=1, maximum-scale=1',
    charset: 'utf-8',
    meta: [
      { name: 'Site to keep track of kids game schedule.', content: 'Game schedule site.' }
    ],
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
            <div class="font-bold text-md">{{ date[0].date }}</div>
            <div v-for="game in date" :key="game.id" class="grid grid-cols-3 gap-5">
              <p class="whitespace-nowrap text-sm font-medium text-gray-900"><span class="text-gray-400 font-normal">{{ game.time }}</span></p>
              <p class="whitespace-nowrap text-sm text-gray-900 font-medium">{{ game.name }}</p>
              <p class="whitespace-nowrap text-sm text-gray-900 font-medium">{{ game.vs }}</p>
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
    id: 2,
    name: 'Kailee',
    address: 'Grayslake',
    date: '2022-05-09',
    time: '6:30 PM',
    vs: 'Grayslake North',
  }
]

const alissaGames = [
  {
    id: 1,
    name: 'Alissa',
    address: 'Schaumburg, IL',
    date: '2022-05-06',
    time: '6:00 PM',
    vs: 'Windmills',
  },
  {
    id: 2,
    name: 'Alissa',
    address: 'Schaumburg, IL',
    date: '2022-05-07',
    time: '8:30 AM',
    vs: 'Sluggers',
  },
  {
    id: 3,
    name: 'Alissa',
    address: 'Schaumburg, IL',
    date: '2022-05-07',
    time: '11:30 AM',
    vs: 'Sluggers',
  },
  {
    id: 4,
    name: 'Alissa',
    address: 'Crown Point, IN',
    date: '2022-05-14',
    time: '10:00 AM',
    vs: 'Beverly Bandits',
  },
  {
    id: 5,
    name: 'Alissa',
    address: 'Crown Point, IN',
    date: '2022-05-14',
    time: '2:00 PM',
    vs: 'Sluggers',
  },
  {
    id: 6,
    name: 'Alissa',
    address: 'Crown Point, IN',
    date: '2022-05-14',
    time: '4:00 PM',
    vs: 'Sox Boyd',
  },
]

const jakeGames = [
  {
    id: 1,
    name: 'Jake',
    address: 'Huntly, IL',
    date: '2022-05-04',
    time: '6:00 PM',
    vs: 'Citius Illinois',
  },
  {
    id: 2,
    name: 'Jake',
    address: 'Elgin, IL',
    date: '2022-05-06',
    time: '5:00 PM',
    vs: 'TBD',
  }, 
  {
    id: 3,
    name: 'Jake',
    address: 'Elgin, IL',
    date: '2022-05-07',
    time: '8:00 AM',
    vs: 'TBD',
  },
  {
    id: 4,
    name: 'Jake',
    address: 'Elgin, IL',
    date: '2022-05-08',
    time: '8:00 AM',
    vs: 'TBD',
  },
  {
    id: 5,
    name: 'Jake',
    address: 'Lake in the Hills, IL',
    date: '2022-05-11',
    time: '5:30 PM',
    vs: 'Thunder',
  },
  {
    id: 6,
    name: 'Jake',
    address: 'Franklin, WI',
    date: '2022-05-13',
    time: '5:00 PM',
    vs: 'TBD',
  },
  {
    id: 7,
    name: 'Jake',
    address: 'Franklin, WI',
    date: '2022-05-14',
    time: '8:00 AM',
    vs: 'TBD',
  },
  {
    id: 8,
    name: 'Jake',
    address: 'Franklin, WI',
    date: '2022-05-15',
    time: '8:00 AM',
    vs: 'TBD',
  },
  {
    id: 9,
    name: 'Jake',
    address: 'Lake in the Hills, IL',
    date: '2022-05-18',
    time: '6:00 PM',
    vs: 'Thunder',
  },
  {
    id: 10,
    name: 'Jake',
    address: 'McHenry, IL',
    date: '2022-05-20',
    time: '5:00 PM',
    vs: 'McHenry 9U',
  },
  {
    id: 11,
    name: 'Jake',
    address: 'McHenry, IL',
    date: '2022-05-25',
    time: '6:00 PM',
    vs: 'Mundelein',
  },
  {
    id: 12,
    name: 'Jake',
    address: 'Bettendorf, IA',
    date: '2022-05-27',
    time: '5:00 PM',
    vs: 'TBD',
  },
  {
    id: 13,
    name: 'Jake',
    address: 'Bettendorf, IA',
    date: '2022-05-28',
    time: '8:00 AM',
    vs: 'TBD',
  },
  {
    id: 14,
    name: 'Jake',
    address: 'Bettendorf, IA',
    date: '2022-05-29',
    time: '8:00 AM',
    vs: 'TBD',
  },
  {
    id: 15,
    name: 'Jake',
    address: 'Bettendorf, IA',
    date: '2022-05-30',
    time: '8:00 AM',
    vs: 'TBD',
  },
  {
    id: 16,
    name: 'Jake',
    address: 'McHenry, IL',
    date: '2022-06-01',
    time: '6:00 PM',
    vs: 'RBA',
  },
  {
    id: 17,
    name: 'Jake',
    address: 'McHenry, IL',
    date: '2022-06-03',
    time: '5:00 PM',
    vs: 'TBD',
  },
  {
    id: 18,
    name: 'Jake',
    address: 'McHenry, IL',
    date: '2022-06-04',
    time: '8:00 AM',
    vs: 'TBD',
  },
  {
    id: 19,
    name: 'Jake',
    address: 'McHenry, IL',
    date: '2022-06-05',
    time: '8:00 AM',
    vs: 'TBD',
  },
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
}
</script>