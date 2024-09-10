<template>
  <div :class="logoBoxStyle">
    <img class="h-full" v-for="logo in partnerLogos" :src="require(`../../public/assets/${logo}`)" alt="logo">
    <span class="text-yellow-500 flex">BID<span class="text-green-500 text-2xl font-bold ml-1">$ 134.75</span></span>
    <span class="text-gray-500 flex">ASK<span class="text-gray-500 text-2xl font-bold ml-1">$ 134.71</span></span>
  </div>
</template>

<script>
export default {
  props: ['isSm','isMed'],
  data () {
    return {
      partnerLogos: ['bitgo.png', 'norton.png', 'secure-trading.png', 'mcafee.png']
    }
  },
  computed: {
    logoBoxStyle () {
      if (this.isSm) {
        return 'wrapper grid grid-cols-3 gap-3 p-2 justify-items-center'
      } else if (this.isMed) {
        return 'wrapper grid grid-cols-3 gap-4 p-2 justify-items-center'
      } else {
        return 'wrapper flex justify-between items-center py-6' 
      }
    }
  }
}
</script>