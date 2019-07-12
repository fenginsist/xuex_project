<template>
  <div id="app">

    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
      <h1>{{ count }}</h1>
      <h5>{{ myCount }}</h5>
    </div>

<!-- 路由地区-->
    <router-view/>

  </div>
</template>

<script>
  import { mapState, mapGetters } from "vuex";

  export default {

    name: "App",
    computed: {
      // 这是没有加 module 之前，一共就一个状态管理，加了 module，状态变多了。则需要修改
      //...mapState(["count"]),

      ...mapState({
        count: state => {
          return state.app.count
        }
      }),

      ...mapGetters(["myCount"]),
      // ...mapGetters()
    }

  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
