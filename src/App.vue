<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- v-for循环数组和对象的区别 -->
    <!-- <ul>
      <li v-for="value in msg" :key="value.id">{{value}}</li>
    </ul> -->
    <input type="text" v-model="msg.firstname">
    <input type="text" v-model="msg.lastname">
    {{changename}}
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      // watch
      // msg:{ firstname: "", lastname: "",changename:''}
      // computed
      msg: { firstname: "", lastname: "",  }
    };
  },
  // 实时监控data里面的属性，变化时呈现在span标签上
  // watch: {
  //   "msg.firstname": function() {
  //     // console.log(this);
  //     // console.log(this.msg.firstname);
  //     this.msg.changename = this.msg.firstname + this.msg.lastname;
  //   },
  //   "msg.lastname":function(){
  //     this.msg.changename = this.msg.firstname + this.msg.lastname;
  //   }
  // },
  // 使用computed实时计算相应值改变 会产生一个新的属性值
  computed: {
    changename: function() {
      // console.log(this);
      return this.msg.firstname + this.msg.lastname;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1,
h2 {
  font-weight: normal;
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
