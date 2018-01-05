<template>
  <transition name="slide">
    <div v-if="seen" class="ReadArticle" :style="{height:height}">
      <div class="header">
        <div style="display:flex;align-items:center;">
          <i class="iconfont" style="font-size: 25px;margin-left: 15px" @click="hidePage()">&#xe62e;</i>
          <img style="width:40px;height:40px;border-radius:20px;margin-left:30px;" src="https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3743909004,3340426306&fm=27&gp=0.jpg" alt="">
          <span style="font-size:14px;font-weight:300;margin-left:8px;">风青杨ELSE</span>
        </div>
        <div style="font-size:25px;margin-right:10px;color:rgba(0,0,0,.6)">
            <i class="iconfont" style="margin-right: 10px;font-size: 23px">&#xe612;</i>
            <i class="iconfont">&#xe600;</i>
        </div>
      </div>
      <div class="content">
        <iframe src="https://mp.weixin.qq.com/s/PUdfChwnon4hAZGTUvR8Qw" frameborder="0" width="100%" :style="{height:iframeHeight}"></iframe>
      </div>
      <div class="footer">
        <i class="iconfont" style="margin-left: 20px;color: #2ecc71">&#xe791;</i>
         <i class="iconfont">&#xe659;</i>
         <i class="iconfont">&#xe643;</i>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: 'ReadArticle',
  props:["seen"],
  data () {
    return {
      height:window.innerHeight+'px',
       iframeHeight: window.innerHeight-110+'px'
    }
  },
  methods: {
    hidePage() {
      this.$store.commit('showReadArticle',false)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.ReadArticle {
  position:fixed;
  top:0;
  width:100%;
  z-index:100;
  background:white;
  box-shadow:-0.1px 0.1px 2px rgba(0,0,0,.4);
}
.header {
  width:100%;
  display:flex;
  height:60px;
  justify-content: space-between;
  align-items:center;
  position:fixed;
  top:0;
  z-index:2;
  background:white;
}
.content{
    margin-top: 62px;
    padding-bottom: 46px;
  }
.footer {
  width:100%;
  height:50px;
  background:white;
  position:fixed;
  bottom:0;
  display: flex;
  align-items: center;
  font-size:25px;
  box-shadow: 0 -0.1px 1px 0 rgba(0,0,0,0.4);
}
.footer i{
    margin: 0 12px;
    color: rgba(0,0,0,0.6);
  }
  @keyframes sliderIn {
    from {
      left:100%
    }
    to {
      left:0
    }
  }
  @keyframes sliderOut {
    from {
      left:0
    }
    to {
      left:100%
    }
  }
.slide-enter-active {
  animation:slideIn .5s;
  -webkit-animation: sliderIn .5s;
  -o-animation: sliderIn .5s;
  -moz-animation: sliderIn .5s;
}
.slide-leave-active {
  animation:sliderOut .5s;
  -webkit-animation: sliderOut .5s;
  -o-animation: sliderOut .5s;
  -moz-animation: sliderOut .5s;
}
</style>
