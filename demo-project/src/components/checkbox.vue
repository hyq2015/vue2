<template>
    <div>
        <input type="checkbox" :checked="checkStatus"/>
        <button @click="clickChildBtn">点击子组件</button>
    </div>
</template>
<script>
  export default {
    props:['checkStatus'],
    created(){
      console.log(this.checkStatus)
    },
    methods:{
      clickChildBtn(){
        this.$emit('callParent','123')
      }
    }
  }
</script>

