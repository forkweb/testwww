<template>
  <div id="app">



    <section class="header el1">
      
      <div class="container">

        <div class="logo"><img src="~@/assets/img/logo.png" alt=""></div>

        <div class="head-title">
          <h1>Clear, smart, attractive design</h1>
          <h2>for your app, logo, website</h2>
        </div>

        <div class="head-control">
          <button class="btn" onclick="animateScrollTo(document.querySelector('.el2'))">read more</button>

          <i class="icon-down-open-big" onclick="animateScrollTo(document.querySelector('.el2'))"></i>

        </div>

      </div>

    </section>


    <section class="about">

      <div class="menu">

        <div class="container">

          <ul class="nav">
            <li onclick="animateScrollTo(document.querySelector('.el1'))">Home</li>
            <li onclick="animateScrollTo(document.querySelector('.el2'))">About us</li>
            <li onclick="animateScrollTo(document.querySelector('.el3'))">Portfolio</li>
            <li onclick="animateScrollTo(document.querySelector('.el4'))">Contact</li>
          </ul>

        </div>

      </div>

      <div class="container el2">

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
      <div class="title-mini">
        Our partners
      </div>

      <div class="partners-content">
        <img src="~@/assets/img/partner1.png" alt="">
        <img src="~@/assets/img/partner2.png" alt="">
        <img src="~@/assets/img/partner3.png" alt="">
        <img src="~@/assets/img/partner4.png" alt="">   
      </div>

    </div>
  </section>




    <section class="contact el4">
    <div class="container">
        <div class="title-container">
          Contact
        </div>

      <div class="contact-content">
        <div class="contact-content__form">

          <div class="el_input">
            <input type="text" placeholder="Your Name">
            <input type="email" placeholder="Your Email">
          </div>
          <textarea placeholder="Message"></textarea>

          <div class="contact-content__send">
            <button class="btn">Send</button>
          </div>

        </div>
        <div class="contact-content__info">
          <p>
            Have an idea for a project? Just looking to 
            explore and see the possibilities?
            I'm here to help.
          </p>
          <p><strong>Postma Elena</strong></p>
          <div class="contact-content__icon">
            <a href="https://vk.com/fork_web" target="_blank"><i class="icon-vkontakte"></i></a>
            <a href="https://www.instagram.com/fork_web/" target="_blank"><i class="icon-instagram-filled"></i></a>
          </div>
          <p>e-mail: <strong>postma.elena@gmail.com</strong></p>
        </div>

      </div>

      <div class="contact-content">

      </div>

    </div>
  </section>






    <section class="footer ElementDemo-element">
    <div class="container">

      <div class="footer-content">
        <div class="logo"><img src="~@/assets/img/logo_footer.png" alt=""></div>
        
        <ul class="footer-content__link">
          <li><a href="/">Home</a></li>
          <li><a href="https://vk.com/fork_web" target="_blank">Vkontakte</a></li>
          <li><a href="https://www.instagram.com/fork_web/" target="_blank">Instagram</a></li>
          <li><a href="https://codepen.io/" target="_blank">Codepen</a></li>
        </ul>
        <div class="footer-content-copyright">
          © 2020. All Rights Reserved 
        </div>

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
      console.log("test");
    },
  },
  create(){
    this.animateScrollTo();
  },
  mounted() {
    this.animate_text();
    this.animateScrollTo();
    this.fixedMenu();

    var textarea = document.querySelector('textarea');
    var initialHeight = 5;
    var resize = function resize() {
      textarea.style.height = initialHeight + 'px';
      var height = textarea.scrollHeight;
      textarea.style.height = height + initialHeight + 'px';
    };
    resize();
    textarea.addEventListener('input', resize);
    
  },
}
</script>

<style lang="scss" type="text/scss">
  @import "./style/main.scss";
</style>
