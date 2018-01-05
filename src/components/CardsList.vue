<template>
  <div>
    <div style="margin-top:5px;background:white;padding:10px;box-shadow:0 0.1px 1px 0 rgba(0,0,0,.4)" v-for="card in cards" @click="showReadArtcile">
      <div style="display:flex;align-items:center;justify-content:space-between">
        <div style="display:flex;align-items:center;margin-left:10px;">
          <img :src="card.image" alt="" style="width:30px;height:30px;border-radius:15px;">
          <span style="margin-left:5px;font-size:12px;">{{card.auth}}</span>
        </div>
        <p style="font-size:12px;">{{card.category}}</p>
      </div>
      <h4 style="margin-left:10px;margin-top:10px;">{{card.title}}</h4>
      <p style="display:-webkit-box;-webkit-box-orient:vertical;-webkit-line-clamp:3;overflow:hidden;padding: 0 10px;padding-right:20px;font-size: 14px;color: rgba(189, 195, 199,1.0);margin-top:5px;">{{card.description}}</p>
      <p style="color: rgba(189, 195, 199,1);font-size: 12px;padding-left: 10px;margin-top: 10px"><span><i class="iconfont">&#xe751;</i><span> {{card.love}}</span></span><span style="margin-left: 20px"><i class="iconfont">&#xe671;</i><span>评论</span></span></p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardsList',
  props: ['cards'],
  data () {
    return {

    }
  },
  methods: {
    showReadArtcile() {
      this.$store.commit('showReadArticle',true)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


</style>
