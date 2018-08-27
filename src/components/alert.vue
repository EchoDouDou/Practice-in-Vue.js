<template>
  <div>
  <button @click = "alert">点击按钮</button>
  <div class="dialog" v-if="isshow">
    <div class="dialog-cover"></div>
    <transition>
      <div class="dialog-content">
        <header class="dialog-back">
          {{tishi}}
        </header>
        <div class="dialog-main">
          {{con}}
        </div>
        <footer class="close" @click = "close">
          Close
        </footer>
      </div>
    </transition>
  </div>
  </div>
</template>
<script>
  export default {
    props:{
      con:String
    },
    data(){
      return{
        tishi:'Alert',
        isshow:false
      }
    },
    methods:{
      close:function () {
        this.isshow = false
      },
      alert:function () {
        this.isshow = true
      }
    }
  }
</script>
<style>
  .dialog {
    position:absolute;
    top:50%;
    left:50%;
    margin:-150px 0 0 -200px;
    width:400px;
    height:300px;
    font-size: 16px;
    color: darkblue;
  }
  .dialog-cover {
    background: rgba(0,0,0, 0.8);
    position: fixed;
    z-index: 200;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
  .dialog-content{
    border-radius: 5%;
    top:50%;
    left:50%;
    transform: translate(-50%,-50%);
    position: absolute;
    height: 200px;
    width: 250px;
    top: 35%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    z-index: 300;
    background-color: lightpink;
  }
  .dialog-back{
    color: wheat;
    top:0;
    position: absolute;
    width: 100%;
    font-size:28px;
    line-height: 40px;
    text-align: center;
    background-color: yellow;
  }
  .dialog-main{
    color: wheat;
    position: absolute;
    width: 100%;
    font-size:28px;
    height: 130px;
    white-space:normal;
    word-break:break-all;
    word-wrap:break-word;
  }
  .close{
    color: wheat;
    position: absolute;
    bottom:0;
    width: 100%;
    font-size:20px;
    line-height: 30px;
    text-align: center;
    background-color: yellow;
  }
</style>
