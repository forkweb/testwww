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
            <li onclick="animateScrollTo(document.querySelector('.ElementDemo-element'))">Home</li>
            <li onclick="animateScrollTo(document.querySelector('.ElementDemo-element'))">About us</li>
            <li onclick="animateScrollTo(document.querySelector('.ElementDemo-element'))">Portfolio</li>
            <li onclick="animateScrollTo(document.querySelector('.ElementDemo-element'))">Contact</li>
          </ul>

        </div>

      </div>

      <div class="container">

        <div class="title-container">
          about
        </div>

        <p class="about-text">
          We specialize in contemporary, functional, and stunning websites with design that really brings that "WOW" factor. <br>
          In our design process, we make sure to stay one step ahead of the latest trends, <br>
          never forgetting to abide by key web standards.
        </p>

        <div class="about-tehnology">

          <div class="about-tehnology__item">
            <div class="about-tehnology__item-image">
            <img src="~@/assets/img/web.png" alt="">
            </div>
            <div class="about-tehnology__item-info">
              <div class="about-tehnology__item-title">WEB</div>
              <p>
                We tend to deliver unique and 
                functional design, through 
                innovation and creativity.
              </p>
            </div>
          </div>

          <div class="about-tehnology__item">
            <div class="about-tehnology__item-image">
            <img src="~@/assets/img/app.png" alt="">
            </div>
            <div class="about-tehnology__item-info">
              <div class="about-tehnology__item-title">iOS AND ANDROID</div>
              <p>
                We seek to bring new businesses and 
                customers closer together through valuable 
                insights and proper targeting.
              </p>
            </div>
          </div>

          <div class="about-tehnology__item">
            <div class="about-tehnology__item-image">
            <img src="~@/assets/img/marketing.png" alt="">
            </div>
            <div class="about-tehnology__item-info">
              <div class="about-tehnology__item-title">MARKETING</div>
              <p>
                We’ll help you establish the right goals 
                and build the right paths. Success depends 
                on setting the right intention.
              </p>
            </div>
          </div>

        </div>
        
      </div>

    </section>


  <template> 
    <Portfolio/>
  </template>


  <section class="partners ElementDemo-element">
    <div class="container">
      <div class="title-container">
        dfsddfsdfsdfsd
      </div>
    </div>
  </section>

  
  </div>
</template>

<script>
import Portfolio from './components/Portfolio.vue'
import animateScrollTo from 'animated-scroll-to';
import jQuery from "jquery";


export default {
  name: 'App',
  components: {
    Portfolio
  },
  watch: {
    animateScrollTo() {
      this.animateScrollTo();
    }
  },
  methods: {
    animateScrollTo(){
      animateScrollTo(0).then(hasScrolledToPosition => {
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
    fixedMenu(){
      (function($) {
        $(window).bind('scroll', function() {
        var navHeight = $( window ).height() - 30;
          if ($(window).scrollTop() > navHeight) {
            $('.nav').addClass('fixed');
          }
          else {
            $('.nav').removeClass('fixed');
          }
      });
      })(jQuery);
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
    this.fixedMenu();
  },
}
</script>

<style lang="scss" type="text/scss">
  @import "./style/main.scss";
</style>
