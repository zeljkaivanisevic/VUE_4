<template>
  <div class="row">
    <div class="col-8">

      <div v-if="authenticated">
        <InstagramCard :key="card.id" :info="card" v-for="card in filteredCards" />
      </div>

    </div>
    <div class="col-4">
      Trazimo sljedece: {{ searchTerm }}
    </div>
  </div>
</template>

<script>
import InstagramCard from '@/components/InstagramCard.vue'
import store from '@/store.js'
export default {
  data () {
    return store;
  },
  computed: {
    filteredCards () {
      // let filtered = []
      // for(let card of this.cards) {
      //   if (card.title.includes(this.searchTerm)) {
      //     filtered.push(card)
      //   }
      // }
      // return filtered;
      return this.cards.filter(card => card.title.includes(this.searchTerm));
    }
  },
  name: 'home',
  components: {
    InstagramCard
  }
}
</script>

<style lang="scss">
.card-body {
  padding: 0px;
}
img:hover {
  cursor: pointer;
}
</style>
© 2019 GitHub, Inc.
Terms
Privacy
Security
Status
Help
Contact GitHub
Pricing
API
Training
Blog
About
