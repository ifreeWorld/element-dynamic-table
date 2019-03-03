<template>
  <div>
    <el-table :data="tableData">
      <template v-for="(column, index) in columns">
        <template v-if="column.slot">
          <el-table-column :key="index" :label="column.label">
            <template slot-scope="{ row }">
              <TableSlot :row="row" :column="column" :index="index"></TableSlot>
            </template>
          </el-table-column>
        </template>
        <template v-else>
          <el-table-column :key="index" :prop="column.key" :label="column.label">
          </el-table-column>
        </template>
      </template>
    </el-Table>
  </div>
</template>
<script>
import TableSlot from './slot.js'
export default {
  name: 'ChildTable',
  data() {
    return {
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
    TableSlot
  }
}
</script>
<style scoped>

</style>
