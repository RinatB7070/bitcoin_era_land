<template>
  <section class="wrapper flex flex-col live-box">
    <button :class="btnStyle">JOIN NOW!</button>
    <div :class="tableBoxStyle">
      <h1 :class="headerStyle">LIVE PROFIT RESULTS</h1>
      <table class="table-auto w-full mb-14">
        <thead>
          <tr class="flex justify-between border-b-2 border-gray-200">
            <th :class="tHeadThClasses">Name</th>
            <th :class="tHeadThClasses">Profit</th>
            <th :class="tHeadThClasses">Trade Time</th>
            <th :class="tHeadThClasses">Cryptocurrency</th>
            <th :class="tHeadThClasses">Result</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="people in active_people"  class="flex justify-between border-b-2 border-gray-200">
            <th :class="tBodyThClasses">{{ people.name }}</th>
            <th :class="tBodyThClasses">₽ {{ people.profit }}</th>
            <th :class="tBodyThClasses" class="font-normal">{{ currentDate }}</th>
            <th :class="tBodyThClasses" class="font-normal">{{ people.cryptocurrency }}</th>
            <th :class="tBodyThClasses"><img src="../../public/assets/tick.png" alt="" class="mx-auto"></th>
          </tr>
        </tbody>
      </table>
    </div>
  </section>
</template>

<script>
export default {
  props: ['isSm', 'isMed'],
  data () {
    let date = new Date;
    return {
      live_profit_people: [
        {
          name: 'Elisa Roth',
          profit: '155',
          cryptocurrency: 'LTC/EOS'
        },
        {
          name: 'Till Kühn',
          profit: '547',
          cryptocurrency: 'ETH/LTC'
        },
        {
          name: 'Aaron Koch',
          profit: '704',
          cryptocurrency: 'LTC/EOS'
        },
        {
          name: 'Liam Kraus',
          profit: '692',
          cryptocurrency: 'ETH/LTC'
        },
        {
          name: 'Mara Kraus',
          profit: '543',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Sam Ilsner',
          profit: '1023',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Sam Ilsner',
          profit: '284',
          cryptocurrency: 'BTC/ETH'
        },
        {
          name: 'Lenny Horn',
          profit: '345',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Lukas Graf',
          profit: '953',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'David Gregory',
          profit: '588',
          cryptocurrency: 'BTC/ETH'
        },
        {
          name: 'Max Maier',
          profit: '755',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Lea Scholz',
          profit: '288',
          cryptocurrency: 'BTC/ETH'
        },
        {
          name: 'Nico Frank',
          profit: '139',
          cryptocurrency: 'ETH/LTC'
        },
        {
          name: 'Toni Thoma',
          profit: '924',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Nico Frank',
          profit: '139',
          cryptocurrency: 'ETH/LTC'
        },
        {
          name: 'Romy Wolf',
          profit: '789',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Tom Vogt',
          profit: '421',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Finn Horn',
          profit: '951',
          cryptocurrency: 'BTC/ETH'
        },
        {
          name: 'Maila Hahn',
          profit: '924',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Mats Huber',
          profit: '467',
          cryptocurrency: 'EOS/ETH'
        },
      ],
      active_people: [
        {
          name: 'Elisa Roth',
          profit: '155',
          cryptocurrency: 'LTC/EOS'
        },
        {
          name: 'Till Kühn',
          profit: '547',
          cryptocurrency: 'ETH/LTC'
        },
        {
          name: 'Liam Kraus',
          profit: '692',
          cryptocurrency: 'ETH/LTC'
        },
        {
          name: 'Aaron Koch',
          profit: '704',
          cryptocurrency: 'LTC/EOS'
        },
        {
          name: 'Mara Kraus',
          profit: '543',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Max Maier',
          profit: '755',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Sam Ilsner',
          profit: '1023',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Lenny Horn',
          profit: '345',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Lukas Graf',
          profit: '953',
          cryptocurrency: 'EOS/ETH'
        },
        {
          name: 'Sam Ilsner',
          profit: '284',
          cryptocurrency: 'BTC/ETH'
        },
      ],
      date: date,
      tHeadThClasses: 'block w-full py-3',
      tBodyThClasses: 'block w-full py-3 text-lg'
    }
  },
  computed: {
    currentDate () {
      return this.date.getDate() + '/' + (this.date.getMonth() + 1) + '/' + this.date.getFullYear()
    },
    tableBoxStyle () {
      if (this.isSm) {
        return 'px-4'
      } else if (this.isMed) {
        return 'px-24'
      } else {
        return 'px-36' 
      }
    },
    headerStyle () {
      if (this.isSm) {
        return 'text-center text-3xl font-bold text-purple-900 mb-12'
      } else if (this.isMed) {
        return 'text-center text-4xl font-bold text-purple-900 mb-12'
      } else {
        return 'text-center text-5xl font-bold text-purple-900 mb-12' 
      }
    },
    btnStyle () {
      if (this.isSm) {
        return 'bg-yellow-300 border-b-4 border-yellow-500 rounded-lg text-2xl font-bold py-4 px-32 mx-auto relative -top-14'
      } else if (this.isMed) {
        return 'bg-yellow-300 border-b-4 border-yellow-500 rounded-lg text-2xl font-bold py-4 px-32 mx-auto relative -top-14'
      } else {
        return 'bg-yellow-300 border-b-4 border-yellow-500 rounded-lg text-3xl font-bold py-6 px-40 mx-auto relative -top-14' 
      }
    }
  },
  methods: {
    currentPeople () {
      let counter = 9
      return setInterval(() => {
        {
          this.active_people.push(this.live_profit_people[counter]);
          this.active_people.shift()
          if (counter < 19) {
            counter++
          } else {
            counter = 0
          }
        }
      }, 4000);
    }
  },
  mounted() {
    this.currentPeople();
  }
}
</script>