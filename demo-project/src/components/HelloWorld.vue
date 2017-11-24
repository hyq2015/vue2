<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
      <br>
      <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>
    <input type="text" v-focus @input="inputChange" placeholder="测试输入框"/>
    <div v-cloak>{{calculateMoney(9)}}{{date.substr(0,10)}}</div>
    <commonCheckbox :check-status="originStatus"  @callParent="receiveChildClickEvent"></commonCheckbox>
  </div>

</template>

<script>
import commonCheckbox from './checkbox.vue'
export default {
  name: 'HelloWorld',
  components:{commonCheckbox},
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      date:'2017-09-08 12:00:20',
      originStatus:false
    }
  },
  created(){

  },
  directives: {
    focus: {
      // 指令的定义
      inserted:function(el) {
        console.log('指令注入了啊');
        el.focus()

      }
    }
  },
  methods:{
    calculateMoney(money){
      return 10
    },
    inputChange(e){
      console.log(e.target.value)
    },
    receiveChildClickEvent(para){
      console.log('接收到来自子组件的事件')
      console.log(para)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
[v-cloak] {
  display: none;
}
h1, h2 {
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
