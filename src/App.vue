<template>
  <div id="app">
    <!-- Call Component -->
    <header-component v-on:ganti-hero="changeHero"></header-component>
    <main>
      <Hero v-bind:hero="data"></Hero>
      <Hero v-bind:hero="data2"></Hero>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
// Import Component
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Hero from './components/Hero.vue'

export default {
  name: 'App',
  components:{                    // Inisiasi Component
    'header-component' : Header,
    Footer,
    Hero
  },
  data: function() {
    return{
      data:{
        name: 'Zilong',
        type: 'Fighter',
        image: 'zilong.jpg'
      },
      data2:{
        name: 'Akai',
        type: 'Tank',
        image: 'akai.jpg'
      }
    }
  },
  methods: {
        changeHero: function(){
            this.data.name = 'Aurora'
            this.data.type = 'Mage'
            this.data.image = 'aurora.jpg'

            this.data2.name = 'Aurora'
            this.data2.type = 'Mage'
            this.data2.image = 'aurora.jpg'
        }
    }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
