<template>
  <div id="app">
    <the-hero />
  </div>
</template>

<script>
import TheHero from '~/components/TheHero.vue'

export default {
  components:{
    TheHero,
  },
  data: function() {
    return {
    }
  },
  created: function() {

  },
  mounted: function() {
    // SmoothScroll
    document.querySelectorAll('a[href^="#"]').forEach(function(element){
      element.addEventListener('click', function(e){
        e.preventDefault();
        const targetY = this.hash ? document.querySelector(this.hash).getBoundingClientRect().top : 0;
        const currentY = window.pageYOffset;
        const adjustY = 50;
        const top = targetY ? targetY + currentY - adjustY : 0;
        window.scroll({
          top: top,
          behavior: 'smooth'
        });
      });
    });

    window.addEventListener('scroll', this.handleScroll)
  },
  destroyed: function() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    
  },
  computed:{
    
  }
}
</script>
