<template>
<h1>Welcome to Victims</h1>
  <div class="container-fluid">
    <div class="row row-cols-1 row-cols-md-2 g-4">
      <div class="col" v-for="debt in debts" :key="debt.id">
        <div class="card h-100">
          <img :src="getAvatar(debt)" class="card-img-top" :alt="debt.firstName">
          <div class="card-body">
            <h5 class="card-title">{{ debt.firstName }} </h5>
            <p class="card-text">
              {{ debt.firstName }} hat {{ debt.debts }} Euro Schulden.
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
      debts: [
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
        return require('../assets/logo.png')
      } else if (debt.gender === 'FEMALE') {
        return require('../assets/logo.png')
      }
    }
  }
}
</script>

<style scoped>

</style>
