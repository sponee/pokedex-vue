<template>
  <div class="home">
    <Pokedex/>
  </div>
</template>

<script>
// @ is an alias to /src
import Pokedex from "@/components/Pokedex.vue";

export default {
  name: "home",
  components: {
    Pokedex
  }
};
</script>
