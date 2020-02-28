<template>
  <div class="container">
  <no-ssr>
    <carousel v-if="!isServer" >
      <slide>
        Slide 1 Content
      </slide>
      <slide>
        Slide 2 Content
      </slide>
  </carousel>
  </no-ssr>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  data() {
    return {
      isServer: 'null'
    }
  },
  created() {
    this.isServer = process.server;
    console.log(process.server);
  },
  mounted() {
    console.log(process);
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
