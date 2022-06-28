<template>
<h1>Welcome to Victims</h1>
<victims-card-list :creditors="this.creditors"></victims-card-list>
<button-collapse></button-collapse>
</template>

<script>
import VictimsCardList from '@/components/VictimsCardList'
import ButtonCollapse from '@/components/ButtonCollapse'
export default {
  name: 'VictimView',
  components: { ButtonCollapse, VictimsCardList },
  data () {
    return {
      creditors: []
    }
  },
  mounted () {
    const endpoint = process.env.VUE_APP_BACKEND_BASE_URL + '/api/v1/creditor'
    const requestOptions = {
      method: 'GET',
      redirect: 'follow'
    }

    fetch(endpoint, requestOptions)
      .then(response => response.json())
      .then(result => result.forEach(creditor => {
        this.creditors.push(creditor)
      }))
      .catch(error => console.log('error', error))
  }
}
</script>

<style scoped>

</style>
