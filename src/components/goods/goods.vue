<template>
  <div class="goods">
    <div class="menu-wrapper">
      <ul>
        <li v-for="item in goods">
          <span class="text">{{item.name}}</span>
        </li>
      </ul>
    </div>
    <div class="foods-wrapper"></div>
  </div>
</template>
<script>
  const ERR_OK = 0

  export default {
    // 拿到父组件的数据
    props: {
      seller: {
        type: Object
      }
    },
    // goods 存入data() 函数里面 后面处理
    data() {
      return {
        goods: []
      }
    },
    // 生命周期钩子
    created() {
      this.$http.get('/api/goods').then((response) => {
        response = response.body
        if (response.errno === ERR_OK) {
          this.goods = response.data
          console.log(this.goods)
        }
      })
    }
  }
</script>
<style lang="stylus" type="text/stylus">
  .goods
    display: flex
    position: absolute
    top: 174px
    bottom: 46px
    width: 100%
    overflow: hidden
    .menu-wrapper
      flex: 0 0 80px
      width: 80px
      background: #f3f5f7
    .foods-wrapper
      flex: 1
      background: #fff;
</style>
