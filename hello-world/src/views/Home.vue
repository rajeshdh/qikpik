<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/>
    <h1>This is home page</h1> -->
    <BitcoinPrice />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import BitcoinPrice from '@/components/BitcoinPrice.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld,
    BitcoinPrice
  }
}
</script>
