<template>
  <div class="card padbottom">
    <h5 class="card-title">{{ pokemon.english_name }}</h5>
    <h6 class="card-subtitle mb-2 text-muted">#{{ pokemon.pokedex_number }}</h6>
  </div>
</template>

<script>
export default {
  props: {
    pokemon: {
      type: Object,
      required: true
    }
  },
  computed: {
    id() {
      return this.pokemon.english_name
    },
    href() {
      return "#" + this.pokemon.english_name
    }
  }
};
</script>

<style lang="scss">

#padbottom {
  padding-bottom: 30px;
}
</style>