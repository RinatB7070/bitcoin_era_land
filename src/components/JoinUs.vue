<template>
  <div :class="boxStyle">
    <div class="join-us-bg">
      <div class="wrapper">
        <div :class="headerBoxStyle">
          <h1 class="text-5xl text-blue-900 font-semibold pb-16">Join Us and Start Getting Rich <span class="text-purple-900">with Bitcoin Era!</span></h1>
          <p class="text-base">The Bitcoin Era is a group reserved exclusively to people who jumped on the insane returns that Bitcoin offers and have quietly amassed a fortune in doing so. Our members enjoy retreats around the world every month while they make money on their laptop with just a few minutes of “work” every day</p>
        </div>
      </div>
    </div>
    <div :class="seenBoxStyle">
      <div class="flex flex-col items-center join-us-width mt-16">
        <h1 class="text-xl font-bold text-purple-900 mb-6">As seen on</h1>
        <img src="../../public/assets/seenon.png" alt="">
      </div>
      <img class="absolute position-img" src="../../public/assets/girl-holding-bitcoin.png" alt="girl" v-show="!isMed && !isSm">
    </div>
  </div>
 

</template>

<script>
export default {
  props: ['isSm', 'isMed'],
  data() {
    return {
    }
  },
  computed: {
    boxStyle () {
      if (this.isSm) {
        return 'mb-24'
      } else if (this.isMed) {
        return 'mb-36'
      } else {
        return 'mb-52' 
      }
    },
    headerBoxStyle () {
      if (this.isSm) {
        return 'join-us-width-sm py-16 px-4 text-center mx-auto'
      } else if (this.isMed) {
        return 'join-us-width-med py-12 px-4 text-center mx-auto'
      } else {
        return 'join-us-width py-16 px-4' 
      }
    },
    seenBoxStyle () {
      if (this.isSm) {
        return 'wrapper'
      } else if (this.isMed) {
        return 'wrapper'
      } else {
        return 'wrapper flex relative' 
      }
    }
  }
}
</script>