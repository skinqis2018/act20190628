<template>
  <div class="banner">
    <img class="banner__bg" src="../img/bg_01.jpg"/>
    <img class="banner__bg" src="../img/bg_02.png"/>
    <img class="banner__bg" src="../img/bg_03.png"/>
    <div class="banner__position">
      <div class="banner__btn">
        <img src="../img/btn_start.png"/>
        <img @click="draw" src="../img/btn_draw.png"/>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      //测试数据，调接口时删除
      result: 0,
      prize: 0
    }
  },
  methods: {
    draw () {
      /**
       * 测试数据，调接口时删除
       * result 表示结果：0 未中奖；1 中奖；2 未点赞
       * prize 表示奖品
       */
      var data = {result: 0, prize: 0};
      this.result == 2 ? this.result = 0 : this.result++
      this.prize == 3 ? this.prize = 0 : this.prize++
      data.result = this.result
      data.prize = this.prize
      eventBus.$emit('openMsg', data)
    }
  }
}
</script>

