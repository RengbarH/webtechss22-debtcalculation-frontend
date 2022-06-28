<template>
  <div class="card h-100">
    <img :src="getAvatar(creditor)" class="card-img-top" :alt="creditor.firstName + ' ' + creditor.lastName">
    <div class="card-body">
      <h5 class="card-title">{{ creditor.firstName }} {{creditor.lastName}} </h5>
      <p class="card-text">
        {{ creditor.firstName }} hat {{ creditor.debtors.length }} Schuldner.
      </p>
      <button type="button" class="btn btn-primary">TestButton</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'VictimCard',
  props: {
    creditor: {
      type: Object,
      required: true
    }
  },
  methods: {
    getAvatar (debt) {
      if (debt.gender === 'MALE') {
        return require('../assets/man.png')
      } else if (debt.gender === 'FEMALE') {
        return require('../assets/woman.png')
      } else if (debt.gender === 'DIVERSE') {
        return require('../assets/diverse.png')
      }
    }
  }
}
</script>

<style scoped>
.card-img-top {
  height: 400px;
}

</style>
