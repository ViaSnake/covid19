<template>
  <v-col cols="12" md="6" class="DataCard">
    <svg-card
      id="details-of-confirmed-cases"
      :title="$t('検査陽性者の状況')"
      :title-id="'details-of-confirmed-cases'"
      :date="Data.inspections_summary.date"
    >
      <confirmed-cases-table
        :aria-label="$t('検査陽性者の状況')"
        v-bind="confirmedCases"
      />
    </svg-card>
  </v-col>
</template>

<script>
import Data from '@/data/data.json'
import formatConfirmedCases from '@/utils/formatConfirmedCases'
import SvgCard from '@/components/SvgCard.vue'
import ConfirmedCasesTable from '@/components/ConfirmedCasesTable.vue'

export default {
  components: {
    SvgCard,
    ConfirmedCasesTable
  },
  props: {
    graphData: {
      type: Object,
      required: false,
      default: Data
    }
  },
  data() {
    // 検査陽性者の状況
    const confirmedCases = formatConfirmedCases(Data.main_summary)

    const data = {
      Data,
      confirmedCases
    }
    return data
  },
  mounted() {
    this.Data = this.graphData
    this.confirmedCases = formatConfirmedCases(this.graphData.main_summary)
  }
}
</script>
