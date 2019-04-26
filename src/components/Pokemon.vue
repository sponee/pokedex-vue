<template>
  <div class="card padbottom">
    <h5 class="card-title">{{ pokemon.english_name }}</h5>
    <h6 class="card-subtitle mb-2 text-muted">#{{ pokemon.pokedex_number }}</h6>
    <div class="ball"><div class="button"></div></div>
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

/* Pokeball */

.ball {
  position: relative;
  width: 200px;
  min-width: 50px;
  height: 200px;
  min-heigh: 50px;
  margin: 30px auto;
  border-radius: 50%;
  border: solid;
  background-image: -webkit-linear-gradient(-90deg, #D00 45%, #333 45%, #3f3f3f 50%, #333 55%, #FFF 55%);
}

.button {
  position: absolute;
  width: 20%;
  height: 20%;
  background-color: #FFF;
  border-radius: 50%;
  box-shadow: 0 0 0 3px #666, 0 0 0 10px #fff, 0 0 0 16px #3f3f3f;
  margin: 40%;
}

.button:hover {
  cursor: pointer;
}

</style>