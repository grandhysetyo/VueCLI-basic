<template>
    <ul>
        <li>
          <img v-bind:src="image" alt="">
          <p>{{index+1}}</p>
          <p>Nama : {{hero.name}}</p>
          <p>Jenis Hero : {{hero.type}}</p>
        </li>
      </ul>
</template>

<script>
export default {
    props: ['hero', 'index'],
    computed: {
        image: function(){
            return require('../assets/hero/' + this.hero.image)
        }
    }
}
</script>

// Style scoped untuk local css khusus Hero.vue
<style scoped>
p{
    color: blue;
}
li {
    list-style: none;
}
</style>