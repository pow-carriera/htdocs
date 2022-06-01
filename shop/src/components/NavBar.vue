<template>
  <div class="navbar">
    <div class="topnav">
      <a class="active" href="#home">Home</a>
      <a href="#news">News</a>
      <a href="#contact">Contact</a>
      <a href="#about">About</a>
    </div>
  </div>
</template>
<script>
export default {
  name: 'NavBar',
  props: {
    msg: String
  }
}
</script>