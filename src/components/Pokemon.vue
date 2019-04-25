<template>
  <div class="card padbottom">
    <img class="card-img-top" :src="pokemon.image_url" :alt="pokemon.name.english"></img>
    <h5 class="card-title">{{ pokemon.name.english }}</h5>
    <h6 class="card-subtitle mb-2 text-muted">#{{ pokemon.id }}</h6>
    <div class="card-body">
      <a class="btn btn-primary" data-toggle="collapse" :href="href" role="button" aria-expanded="false" aria-controls="collapseExample">
        Stats
      </a>
    </div>
    <div class="collapse" :id="id">
      <div class="card-body">
        <ul v-for="(stat, statName) in pokemon.base" class="list-group list-group-flush">
          <li class="list-group-item">{{statName}}: {{stat}}</li>
        </ul>
      </div>
    </div>
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
      return this.pokemon.name.english
    },
    href() {
      return "#" + this.pokemon.name.english
    }
  }
};
</script>

<style lang="scss">

#padbottom {
  padding-bottom: 30px;
}
</style>