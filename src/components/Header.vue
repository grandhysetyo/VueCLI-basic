<template>
    <header>
      <img alt="Vue logo" src="../assets/logo.png" width="100">
      <h3>Mobile Legend: Bang Bang</h3>
      <!-- Event Handling Click to method changeHero Parent using emit-->
      <button v-on:click="$emit('ganti-hero')">Ganti Hero</button>
    </header>
</template>

<script>
export default {
    
}
</script>