<template>
  <div class="container">
    <div class="row">
      <div v-for="pokemon in pokedex" :key="pokemon.id" class="col-md-4">
        <Pokemon :pokemon="pokemon"/>
      </div>
    </div>
  </div>
</template>

<script>
import api from "@/api";
import Pokemon from "@/components/Pokemon";

export default {
  components: { Pokemon
  },
  data() {
    return {
      pokedex: [],
    };
  },
  created() {
    api.getPokedex().then(response => {
      this.pokedex = response.data;
    });
  }
};
</script>

<style scoped lang="scss">
.spinner {
  font-size: 7rem;
  text-align: center;
}
</style>
