<template>
  <div class="home">
    <object id="CommonLiveDetectionOCX" ref="htjcObj" class="ocx" classid="CLSID:F968BF6F-304F-435D-A387-A9AB273D1FD7"></object>
  </div>
  
  <!-- TODO
  <script type="text/javascript" for="CommonLiveDetectionOCX" event="LiveDetectStatusEvent(ULONG)">
    checkHtjc(ULONG)
  </script> -->
  
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      obj: null,
      pic: null
    }
  },
  methods: {
    
  },
  mounted(){
    this.obj = this.$refs.htjcObj
    window.addEventListener('event', this.handleMessage)
    setTimeout(() => {
      this.obj.StartVedio()
    }, 1000);
  },
  handleMessage (event) {
    // 根据上面制定的结构来解析iframe内部发回来的数据
    console.log(event)
    const data = event.data
    console.log(data)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
  .home
    width: 100%
    height: 100%
    
</style>
