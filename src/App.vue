<script>
import { RouterLink, RouterView } from "vue-router";

export default {
  components: {
    RouterLink,
    RouterView
  }
}
</script>
<template>
  <div>
    <RouterLink to="/myassignment">Assignment</RouterLink><br>
    <RouterLink to="/about">About</RouterLink><br>
    <RouterLink to="/">Home</RouterLink><br>
    <RouterLink to="/blog">Blog</RouterLink>
    <RouterView/>
  </div>
</template>
