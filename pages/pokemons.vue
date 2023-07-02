<template>
  <div>
    <ul class="flex flex-wrap">
      <li
        class="uppercase border-solid border-black border-2 rounded-lg w-[calc(25%-1rem)] h-auto max-w-xs mx-4 mb-6 text-center transition duration-300 hover:shadow-xl"
        v-for="(item, index) in pokemon.results"
        :key="item.name"
      >
        <NuxtLink :to="`/pokemon/${index + 1}`" class="card w-full block p-8">
          <img
            class="mx-auto mb-4 w-40 h-40 duration-300"
            :src="`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${
              index + 1
            }.svg`"
            :alt="item.name"
          />
          <p class="text-lg font-bold">
            {{ item.name }}
          </p>
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script setup>
const url = useState(
  'url',
  () => `https://pokeapi.co/api/v2/pokemon?limit=151`
);

const { data: pokemon } = await useFetch(url);

</script>
<style>
  @import '~/assets/css/main.scss';
</style>