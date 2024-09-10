<template>
  <section class="mt-20">
    <div :class="bgStyle"></div>
    <div class="wrapper relative -top-48">
      <h2 :class="headerStyle">HOW IT WORKS</h2>
      <div :class="stepsBox">
        <div v-for="(step, index) in steps" class="text-center step-w border mb-10 pb-10 bg-white">
          <h2 :class="step.headerStyle">Step {{ index + 1 }}</h2>
          <div class="p-4">
            <img :src="require(`../../public/assets/${step.logo}.png`)" alt="logo" class="mx-auto mb-3" >
            <h2 class="mb-3 text-lg font-bold text-purple-900">{{ step.title }}</h2>
            <span>{{ step.text }}</span>
          </div>
        </div>
      </div>
      <button class="bg-yellow-300 border-b-4 border-yellow-500 rounded-lg text-2xl font-bold py-6 px-16 block mx-auto">OPEN FREE ACCOUNT</button>
    </div>
  </section>
</template>

<script>
export default {
  props: ['isSm', 'isMed'],
  data() {
    return {
      steps: [
        {
          logo: 'step-img-1',
          title: 'REGISTER ON THE SITE',
          text: 'Once your registration is accepted, you will automatically become the newest member of the Bitcoin Era. And you will get to claim our proprietary bitcoin trading software for free',
          headerStyle: 'bg-purple-800 text-lg text-white py-1',
        },
        {
          logo: 'step-img-2',
          title: 'FUND YOUR ACCOUNT',
          text: 'Like any business, you need working capital to get started. So to start profiting with The Bitcoin Era, you must invest any amount you desire of ₽250 or more.',
          headerStyle: 'bg-blue-900 text-lg text-white py-1',
        },
        {
          logo: 'step-img-3',
          title: 'FINISH',
          text: 'Click trade to enjoy precise and accurate hands-free trading powered by our award-winning algorithm. You can also set the trading to manual if you prefer to trade on your own.',
          headerStyle: 'bg-blue-600 text-lg text-white py-1',
        },
      ]
    }
  },
  computed: {
    bgStyle () {
      if (this.isSm) {
        return 'bg-blue-600 w-full step-bg-med absolute'
      } else if (this.isMed) {
        return 'bg-blue-600 w-full step-bg-med absolute'
      } else {
        return 'bg-blue-600 w-full h-96 absolute' 
      }
    },
    headerStyle () {
      if (this.isSm) {
        return 'text-center text-4xl font-semibold text-purple-900 mb-16'
      } else if (this.isMed) {
        return 'text-center text-4xl font-semibold text-purple-900 mb-16'
      } else {
        return 'text-center text-5xl font-semibold text-purple-900 mb-16' 
      }
    },
    stepsBox () {
      if (this.isSm) {
        return 'flex flex-col items-center'
      } else if (this.isMed) {
        return 'flex flex-col items-center'
      } else {
        return 'flex justify-between' 
      }
    }
  }
}
</script>