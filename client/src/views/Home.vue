<template>
  <div>
    <hello-world />
    <hello-world />
    <hello-world />
    <hello-world />
  </div>
</template>

<script>
  import HelloWorld from '../components/HelloWorld'

  export default {
    name: 'Home',

    components: {
      HelloWorld,
    },
  }
</script>

<style >
@import url('https://fonts.googleapis.com/css2?family=Titillium+Web:wght@300&display=swap');

body {
  font-family: 'Titillium Web', sans-serif;
}
</style>
