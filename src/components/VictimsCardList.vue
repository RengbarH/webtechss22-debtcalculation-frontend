<template>
  <div class="container-fluid">
    <div class="row row-cols-1 row-cols-md-4 g-4">
      <div class="col" v-for="creditor in creditors" :key="creditor.id">
        <victim-card :creditor="creditor"></victim-card>
      </div>
    </div>
  </div>
</template>

<script>
import VictimCard from '@/components/VictimCard'
export default {
  name: 'VictimsCardList',
  components: { VictimCard },
  props: {
    creditors: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>

</style>
