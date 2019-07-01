<template>
  <div class="msg" v-show="visible">
    <div class="msg__mask">
      <div v-show="sorry || unqualified" class="msg__result">
        <img v-show="sorry" src="../img/Orochimaru_sorry.png" />
        <img v-show="unqualified" src="../img/Orochimaru_unqualified.png" />
        <div :class="{close__Orochimaru: sorry || unqualified}" @click="close" class="close"></div>
      </div>
      <div v-show="prize" class="msg__prize">
        <img class="msg__prize__bg" src="../img/msg_prize.png">
        <img class="msg__prize__icon" :src="icon">
        <div :class="{close__prize: prize}" @click="close" class="close"></div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      visible: false,
      sorry: false,
      unqualified: false,
      prize: false,
      icon: require('../img/prize_demo_01.png'),
      icons: [
        require('../img/prize_demo_01.png'),
        require('../img/prize_demo_02.png'),
        require('../img/prize_demo_03.png'),
        require('../img/prize_demo_04.png')
      ]
    }
  },
  created () {
    eventBus.$on('openMsg', obj => {
      switch (obj.result) {
        case 0:
          this.sorry = true
          break;
        case 1:
          this.prize = true
          this.icon = this.icons[obj.prize]
          break;
        case 2:
          this.unqualified = true
          break;
        default:
          this.sorry = true
          break;
      }
      this.visible = true
    })
  },
  methods: {
    close () {
      this.visible = false
      this.sorry = false
      this.prize = false
      this.unqualified = false
    }
  }
}
</script>

