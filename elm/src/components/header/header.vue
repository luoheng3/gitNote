<template>
  <div class="header">
    <div class="content-wrapper">
      <div class="avatar">
        <img :src="seller.avatar" alt="" width="64" height="64">
      </div>
      <div class="txt">

      </div>
    </div>
  </div>
</template>
<script>
  export default {
    props: ['seller']
  }
</script>
<style>
  .header{
    width: 100%;
    background: rgba(0,0,0,.5);
  }
  .header .content-wrapper{
    overflow: hidden;
  }
  .header .content-wrapper .avatar{
    float: left;
    width: 64px;
    height: 64px;
    margin:24px 16px 18px 24px;
  }
  .header .content-wrapper .avatar img{
    display: block;
    width: 100%;
    height: 100%;
  }
</style>
