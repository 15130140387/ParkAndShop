<template>
  <div style="margin-top: 20px">
    <p style="font-size:12px; font-weight:700; color: #fff; padding: 3px 5px; height: 25px; line-height: 25px; background: rgb(63,127,206)">The Goods</p>

    <div style="width: 1000px; height: 590px; margin: 0px auto;">
      <img v-bind:src="data.portraitURL" style="float: left; width: 418px; height: 418px"/>
      <div style="float: left; margin-left: 20px; width: 552px;">
        <p style="color: #000; font-size: 20px; font-weight: 700;  padding: 20px 0px;">{{ data.pName }}</p>
        <div style="background-image: url(data:image/png;base64,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);
                width: 552px; height: 70px;">
          <p style="float: left; line-height: 70px; color: rgb(153, 153, 153); font-size: 12px; font-weight: 400; margin-left: 10px">Price：</p>
          <p  style="line-height: 70px;color: rgb(255, 0, 54); font-size: 30px; font-weight: 700;">¥{{ data.price }}</p>
        </div>
        <div style="width: 552px; margin-top: 20px; float: right; height: 162px;">
          <div style="width: 552px; background: rgb(237, 237, 237); height: 132px; border-radius: 5px">
            <p style="padding-top: 15px; margin-bottom: 10px; margin-left: 20px; font-size: 14px; font-weight: 600; color: #666;">Good Description:</p>
            <p style="margin-top: 10px; margin-left: 20px; margin-right: 20px; font-size: 13px; font-weight: 400; color: #666;">{{ data.description }}</p>
          </div>
        </div>
        <p>Number：{{ data.num }}</p>
        <div style="margin-top: 20px">
          <button style="float: right; width: 178px; height: 38px; margin-left: 5px;border: none; background: rgb(255,0,54); color: #fff; font-weight: 400; font-size: 16px" v-on:click="setTop10()">Set Top10</button>
        </div>
        <loading v-show="isLoad"/>
      </div>
    </div>
  </div>
</template>

<script>
import Loading from '@/components/common/Loading'

export default {
  components: {Loading},

  mounted () {
    this.data = this.$route.params.data
    this.$emit('childByValue', this.data.sID)
    console.log(this.data)
  },

  data: function () {
    return {
      data: {},
      isLoad: false
    }
  },

  methods: {
    setTop10: function () {
      // 给后台返回商品id， 让后台加入top10
      this.isLoad = true
      this.$http.get(this.URL + 'm/product_to_top10?id=' + this.data.pID)
        .then((data) => {
          this.isLoad = false
          if (data.body.code === 101) {
            alert('Set Succeed')
          } else {
            alert('Set Failed')
          }
        })
        .catch(() => {
          this.isLoad = false
        })
      event.stopPropagation()
    },
    setTop5: function (info) {
      // 给后台传入店铺的id，设置为top5店铺
      this.isLoad = true
      this.$http.get(this.URL + 'm/seller_to_top5?id=' + info.id)
        .then((data) => {
          console.log(data)
          this.isLoad = false
          if (data.body.code === 101) {
            alert('Set Succeed')
          } else {
            alert('Set Failed')
          }
        })
        .catch(() => {
          this.isLoad = false
        })
      event.stopPropagation()
    }
  }
}
</script>

<style scoped>

  *{
    margin: 0px;
    padding: 0px;
    display: block;
  }

</style>
