<template>
  <div class="shopcart">
    <div class="content">
      <div class="content-left">
        <div class="logo-wrapper">
          <div class="logo"><i class="icon-shopping_cart"></i></div>
        </div>
        <div class="price">￥0元</div>
        <div class="desc">另需配送费￥{{deliveryPrice}}元</div>
      </div>
      <div class="content-right"></div>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      deliveryPrice: {
        type: Number,
        default: 0
      },
      minPrice: {
        type: Number,
        default: 0
      }
    }
  }
</script>

<style lang="stylus" rel="stylus">
  .shopcart
    z-index: 99
    position: fixed
    bottom: 0
    left: 0
    width: 100%
    height: 48px
    .content
      display: flex
      background: #141d27
      font-size: 0
      .content-left
        flex: 1
        .logo-wrapper
          display: inline-block
          position: relative
          top: -10px
          margin: 0 12px
          padding: 6px
          width: 56px
          height: 56px
          box-sizing: border-box
          vertical-align: top
          border-radius: 50%
          background: #141d27
          .logo
            width: 100%
            height: 100%
            border-radius: 50%
            text-align: center
            background: #2b343c
            .icon-shopping_cart
              line-height: 44px
              font-size: 24px
              color: #80858a
        .price
          display: inline-block
          vertical-align: top
          margin-top: 12px
          line-height: 24px
          padding: 0 12px 0 0
          box-sizing: border-box
          border-right: 1px solid rgba(255, 255, 255, .1)
          font-size: 16px
          font-weight: 700
          color: rgba(255, 255, 255, .4)
        .desc
          display: inline-block
          vertical-align: top
          margin: 12px 0 0 12px
          line-height: 24px
          color: rgba(255, 255, 255, .4)
          font-size: 10px
      .content-right
        flex: 0 0 105px
        width: 105px
</style>
