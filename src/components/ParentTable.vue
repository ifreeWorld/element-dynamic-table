<template>
  <div>
    <ChildTable :tableData="tableData" :columns="columns"></ChildTable>
  </div>
</template>
<script>
import ChildTable from './ChildTable.vue'
export default {
  name: 'ParentTable',
  data() {
    return {}
  },
  provide() {
    return {
      tableRoot: this
    }
  },
  props: {
    tableData: {
      type: Array,
      default() {
        return []
      }
    },
    columns: {
      type: Array,
      default() {
        return []
      }
    }
  },
  components: {
    ChildTable
  }
}
</script>
<style scoped>
</style>
