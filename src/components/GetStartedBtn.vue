<template>
  <section class="get-started-bg py-20">
    <button :class="btnStyle">GET STARTED NOW</button>
  </section>
</template>

<script>
export default {
  props: ['isSm', 'isMed'],
  computed: {
    btnStyle () {
      if (this.isSm) {
        return 'bg-yellow-300 border-b-4 border-yellow-500 rounded-lg text-xl text-purple-900 font-bold py-12 px-24 block mx-auto'
      } else if (this.isMed) {
        return 'bg-yellow-300 border-b-4 border-yellow-500 rounded-lg text-2xl text-purple-900 font-bold py-12 px-32 block mx-auto'
      } else {
        return 'bg-yellow-300 border-b-4 border-yellow-500 rounded-lg text-2xl text-purple-900 font-bold py-12 px-44 block mx-auto' 
      }
    }
  }
}
</script>