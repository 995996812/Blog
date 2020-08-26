<template>
  <div>
    <Navbar></Navbar>
    <div class="content">
       <h2>{{mydata.title}}</h2>
       <div class="boss" v-for="(item, index) in mydata.mygq" :key="index">
         <div class="boss-content">
          <img :src="require('@/'+item.src)" alt="">
         </div>
       </div>
    </div>
    <div class="content">
       <h2>myGQ</h2>
       <div class="boss" v-for="(item, index) in mydata.mygq" :key="index">
         <div class="boss-content">
          <img :src="require('@/'+item.src)" alt="">
         </div>
       </div>
    </div>
    <TabBar></TabBar>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue'
import TabBar from '@/components/TabBar.vue'

// @ is an alias to /src

export default {
  name: 'index',
  components: {
    Navbar,
    TabBar
  },
  data () {
    return {
      'mydata': {}
    }
  },
  mounted () {
    this.$axios.get('mydata.json', {
    })
      .then(response => {
        this.mydata = response.data.data
      })
      .catch(error => {
        console.log(error)
      })
  }
}
</script>

<style lang="scss">
body {
  background: rgb(224, 224, 224);
}

.content {
  overflow:hidden;
  margin: 25px 5vw;
  background: white;
  h2 {
    // 上 右 下 左
    margin: 25px 0px 25px 25px;
    font-size: 30px;
    text-align: left;
  }
  .boss {
    float: left;
    margin-bottom: 20px;
    display: flex;
    justify-content: space-between;
    img {
      margin-left: 14px;
      position: relative;
      width: 240px;
      border: solid 1px gray;
      display: block;
      }
  }
}
</style>
