<template>
  <div id="app">
    <!-- Call Component -->
    <header-component v-on:ganti-hero="changeHero"></header-component>
    <main>
      <Hero v-bind:hero="data"></Hero>
      <Hero v-bind:hero="data2"></Hero>
      <h3>Perulangan</h3>
      <div v-for="item in data3" :key="item.id">
        <Hero v-bind:hero="item"></Hero>
      </div>
      <!-- atau -->
      <h3>Hero Terbaik</h3>
      <article v-if="!selectedHero">
        <Hero v-for="(item,index) in data3" v-bind:hero="item" :key="item.id" v-bind:index="index"> </Hero>
      </article>
      <article>
        <Hero v-bind:hero="selectedHero" :key="selectedHero.id" v-bind:index="0"> </Hero>
      </article>
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
      },
      data3: [
        {
          id: 1,
          name: 'Bruno',
          type: 'Marksman',
          image: 'bruno.jpg'
        },
        {
          id: 2,
          name: 'Gatotkaca',
          type: 'Tank',
          image: 'gatotkaca.png'
        }
      ],
      selectedHero: ''
    }
  },
  methods: {
        changeHero: function(){
            this.selectedHero = this.randomHero()
        },
        randomHero(){
          return this.data3[Math.floor(Math.random() * this.data3.length)]
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
main {
  text-align: center;
}
article {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
