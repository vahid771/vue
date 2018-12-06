<template>
  <div class="home">
    <img alt="Vue logo" :src="`${baseUrl}logo.png`">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  data () {
    return {
      baseUrl: process.env.BASE_URL,
      image: 'a.jpg'
    }
  },
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>
