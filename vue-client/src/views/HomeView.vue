<template>
  <div class="home">
    <Blog/>
  </div>
</template>

<script>
// @ is an alias to /src
import Blog from "@/components/Blog.vue";

export default {
  name: 'HomeView',
  components: {
    Blog,
  }
}
</script>
