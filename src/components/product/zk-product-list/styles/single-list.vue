<template>
  <view class="zk-product">
    <view class="common" v-for="(item,index) in viewModel" :key="index" @click="linkTo(item)">
      <view class="common-left">
        <view class="common-image">
          <img :src="$api.baseUrl()+item.thumbnailUrl" alt="" v-lazy>
        </view>
      </view>
      <view class="common-right">
        <view class="common-title-product">{{item.name}}</view>
        <view class="common-intro">库存 {{item.stock}}</view>
        <view class="common-price-nologin">￥{{item.price}}</view>
        <view class="common-foot" v-if="false">
          <view class="common-a">
            <view class="common-qiang">抢</view>
            <view class="common-price">￥{{item.price}}</view>
          </view>
          <view class="common-hot">立即抢购</view>
        </view>
      </view>
    </view>
  </view>
</template>


<script>
  export default {
    props: {
      viewModel: {}
    },
    mounted () {
    },
    methods: {
      // 下拉菜单事件
      scrollView () {
      },
      linkTo (item) {
        this.$api.to(`/product/show?id=${item.id}`)
      }
    }
  }
</script>

<style lang="scss" scope>
  @import "./single-list.scss";
  .zk-product {
    padding: 10px 10px 0 10px;
  }
</style>
