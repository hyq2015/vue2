<template>
  <div>
    <input type="radio" :checked="checkStatus"/>
  </div>
</template>
<script>
  export default {
    props:['checkStatus']
  }
</script>
