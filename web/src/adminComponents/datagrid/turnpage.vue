<template>
    <div class="block">
      <el-pagination
        @size-change="handleSizeChange"
        @current-change="handleCurrentChange"
        :current-page="currentPage"
        :page-size="10"
        layout="total, prev, pager, next, jumper"
        :total="total">
      </el-pagination>
    </div>
</template>

<script>
  import http from '../../utils/httpClient.js'

  export default {
    methods: {
      handleSizeChange(val) {
        console.log(`每页 ${val} 条`);
      },
      handleCurrentChange(val) {

        var self = this;
        self.currentPage = val;
        self.params.pageNumber = val;
        console.log(self.params.pageNumber)
      }
    },
    data() {
      return {
        currentPage: 1
      };
    },
    props:['total','params']
  }
</script>