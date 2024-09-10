<template>
  <header>
    <div class="py-1 bg-red-600 text-center text-white text-lg">WARNING: Due to extremely high media demand, we will close registration as of 08/08/2024 - HURRY! 0{{ timer[0] }}:{{ getSeconds }}</div>
    <div
      :class="mediaHeaderBoxStyle"
      >
      <img src="../../public/assets/logo.png" alt="logo" :class="mediaHeaderLogoStyle ">
      <div class="flex max-w-md py-5">
        <p
          class="uppercase font-semibold"
          :class="mediaMobileTextStyle"
        >Exclusive offers for <br>
          <span class="text-red-600">trades in United Kingdom of Great Britain and Northern Ireland (the)</span>
          </p>
          <img src="../../public/assets/flag.svg" alt="flag" class="w-10">
      </div>
      <div :class="mediaHeaderJustMadeStyle">
        <img
        :src="require(`../../public/assets/users/${jusMadePeople[personCounter].img}.jpg`)"
         alt="photo" class="h-16 border-4 border-yellow-500 rounded-full my-auto mr-4">
        <div class="flex flex-col my-auto w-32">
          <p class="flex justify-center">
            <span class="font-bold text-center">{{ jusMadePeople[personCounter].name }}</span>
            &nbsp
            <span class="font-bold">{{ jusMadePeople[personCounter].surename }}</span>
          </p>
          <span class="text-center">just made:</span>
          <span class="font-bold text-center">$ {{ jusMadePeople[personCounter].amount }}</span>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  props: ['isSm','isMed'],
  data () {
    return {
      timer: [5, 6],
      personCounter: 0,
      jusMadePeople: [
        {
          name: 'William',
          surename: 'Cook',
          amount: 720,
          img: 'man/1'
        },
        {
          name: 'Jakob',
          surename: 'Haas',
          amount: 911,
          img: 'man/2'
        },
        {
          name: 'Sam',
          surename: 'Lisner',
          amount: 652,
          img: 'man/3'
        },
        {
          name: 'Hoel',
          surename: 'Hakas',
          amount: 391,
          img: 'man/4'
        },
        {
          name: 'Lea',
          surename: 'Sholz',
          amount: 556,
          img: 'woman/1'
        },
        {
          name: 'Erik',
          surename: 'Horn',
          amount: 231,
          img: 'man/5'
        }
        
      ]
    }
  },
  methods: {
    startTimer () {
      let timer = setInterval(() => {
        {
          this.timer[1]--;
          if (this.timer[1] === 0) {
            this.timer[1] = 60;
            this.timer[0]--;
          } else if (this.timer[0] === 0 && this.timer[1] === 1) {
            this.timer[1]--;
            clearInterval(timer);
          }
        }
      }, 1000);
    },
    changePerson () {
      return setInterval(() => {
        {
          this.personCounter++;
          if (this.personCounter == this.jusMadePeople.length) {
            this.personCounter = 0;
          }
        }
      }, 8000);
    }
  },
  computed: {
    getSeconds () {
      if (this.timer[1] < 10) {
        return '0' + this.timer[1]
      } else {
        return this.timer[1]
      }
    },
    mediaHeaderBoxStyle () {
      if (this.isSm) {
        return 'wrapper flex flex-col items-center justify-between mx-auto pb-4'
      } else {
        return 'wrapper flex justify-between mx-auto' 
      }
    },
    mediaHeaderLogoStyle () {
      if (this.isSm) {
        return 'w-40 h-6 my-auto'
      } else if (this.isMed) {
        return 'w-60 h-10 my-auto'
      } else {
        return 'w-72 h-12 my-auto' 
      }
    },
    mediaHeaderJustMadeStyle () {
      if (this.isMed) {
        return 'flex bg-gray-100 px-2'
      } else {
        return 'flex bg-gray-100 px-5'
      }
    },
    mediaMobileTextStyle () {
      if (this.isSm) {
        return 'text-normal'
      } else if (this.isMed) {
        return 'text-lg'
      } else {
        return 'text-xl' 
      }
    }
  },
  mounted() {
    this.startTimer();
    this.changePerson();
  }
}
</script>
