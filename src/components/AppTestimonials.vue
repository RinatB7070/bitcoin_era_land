<template>
  <section class="relative z-10">
    <h1 class="uppercase text-center text-3xl text-purple-900 font-semibold mb-10">real testimonials from our users</h1>
    <div :class="testemonialBoxStyle">
      <div
      v-for="people in testemonials"
      class="flex relative w-full"
      >
        <span class="absolute flex flex-col h-full p-4 italic text-center text-white bg-blue-500/60 testimonial-transition">"{{ people.message }}"</span>
        <img :src="require(`../../public/assets/${people.img}.jpg`)" alt="" class="w-full">
        <div class="absolute flex flex-col left-0 right-0 bottom-6">
          <span class="text-lg text-center text-white mb-0.5">{{ people.name }}</span>
          <span class="text-lg text-center text-white mb-0.5">{{ people.city }}, {{ people.region }}</span>
          <span class="text-2xl font-semibold text-center text-yellow-400">Profit: ₽{{ people.profit }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: ['isSm', 'isMed'],
  data () {
    return {
      testemonials: [
        {
          img: 'testimonial1',
          name: 'Mark K.',
          city: 'Tuchkovo',
          region: 'RU',
          profit: '12923',
          message: 'I finally know what it’s like to live the dream. I no longer feel like I’m on the outside looking in while everyone else has all the fun. Bitcoin Era has allowed me to retire early and live the 1% lifestyle.' 
        },
        {
          img: 'testimonial2',
          name: 'Jennifer A.',
          city: 'Neliduvo',
          region: 'RU',
          profit: '7192',
          message: "I've been a member of Bitcoin Era for only 47 days. But my life has already changed! Not only have I made my first."
        },
        {
          img: 'testimonial3',
          name: 'Ernest I.',
          city: 'Sheksna',
          region: 'RU',
          profit: '10519',
          message: "Surprisingly, I used to be an investor on Wall Street. AndI’ve never seen anything like this in my 10 year tenure at the company. My colleagues all thought I was crazy when I quit the firm to invest with the Bitcoin Era software full-time."
        },
        {
          img: 'testimonial4',
          name: 'Jane K.',
          city: 'Ulyanovsk',
          region: 'RU',
          profit: '8519',
          message: "Two weeks ago, I got laid off. With no options left, I thought my life was over. Now I’m making over"
        }
      ],
      upHere: false,
      classLis: ''
    }
  },
  methods: {
    over () {
      this.upHere = true
      console.log(this.upHere)
    },
    leave () {
      this.upHere = false
      console.log(this.upHere)
    }
  },
  computed: {
    testemonialBoxStyle () {
      if (this.isSm) {
        return 'grid grid-cols-1'
      } else if (this.isMed) {
        return 'grid grid-cols-2'
      } else {
        return 'flex h-80' 
      }
    }
  }
}
</script>