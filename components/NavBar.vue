<template>
  <nav class='bg-gray-dark'>
    <ul class='flex space-x-4 container m-auto p-4'>
      <li v-for='item in navItems' :key='item.name'>
        <a class='font-sans text-blue text-stone-700 font-medium uppercase transition duration-300 hover:text-white' :href="item.url">{{ item.name }}</a>
      </li>
    </ul>
  </nav>
</template>

<script>
import { navItems } from '~/data';
export default {
  name: 'NavBar',
  data() {
    return {
      navItems: navItems,
    };
  },
};
</script>
