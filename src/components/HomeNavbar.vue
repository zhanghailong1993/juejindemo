<template>
  <div class="HomeNavBar">
    <ul>
        <li id="homeref" @click="home">首页</li>
        <li @click="android">产品</li>
        <li @click="frontend">前端</li>
        <li @click="ios">iOS</li>
    </ul>
    <div id="indicator" :style="{left:left}"></div>
  </div>
</template>

<script>
export default {
  name: 'HomeNavBar',
  data () {
    return {
      left: ''
    }
  },
  methods: {
    init:function () {
      this.left = document.getElementById('homeref').offsetLeft+3+'px'
    },
    home() {
      this.left = event.currentTarget.offsetLeft+3+'px'
      this.$store.commit('changeNav','nav_home');
    },
    android() {
      this.left = event.currentTarget.offsetLeft+3+'px'
      this.$store.commit('changeNav','nav_prd');
    },
    frontend() {
      this.left = event.currentTarget.offsetLeft+3+'px'
      this.$store.commit('changeNav','nav_front')
    },
    ios() {
      this.left = event.currentTarget.offsetLeft+3+'px'
      this.$store.commit('changeNav','nav_ios')
    }
  },
  mounted() {
    this.init();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.HomeNavBar {
  width:100%;
  height:60px;
  background-color:#3498db;
  position:fixed;
  font-size:14px;
  font-weight: 400;
}
#indicator{
  width:60px;
  height: 2px;
  background-color: white;
  position: absolute;
  bottom: 0;
}
ul {
  list-style:none;
  margin:0;
  padding-left:20px;
}
ul li {
  display:inline-block;
  color:white;
  padding:0 20px;
  margin-top:20px;
}



</style>
