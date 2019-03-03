<template>
  <div>
    <ParentTable :tableData="tableData" :columns="columns">
      <template slot-scope="{ row }" slot="name">
        <strong>{{ row.name }}</strong>
      </template>
      <template slot-scope="{ row }" slot="action">
        <strong>{{ row.address }}</strong>
      </template>
    </ParentTable>
  </div>
</template>
<script>
import ParentTable from './ParentTable.vue'
export default {
  name: 'Demo',
  data() {
    return {
      tableData: [
        {
          name: 'John Brown',
          age: 18,
          address: 'New York No. 1 Lake Park'
        },
        {
          name: 'Jim Green',
          age: 24,
          address: 'London No. 1 Lake Park'
        },
        {
          name: 'Joe Black',
          age: 30,
          address: 'Sydney No. 1 Lake Park'
        },
        {
          name: 'Jon Snow',
          age: 26,
          address: 'Ottawa No. 2 Lake Park'
        }
      ],
      columns: [
        {
          label: 'Name',
          slot: 'name'
        },
        {
          label: 'Age',
          key: 'age'
        },
        {
          label: 'Address',
          key: 'address'
        },
        {
          label: 'Action',
          slot: 'action',
          width: 150,
          align: 'center'
        }
      ]
    }
  },
  components: {
    ParentTable
  }
}
</script>
<style scoped>
</style>
