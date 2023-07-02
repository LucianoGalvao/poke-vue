<template>
  <div>
    <section class="text-center border-b pb-4 mb-4">
      <img
        class="mx-auto mb-10"
        :src="`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${route.params.slug}.svg`"
      />
      <h1 class="capitalize text-3xl font-bold">{{ pokemon.name }}</h1>
      <ul class='flex justify-center space-x-4 mt-10'>
        <li
          :class="`uppercase p-1 px-4 rounded-lg font-bold ${item.type.name}`"
          v-for="(item, index) in pokemon.types"
          :key="index"
        >
          {{ item.type.name }}
        </li>
      </ul>
    </section>
    <div>
      Habilidades:
      <ul>
        <li
          class="capitalize"
          v-for="(item, index) in pokemon.abilities"
          :key="index"
        >
          {{ item.ability.name }}
        </li>
      </ul>
    </div>
    <div>Altura: {{ pokemon.height }}</div>
    <div>Peso: {{ pokemon.weight }}</div>
    <div>
      Movimentos:
      <ul>
        <li
          class="capitalize"
          v-for="(item, index) in pokemon.moves"
          :key="index"
        >
          <p v-if="index <= 4">
            {{ item.move.name.replace(/-/g, ' ') }}
          </p>
        </li>
      </ul>
    </div>
    <div>
      Status base:
      <ul>
        <li
          class="capitalize"
          v-for="(item, index) in pokemon.stats"
          :key="index"
        >
          {{ item.stat.name.replace(/-/g, ' ') }}: {{ item.base_stat }}
        </li>
      </ul>
    </div>
  </div>

  <NuxtLink to="/pokemons">Voltar</NuxtLink>
</template>

<script setup>
const route = useRoute();

const url = `https://pokeapi.co/api/v2/pokemon/${route.params.slug}`;

const { data: pokemon } = await useFetch(url);

</script>
