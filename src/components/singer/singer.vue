<template>
  <div class="singer">
    歌手页面
  </div>
</template>

<script>
  import {getSingerList} from 'api/singer'
  import {ERR_OK} from 'api/config'

  export default {
    data() {
      return {
        singers: []
      }
    },
    created() {
      this._getSingerList()
    },
    methods: {
      _getSingerList() {
        getSingerList().then((res) => {
          if (res.code === ERR_OK) {
            console.log(res.data.list)
          }
        })
      }
    }
  }
</script>

<style lang="stylus">
  .singer
    poaition: fixed
    top: 88px
    bottom: 0
    width: 100%
</style>