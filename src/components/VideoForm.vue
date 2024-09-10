<template>
  <section class="videoform-bg">
    <div class="wrapper mx-auto pt-4 pb-16">
      <h1 :class="titleStyle">Bitcoin Is Making People Rich</h1>
      <p :class="textStyle">And you Become The <span class="text-yellow-500">Next Millionare...</span></p>
      <div :class="videoFormBoxStyle">
      <div class="mr-8 mb-6">
        <div class="absolute text-white mt-4 ml-6 text-lg">Sunday August 21, 2021</div>
        <video src="../../public/assets/videoplayback.mp4" controls autoplay loop muted playsinline class="border-8 video-width box-border"></video>
      </div>
      <AppForm
        :isSm="this.isSm"
        :isMed="this.isMed"
      ></AppForm>
      </div>
    </div>
  </section>
</template>

<script>
import AppForm from './AppForm.vue';
export default {
  props: ['isSm','isMed'],
  data () {
    return {
    }
  },
  computed: {
    titleStyle () {
      if (this.isSm) {
        return 'text-center text-white text-4xl font-bold pt-8 pb-6'
      } else if (this.isMed) {
        return 'text-center text-white text-5xl font-bold pt-8 pb-6'
      } else {
        return 'text-center text-white text-6xl font-bold pt-8 pb-6' 
      }
    },
    textStyle () {
      if (this.isSm) {
        return 'text-center text-white text-2xl pb-7'
      } else if (this.isMed) {
        return 'text-center text-white text-3xl pb-7'
      } else {
        return 'text-center text-white text-4xl pb-7' 
      } 
    },
    videoFormBoxStyle () {
      if (this.isSm) {
        return 'flex flex-col items-center px-8 '
      } else if (this.isMed) {
        return 'flex px-8'
      } else {
        return 'flex px-8' 
      }
    }
  },
  components: {
    AppForm
  }
}
</script>