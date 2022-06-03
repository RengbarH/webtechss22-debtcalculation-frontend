<template>
<h1>Welcome to Victims</h1>
  <div class="container-fluid">
    <div class="row row-cols-1 row-cols-md-4 g-4">
      <div class="col" v-for="creditor in creditors" :key="creditor.id">
        <div class="card h-100">
          <img :src="getAvatar(creditor)" class="card-img-top" :alt="creditor.firstName">
          <div class="card-body">
            <h5 class="card-title">{{ creditor.firstName }} </h5>
            <p class="card-text">
              {{ creditor.firstName }} hat {{ creditor.debts }} Euro Schulden.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'VictimView',
  data () {
    return {
      creditors: [
        {
          id: 1,
          firstName: 'Max',
          debts: 2.0,
          gender: 'MALE'
        },
        {
          id: 2,
          firstName: 'Maxima',
          debts: 3.0,
          gender: 'FEMALE'
        }
      ]
    }
  },
  methods: {
    getAvatar (debt) {
      if (debt.gender === 'MALE') {
        return require('../assets/man.png')
      } else if (debt.gender === 'FEMALE') {
        return require('../assets/woman.png')
      }
    }
  }
}
</script>

<style scoped>

</style>
