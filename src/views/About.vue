<template>
  <div class="about">
    <h1>This is an about page</h1>
    <img alt="Vue logo" :src="image">
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  data () {
    return {
      image: process.env.BASE_URL + "images/avatars/daniel.jpg"
    }
  }
}
</script>