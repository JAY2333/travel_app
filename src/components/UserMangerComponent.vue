<template>
<div>
  <el-breadcrumb separator-class="el-icon-arrow-right">
    <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
    <el-breadcrumb-item>活动管理</el-breadcrumb-item>
    <el-breadcrumb-item>活动列表</el-breadcrumb-item>
    <el-breadcrumb-item>活动详情</el-breadcrumb-item>
  </el-breadcrumb>
  <div style="margin: 10px 0">
    <el-button type="primary">新增<i class="el-icon-circle-plus-outline"></i></el-button>
    <el-button type="danger">批量删除<i class="el-icon-remove-outline"></i></el-button>
    <el-button type="primary">导出<i class="el-icon-top"></i></el-button>
  </div>
  <el-table
    :row-class-name="tableRowClassName"
    :data="tableData.filter(data => !search || data.name.toLowerCase().includes(search.toLowerCase()))"
    style="width: 100%;margin-top:10px;">
    <el-table-column
      label="Date"
      prop="date">
    </el-table-column>
    <el-table-column
      label="Name"
      prop="name">
    </el-table-column>
    <el-table-column
      align="right">
      <template slot="header" slot-scope="{}">
        <el-input
          v-model="search"
          size="mini"
          placeholder="输入关键字搜索"/>
      </template>
      <template slot-scope="scope">
        <el-button
          size="mini"
          @click="handleEdit(scope.$index, scope.row)">Edit</el-button>
        <el-popover
                    placement="top"
                    width="160"
                    v-model="scope.row.visible">
            <p>确定删除吗？</p>
            <div style="text-align: right; margin: 0">
                <el-button size="mini" type="text" @click="scope.row.visible = false">取消</el-button>
                <el-button type="text" size="mini"  @click="handleDelete(scope.$index,scope.row)">确定</el-button>
            </div>
            <el-button size="mini" type="danger" slot="reference">删除</el-button>
        </el-popover>
    </template>
    </el-table-column>
  </el-table>
  <el-pagination style="margin : 50px 0 0 200px"
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
      :current-page="currentPage4"
      :page-sizes="[7, 14, 21, 28]"
      :page-size="7"
      layout="total, sizes, prev, pager, next, jumper"
      :total="400">
    </el-pagination>
</div>
</template>
<script>
export default {
  name: 'UserMangerComponent',
  methods: {
    tableRowClassName ({ row, rowIndex }) {
      if ((rowIndex % 2) !== 0) {
        if (Math.round(Math.random()) === 0) {
          return 'warning-row'
        } else {
          return 'success-row'
        }
      }
      return ''
    },
    handleEdit (index, row) {
      console.log(index, row)
    },
    handleDelete (index, row) {
      row.visible = false
      console.log(index, row)
    }
  },
  data () {
    return {
      visible: false,
      tableData: [
        {
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄'
        }, {
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1516 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄'
        }],
      search: ''
    }
  }
}
</script>
<style>
  .el-table .warning-row {
    background: oldlace;
  }

  .el-table .success-row {
    background: #f0f9eb;
  }
</style>
