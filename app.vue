<template>
  <div>
    <NavBar />
    <div class="container p-4 m-auto text-sm mt-10">
      <NuxtPage />
    </div>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue';

export default {
  name: 'App',
  components: {
    NavBar,
  },
};
</script>
