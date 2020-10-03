<template>
  <div id="app">
    <GetUserData/>
  </div>
</template>

<script>
import GetUserData from './components/GetUserData.vue';

export default {
  name: 'App',
  components: {
    GetUserData,
  }
}
</script>
  
<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    display: flex;
    justify-content: center;
    align-items: center;
    background: #dedede;
    font-family: "Lato", sans-serif;
    line-height: 1.4;
  }
  
  #app {
    margin-top: 50px;
    background-color: #f03482;
    border-radius: 10px;
    padding: 20px;
    width: 940px;
    border: 1px rgb(240, 238, 238) solid;
    -webkit-box-shadow: 10px 16px 30px -14px rgba(179,179,179,1);
    -moz-box-shadow: 10px 16px 30px -14px rgba(179,179,179,1);
    box-shadow: 10px 16px 30px -14px rgba(179,179,179,1);
  }

</style>- =)
