<template>
  <div class="TabNavBar">
    <div class="content">
        <i class="iconfont" @click="changeColor('home')" :class="{icolor: this.$store.state.tab_home}">&#xe617;</i>
        <i class="iconfont" @click="changeColor('search')" :class="{icolor: this.$store.state.tab_search}">&#xe777;</i>
        <i class="iconfont" @click="changeColor('bell')" :class="{icolor: this.$store.state.tab_bell}">&#xe616;</i>
        <i class="iconfont" @click="changeColor('people')" :class="{icolor: this.$store.state.tab_people}">&#xe6b3;</i>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TabNavBar',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    changeColor(val) {
      switch(val) {
        case 'home':
          this.$store.commit('tab_home',true)
          this.$store.commit('tab_search',false)
          this.$store.commit('tab_bell',false)
          this.$store.commit('tab_people',false)
        break;
        case 'search':
          this.$store.commit('tab_home',false)
          this.$store.commit('tab_search',true)
          this.$store.commit('tab_bell',false)
          this.$store.commit('tab_people',false)
        break;
        case 'bell':
          this.$store.commit('tab_home',false)
          this.$store.commit('tab_search',false)
          this.$store.commit('tab_bell',true)
          this.$store.commit('tab_people',false)
        break;
        case 'people':
          this.$store.commit('tab_home',false)
          this.$store.commit('tab_search',false)
          this.$store.commit('tab_bell',false)
          this.$store.commit('tab_people',true)
        break;
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.TabNavBar {
  height:60px;
  position: fixed;
  bottom:0;
  width:100%;
  background-color:white;
  box-shadow:0 -0.1px 0.1px 0 rgba(0,0,0,.1);
}
.content {
  height:inherit;
  width:inherit;
  display:flex;
  align-items: center;
  justify-content: space-around;
}
i{
  color: rgba(189, 195, 199,1.0);
  font-size: 25px;
}
.icolor{
  color: rgba(52, 152, 219,1);
}


</style>
