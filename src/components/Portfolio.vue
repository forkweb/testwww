<template>
  <section class="portfolio el3">
    <div class="container">
      <div class="title-container">PORTFOLIO</div>

      <div class="portfolio-content">

        <div class="portfolio-content__control">
          <button class="portfolio-content__control-btn" type="button" data-filter="all">All</button>
          <button class="portfolio-content__control-btn" type="button" data-filter=".category-a">Web</button>
          <button class="portfolio-content__control-btn" type="button" data-filter=".category-b">Apps</button>
          <button class="portfolio-content__control-btn" type="button" data-filter=".category-c">Other</button>
        </div>

        <div class="portfolio-content__items">

          <div class="blabla coub_work mix category-a" data-order="1"><a class="image-popup-zoom" title="Это описание изображения" href="https://sun9-41.userapi.com/c813024/v813024504/99102/R6lVeobUX3I.jpg"><img src="https://sun9-41.userapi.com/c813024/v813024504/99102/R6lVeobUX3I.jpg" alt=""></a>
            <button class="popup_content">Подробнее</button>							
          </div>

          <div class="blabla coub_work mix category-b" data-order="2"><a class="image-popup-zoom" title="Это описание изображения" href="https://sun9-54.userapi.com/c857428/v857428169/1bcbbb/-lnnuObYl4E.jpg"><img src="https://sun9-54.userapi.com/c857428/v857428169/1bcbbb/-lnnuObYl4E.jpg" alt=""></a>
            <button class="popup_content">Подробнее</button>							
          </div>

          <div class="blabla coub_work mix category-c" data-order="2"><a class="image-popup-zoom" title="Это описание изображения" href="https://sun7-8.userapi.com/asKlovUF13Iyjl4q38CcykrbFy-l2tixh5u41Q/k_MDfBVJ4Gk.jpg"><img src="https://sun7-8.userapi.com/asKlovUF13Iyjl4q38CcykrbFy-l2tixh5u41Q/k_MDfBVJ4Gk.jpg" alt=""></a>
            <button class="popup_content">Подробнее</button>							
          </div>

          <div class="blabla coub_work mix category-b" data-order="2"><a class="image-popup-zoom" title="Это описание изображения" href="https://sun9-54.userapi.com/c857428/v857428169/1bcbbb/-lnnuObYl4E.jpg"><img src="https://sun9-54.userapi.com/c857428/v857428169/1bcbbb/-lnnuObYl4E.jpg" alt=""></a>
            <button class="popup_content">Подробнее</button>							
          </div>

          <div class="blabla coub_work mix category-a" data-order="2"><a class="image-popup-zoom" title="Это описание изображения" href="https://sun9-41.userapi.com/c813024/v813024504/99102/R6lVeobUX3I.jpg"><img src="https://sun9-41.userapi.com/c813024/v813024504/99102/R6lVeobUX3I.jpg" alt=""></a>
            <button class="popup_content">Подробнее</button>							
          </div>

          <div class="blabla coub_work mix category-b" data-order="2"><a class="image-popup-zoom" title="Это описание изображения" href="https://sun7-8.userapi.com/asKlovUF13Iyjl4q38CcykrbFy-l2tixh5u41Q/k_MDfBVJ4Gk.jpg"><img src="https://sun7-8.userapi.com/asKlovUF13Iyjl4q38CcykrbFy-l2tixh5u41Q/k_MDfBVJ4Gk.jpg" alt=""></a>
            <button class="popup_content">Подробнее</button>							
          </div>

          <div class="blabla coub_work mix category-c" data-order="2"><a class="image-popup-zoom" title="Это описание изображения" href="https://sun9-41.userapi.com/c813024/v813024504/99102/R6lVeobUX3I.jpg"><img src="https://sun9-41.userapi.com/c813024/v813024504/99102/R6lVeobUX3I.jpg" alt=""></a>
            <button class="popup_content">Подробнее</button>							
          </div>


          <div class="blabla coub_work mix category-b" data-order="2"><a class="image-popup-zoom" title="Это описание изображения" href="https://sun9-54.userapi.com/c857428/v857428169/1bcbbb/-lnnuObYl4E.jpg"><img src="https://sun9-54.userapi.com/c857428/v857428169/1bcbbb/-lnnuObYl4E.jpg" alt=""></a>
            <button class="popup_content">Подробнее</button>							
          </div>

        </div>

        <button class="btn btn-more">Read more</button>

      </div>

    </div>
  </section>  
</template>

<script>
import 'magnific-popup'
import $ from "jquery";
import mixitup from 'mixitup';

export default {
  watch: {
  },
  methods: {
    magnificPopup(){
      (function($) {
        $('.image-popup-zoom').magnificPopup({
          mainClass: 'mfp-zoom-in',
          type: 'image',
          tLoading: '',
          gallery:{
            enabled:true,
            tCounter: '%curr% из %total%',
          },
          removalDelay: 300,
          callbacks: {
            beforeChange: function() {
              this.items[0].src = this.items[0].src + '?=' + Math.random(); 
            },
            open: function() {
              $.magnificPopup.instance.next = function() {
                var self = this;
                self.wrap.removeClass('mfp-image-loaded');
                setTimeout(function() { $.magnificPopup.proto.next.call(self); }, 120);
              }
              $.magnificPopup.instance.prev = function() {
                var self = this;
                self.wrap.removeClass('mfp-image-loaded');
                setTimeout(function() { $.magnificPopup.proto.prev.call(self); }, 120);
              }
            },
            imageLoadComplete: function() { 
              var self = this;
              setTimeout(function() { self.wrap.addClass('mfp-image-loaded'); }, 16);
            }
          }
        });

        $(".coub_work").hover(function(){
          $(this).children(".popup_content").css("opacity","1");
          $(this).children(".image-popup-zoom").children("img").css("opacity","0.4");
          $(this).css("background-color","black");
        },function(){
          $(this).children(".popup_content").css("opacity","0");
          $(this).children(".image-popup-zoom").children("img").css("opacity","")
          $(this).css("background-color","");
        });

        $(".popup_content").on('click',function(){
          $(this).parent().children(".image-popup-zoom").children("img").trigger("click");
        });

      })($);
    },
    mixitup(){
      mixitup('.portfolio-content__items');
    }
  },
  create(){
    this.animateScrollTo();
  },
  mounted() {
    this.magnificPopup();
    this.mixitup();
  },
}
</script>

<style lang="scss" type="text/scss">
  @import "../style/main.scss";
  @import "../style/portfolio.scss";
</style>