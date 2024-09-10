<template>
  <section class="wrapper">
    <h1 :class="headerStyle">FREQUENTLY ASKED QUESTIONS</h1>
    <div :class="questionsBoxStyle">
      <div v-for="(question, index) in questions" :class="questionBoxStyle">
        <div :class="questionNumStyle">{{ index }}</div>
        <h2 class="text-xl font-semibold text-purple-700 mb-2">{{ question.title }}</h2>
        <p>{{ question.text }}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: ['isSm', 'isMed'],
  data() {
    return {
      questions: [
        {
          title: 'What kind of results can I expect?',
          text: 'Bitcoin Era members typically profit a minimum of ₽1100 daily.'
        },
        {
          title: 'How many hours per day do I need to work?',
          text: 'Our members work an average of 20 minutes a day or less. Because the software handles the trading the amount of "work" required is minimal.'
        },
        {
          title: 'What is the maximum amount that I can make?',
          text: 'Your profits are unlimited within The Bitcoin Era. Some members earned their first million within just 61 days.'
        },
        {
          title: 'How much does the software cost?',
          text: 'Members of The Bitcoin Era get a copy of our proprietart software free of charge. To become a member, simply fill out the form on this page.'
        },
        {
          title: 'Is this like MLM or Affiliate Marketing?',
          text: 'This is not like MLM, affiliate marketing or anything else out there. The software wins trades with 99.4% accuaracy.'
        },
        {
          title: 'Are there any fees?',
          text: 'There are no hidden fees. No broker fees or commissions. All of your money is 100% yours and you are free to withdraw it at any time you choose without delay.'
        },
      ]
    }
  },
  computed: {
    headerStyle () {
      if (this.isSm) {
        return 'text-3xl font-bold text-purple-900 text-center mb-20'
      } else if (this.isMed) {
        return 'text-3xl font-bold text-purple-900 text-center mb-20'
      } else {
        return 'text-4xl font-bold text-purple-900 text-center mb-20' 
      }
    },
    questionsBoxStyle () {
      if (this.isSm) {
        return 'grid grid-cols-1 mb-20'
      } else if (this.isMed) {
        return 'grid grid-cols-1 mb-20'
      } else {
        return 'grid grid-cols-2 gap-y-5 gap-x-20 mb-20' 
      }
    },
    questionBoxStyle () {
      if (this.isSm) {
        return 'p-8 pl-20 relative shadow-lg mx-5'
      } else if (this.isMed) {
        return 'p-8 pl-20 relative shadow-lg mx-5'
      } else {
        return 'p-8 ml-14 relative shadow-lg' 
      }
    },
    questionNumStyle () {
      if (this.isSm) {
        return 'bg-purple-700 text-white text-xl absolute left-4 top-10 px-5 py-3'
      } else if (this.isMed) {
        return 'bg-purple-700 text-white text-lg absolute left-4 top-10 px-3 py-1'
      } else {
        return 'bg-purple-700 text-white text-xl absolute -left-6 top-16 px-5 py-3' 
      }
    }
  }
}
</script>