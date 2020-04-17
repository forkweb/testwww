<template>
  <div id="app">



    <section class="header">
      
      <div class="container">

        <div class="logo"><img src="~@/assets/img/logo.png" alt=""></div>

        <div class="head-title">
          <h1>Clear, smart, attractive design</h1>
          <h2>for your app, logo, website</h2>
        </div>

        <div class="head-control">
          <button class="btn">read more</button>

          <i class="icon-down-open-big"></i>

        </div>

      </div>

    </section>


  <template> 
    <Portfolio/>
  </template>

  
  </div>
</template>

<script>
import Portfolio from './components/Portfolio.vue'

export default {
  name: 'App',
  components: {
    Portfolio
  }
}
</script>

<style lang="scss" type="text/scss">
  @import "./style/main.scss";
</style>
