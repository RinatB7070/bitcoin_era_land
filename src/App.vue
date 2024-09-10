<template>
  <AppHeader
    :isSm="this.isSm"
    :isMed="this.isMed"
    ></AppHeader>
  <VideoForm
    :isSm="this.isSm"
    :isMed="this.isMed"
    ></VideoForm>
  <AppLogos
    :isSm="this.isSm"
    :isMed="this.isMed"
    ></AppLogos>
  <JoinUs
    :isSm="this.isSm"
    :isMed="this.isMed"
  ></JoinUs>
  <AppTestimonials
    :isSm="this.isSm"
    :isMed="this.isMed"
  ></AppTestimonials>
  <AppFeatures
    :isSm="this.isSm"
    :isMed="this.isMed"
  ></AppFeatures>
  <LiveResults
    :isSm="this.isSm"
    :isMed="this.isMed"
  ></LiveResults>
  <HowItWorks
    :isSm="this.isSm"
    :isMed="this.isMed"
  ></HowItWorks>
  <AskedQuestions
    :isSm="this.isSm"
    :isMed="this.isMed"
  ></AskedQuestions>
  <GetStartedBtn
    :isSm="this.isSm"
    :isMed="this.isMed"
  ></GetStartedBtn>
  <AppFooter></AppFooter>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import VideoForm from './components/VideoForm.vue';
import AppLogos from './components/AppLogos.vue';
import JoinUs from './components/JoinUs.vue';
import AppTestimonials from './components/AppTestimonials.vue';
import AppFeatures from './components/AppFeatures.vue';
import LiveResults from './components/LiveResults.vue';
import HowItWorks from './components/HowItWorks.vue';
import AskedQuestions from './components/AskedQuestions.vue';
import GetStartedBtn from './components/GetStartedBtn.vue';
import AppFooter from './components/AppFooter.vue'

export default {
  data () {
    const mediaSm = window.matchMedia('(max-width: 640px)');
    const mediaMed = window.matchMedia('(max-width: 800px)');
    return {
        mediaSm,
        mediaMed,
        isSm: mediaSm.matches,
        isMed: mediaMed.matches
    }
  },
  mounted() {
    this.mediaSm.addEventListener('change', () => {
      this.isSm = this.mediaSm.matches;
    }) 
    this.mediaMed.addEventListener('change', () => {
      this.isMed = this.mediaMed.matches;
    }) 
  },
  components: {
    AppHeader,
    VideoForm,
    AppLogos,
    JoinUs,
    AppTestimonials,
    AppFeatures,
    LiveResults,
    HowItWorks,
    AskedQuestions,
    GetStartedBtn,
    AppFooter
  }
}
</script>

