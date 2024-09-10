<template>
  <section class="features-bg">
    <div :class="featuresBoxStyle">
      <div v-for="feature in features" :class="featureStyle">
        <img :src="require(`../../public/assets/${feature.logo}.png`)" alt="" class="mx-auto h-24 mb-6">
        <span
          class="text-lg font-semibold"
          :class="featureTextStyle"
        >{{ feature.title }}</span>
        <span :class="featureTextStyle">{{ feature.text }}</span>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: ['isSm', 'isMed'],
  data () {
    return {
      features: [
        {
          logo: 'feature-img-1',
          title: 'LASER-ACCURATE PERFORMANCE',
          text: "There is no other trading app in the world that performs at the 99.4% level of accuaracy that The Bitcoin Era is able to hit. That's why our members from around the world trust us to double triple and quadruple their hard-earned money."
        },
        {
          logo: 'feature-img-2',
          title: 'SUPERIOR TECHNOLOGY',
          text: 'The Bitcoin Era software has been created using the most advanced programming the trading world has ever seen. The software is ahead of the markets by 0.01 seconds. This "time leap" makes the software the most consistent trading app on the planet.'
        },        {
          logo: 'feature-img-3',
          title: 'AWARD-WINNING TRADING APP',
          text: 'The Bitcoin Era app has won a number of awards. The most recent awards we have had the honor of receiving is getting #1 in the trading software category for the US Trading Association.'
        }
      ]
    }
  },
  computed: {
    featuresBoxStyle () {
      if (this.isSm) {
        return 'wrapper grid grid-cols-1 justify-items-center pt-12 pb-80 justify-around'
      } else if (this.isMed) {
        return 'wrapper grid grid-cols-1 justify-items-center pt-12 pb-80 justify-around'
      } else {
        return 'wrapper flex pt-36 pb-80 justify-around' 
      }
    },
    featureStyle () {
      if (this.isSm) {
        return 'flex flex-col feature-bg p-2 border-b-8 border-purple-500'
      } else if (this.isMed) {
        return 'flex flex-col feature-bg p-3 border-b-8 border-purple-500'
      } else {
        return 'flex flex-col feature-bg p-5 border-b-8 border-purple-500' 
      }
    },
    featureTextStyle () {
      if (this.isSm) {
        return 'text-center text-white mb-2'
      } else if (this.isMed) {
        return 'text-center text-white mb-5'
      } else {
        return 'text-center text-white mb-10' 
      }
    }
  }
}
</script>