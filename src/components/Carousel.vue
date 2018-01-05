<template>
  <div class="">
    <el-carousel height="150px" arrow="never">
      <el-carousel-item v-for="image in images" :key="image">
        <img :src="image" alt="" style="width:inherit;height:inherit">
      </el-carousel-item>
    </el-carousel>
  </div>
</template>

<script>
export default {
  name: 'Carousel',
  data () {
    return {
      images:[
        "http://wimg.huodongxing.com/logo/201712/3417245094000/772905617658290_v2.jpg@!wmlogo",
        "http://wimg.huodongxing.com/logo/201712/2417973718300/912902667738841.jpg@!wmlogo",
        "https://pub-files.jinshuju.net/hi/20171207203419_655947@hixlargeRetina"
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
