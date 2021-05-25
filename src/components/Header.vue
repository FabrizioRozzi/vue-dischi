<template>
  <div class="wrap-header d-flex align-items-center">
    <img src="@/assets/img/logo.png" alt="logo">
  </div>
</template>

<script>
export default {
  name : 'Header'
}
</script>

<style lang="scss" scoped>

  .wrap-header{
    width: 100%;
    height: 100px;
  
    background-color: #2E3A46;
    img{
      height: 80px;
      background-color: #2E3A46;
      padding-left: 10px;
    }
  }

</style>