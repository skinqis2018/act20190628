<template>
  <div class="list">
    <header>
      <img src="../img/list_head.png"/>
    </header>
    <div class="list__content">
      <div 
        v-for="item in list[0]" 
        :key="item.id"
        class="list__item">
        <img class="list__item__poster" :src="item.poster"/>
        <div class="list__item__info">
          <div class="list__item__info__anchor">
            <img :src="item.avatar">
            <span>{{item.nick}}</span>
          </div>
          <div 
            class="list__item__info__follow"
            @click="follow(item)">
            <img v-if="item.isFollowed" src="../img/heart_01.png"/>
            <img v-else src="../img/heart_02.png"/>
            <span>{{item.follow}}</span>
          </div>
        </div>
      </div>
    </div>
    <footer>
      <div 
        class="pre"
        @click="changePage('pre')">
        <img src="../img/list-pagination.png"/>第一页
      </div>
      <span
        :class="{ activePage: currentPage == 1}"
        @click="changePage(1)">
        1
      </span>
      <span
        :class="{ activePage: currentPage == 2}"
        @click="changePage(2)">
        2
      </span>
      <span
        :class="{ activePage: currentPage == 3}"
        @click="changePage(3)">
        3
      </span>
      <span
        :class="{ activePage: currentPage == 4}"
        @click="changePage(4)">
        4
      </span>
      <span
        :class="{ activePage: currentPage == 5}"
        @click="changePage(5)">
        5
      </span>
      <div 
        class="next"
        @click="changePage('next')">
        尾页<img src="../img/list-pagination.png"/>
      </div>
    </footer>
  </div>
</template>
<script>
export default {
  data () {
    return {
      list: [
        [
          {
            id: 0,
            poster: require('../img/poster.jpg'),
            avatar: require('../img/avatar.jpeg'),
            nick: '15岁的日天',
            isFollowed: true,
            follow: '1314'
          },{
            id: 1,
            poster: require('../img/poster.jpg'),
            avatar: require('../img/avatar.png'),
            nick: '15岁的日天',
            isFollowed: false,
            follow: '999.9w'
          },{
            id: 2,
            poster: require('../img/poster.jpg'),
            avatar: require('../img/avatar.png'),
            nick: '西瓜',
            isFollowed: false,
            follow: '1314'
          },{
            id: 3,
            poster: require('../img/poster.jpg'),
            avatar: require('../img/avatar.jpeg'),
            nick: '请叫我天坑哥哥',
            isFollowed: true,
            follow: '999.9w'
          },{
            id: 4,
            poster: require('../img/poster.jpg'),
            avatar: require('../img/avatar.jpeg'),
            nick: '请叫我天坑哥哥',
            isFollowed: true,
            follow: '1314'
          },{
            id: 5,
            poster: require('../img/poster.jpg'),
            avatar: require('../img/avatar.jpeg'),
            nick: '15岁的日天',
            isFollowed: false,
            follow: '1314'
          }
        ]
      ],
      currentPage: 1
    }
  },
  methods: {
    changePage (val) {
      if (Number.isInteger(val)&&this.currentPage != val) {
        this.currentPage = val
      } else if (val == 'pre') {
        this.currentPage = 1
      } else if (val == 'next') {
        this.currentPage = 5
      }
    },
    follow (item) {
      item.isFollowed = true
    }
  }
}
</script>

