<template>
  <div class="hello">
<!--    <h1>{{ msg }}</h1>-->
    <button @click="increase">增加</button>
    <button @click="decrease">减少</button>
  </div>
</template>

<script>

import { mapMutations, mapActions } from "vuex"
import { INCREASE, DECREASE } from "@/store/mutation-type"

export default {
  name: 'HelloWorld',
  /*props: {
    msg: String
  },*/
  methods:{
    ...mapMutations([INCREASE,DECREASE]),
    ...mapActions(['myIncrease','myDecrease']),
    async increase() {
      this.$store.commit(INCREASE, 1);
      // this.$store.state.count += 1;
      // this.increment();
      //   const product = await this.myIncrease({
            // id:123,
        // });   // 不加 await 会 打印出 promise 方法，里面有这个返回来的数据 （数组）
        // console.log(product);
    },

    decrease(){
      this.$store.commit(DECREASE, 1);
      //   this.$store.state.count -= 1;
      //   this.decrement();
      //   this.myDecrease();
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
