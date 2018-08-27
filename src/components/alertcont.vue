<template>
  <div class="wrapper">
    <Alert :con="mes"></Alert>
  </div>
</template>
<script>
  import Alert from './alert.vue'
  export default {
    data(){
      return{
        mes:"I can see you"
      }
    },
    components:{
      Alert
    }
  }
</script>
