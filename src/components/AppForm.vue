<template>
  <div class="max-w-96"> 
    <h1 :class="headerStyle">Change your life today!</h1>
    <div class="flex">
      <span class="border-4 w-3/6 border-yellow-500"></span>
      <span class="border-4 w-3/6 border-pink-500"></span>
    </div>
    <form action=""  :class="inputBoxStyle">
      <input type="text" placeholder="Your First Name" :class="inputStyle">
      <input type="text" placeholder="Your Last Name" :class="inputStyle">
      <input type="text" placeholder="Your Email" :class="inputStyle">
      <input type="tel" placeholder="Your mobile phone" :class="inputStyle">
      <button :class="btnStyle">submit</button>
    </form>
  </div>
</template>

<script>
export default {
  props: ['isSm','isMed'],
  computed: {
    headerStyle () {
      if (this.isSm) {
        return 'uppercase text-center text-white text-xl font-semibold tracking-wider pt-4 px-6 pb-4 videoform_header-bg'
      } else if (this.isMed) {
        return 'uppercase text-center text-white text-2xl font-semibold tracking-wider pt-3 px-6 pb-3 videoform_header-bg'
      } else {
        return 'uppercase text-center text-white text-4xl font-semibold tracking-wider pt-6 px-9 pb-5 videoform_header-bg' 
      }
    },
    inputBoxStyle () {
      if (this.isSm) {
        return 'form-bg p-3'
      } else if (this.isMed) {
        return 'form-bg p-3'
      } else {
        return 'form-bg p-4'
      }
    },
    inputStyle () {
      if (this.isSm) {
        return 'bg-gray-50 border border-gray-300 text-lg rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-1 pl-4 mb-3'
      } else if (this.isMed) {
        return 'bg-gray-50 border border-gray-300 text-lg rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-1 pl-4 mb-3'
      } else {
        return 'bg-gray-50 border border-gray-300 text-lg rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-1 pl-4 mb-3' 
      }
    },
    btnStyle () {
      if (this.isSm) {
        return 'uppercase bg-blue-700 border border-blue-700 text-white text-center text-xl font-bold w-full rounded-lg px-2 py-3'
      } else if (this.isMed) {
        return 'uppercase bg-blue-700 border border-blue-700 text-white text-center text-lg font-bold w-full rounded-lg px-1 py-2'
      } else {
        return 'uppercase bg-blue-700 border border-blue-700 text-white text-center text-xl font-bold w-full rounded-lg px-2 py-3' 
      }
    }
  }
}
</script>