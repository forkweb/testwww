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


    <section class="about">

      <div class="menu">

        <div class="container">

          <ul class="nav">
            <li onclick="animateScrollTo(document.querySelector('.ElementDemo-element'))">CLICK</li>
          </ul>

        </div>

      </div>

      <div class="container">

        <div class="title">
          about
        </div>
        
      </div>

    </section>


  <template> 
    <Portfolio/>
  </template>


  <section class="partners ElementDemo-element">
    <div class="container">
      asdasd
    </div>
  </section>

  
  </div>
</template>

<script>
import Portfolio from './components/Portfolio.vue'
import animateScrollTo from 'animated-scroll-to';


export default {
  name: 'App',
  components: {
    Portfolio
  },
  methods: {
    animateScrollTo(){
      animateScrollTo(500).then(hasScrolledToPosition => {
        // scroll animation is finished

        // "hasScrolledToPosition" indicates if page/element
        // was scrolled to a desired position
        // or if animation got interrupted
        if (hasScrolledToPosition) {
          // page is scrolled to a desired position
        } else {
          // scroll animation was interrupted by user
          // or by another call of "animateScrollTo"
        }
      });
    },
    animate_text() {
      console.log("asdasdasdasda");
    },
  },
  create(){
    this.animateScrollTo();
  },
  mounted() {
    this.animate_text();
    this.animateScrollTo();
  },
}
</script>

<style lang="scss" type="text/scss">
  @import "./style/main.scss";
</style>
