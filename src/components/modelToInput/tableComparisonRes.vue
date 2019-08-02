<template>
  <div class="">
    <el-table
      :data="listData"
      :span-method="objectSpanMethod"
      class="tableArea"
      style="width: 100%">
      <el-table-column
        prop="type"
        label="序号"
        align="center"
        width="200"/>
      <el-table-column
        prop="sheetType"
        label="工单类型"
      />
      <el-table-column
        prop="taskKey"
        label="taskKey"
      />
      <el-table-column
        prop="templateUrl"
        label="templateUrl"
      />
      <el-table-column
        label="操作"
      >
        <template slot-scope="scope">
          <el-tooltip class="item" effect="dark" content="修改" placement="top-start">
            <i class="el-icon-edit-outline" @click="modify(scope)"/>
          </el-tooltip>
          <el-tooltip class="item" effect="dark" content="删除" placement="top-start">
            <i class="el-icon-delete" @click="deleteData(scope)"/>
          </el-tooltip>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>
<script>

  export default {
    name: 'myNeedDeal',
    data () {
      return {
        rowList: [],
        spanArr: [],
        position: 0,
        listData: []
      }
    },

    methods: {
      queryData () { // 查询操作
        this.listData = [
          {
            id: 1,
            type: 1,
            sheetType: '事件单',
            taskKey: 'shijian_01',
            templateUrl: '/shijian_01'
          },
          {
            id: 2,
            type: 1,
            sheetType: '事件单',
            taskKey: 'shijian_02',
            templateUrl: '/shijian_02'
          },
          {
            id: 3,
            type: 1,
            sheetType: '事件单',
            taskKey: 'shijian_03',
            templateUrl: '/shijian_04'
          },
          {
            id: 22,
            type: 1,
            sheetType: '事件单',
            taskKey: 'shijian_02',
            templateUrl: '/shijian_02'
          },
          {
            id: 4,
            type: 2,
            sheetType: '问题单',
            taskKey: 'wenti_01',
            templateUrl: '/wenti_01'
          },
          {
            id: 5,
            type: 2,
            sheetType: '问题单',
            taskKey: 'wenti_02',
            templateUrl: '/wenti_02'
          },
          {
            id: 6,
            type: 2,
            sheetType: '问题单',
            taskKey: 'wenti_03',
            templateUrl: '/wenti_03'
          },
          {
            id: 21,
            type: 3,
            sheetType: '问题单',
            taskKey: 'wenti_03',
            templateUrl: '/wenti_03'
          }
        ]
        this.rowspan()
        console.log(this.spanArr, 'this.spanArr')
      },
      rowspan () {
        this.listData.forEach((item, index) => {
          if (index === 0) {
            this.spanArr.push(1)
            this.position = 0
          } else {
            if (this.listData[index].type === this.listData[index - 1].type) {
              this.spanArr[this.position] += 1
              this.spanArr.push(0)
            } else {
              this.spanArr.push(1)
              this.position = index
            }
          }
        })

      },
      objectSpanMethod ({row, column, rowIndex, columnIndex}) {  //表格合并行
        if (columnIndex === 0) {
          const _row = this.spanArr[rowIndex]
          const _col = _row > 0 ? 1 : 0
          return {
            // 1代表：独占一行
            // 更大的自然数：代表合并了若干行
            // 0：代表“消失”的哪那一个单元格，后面的单元格向前推一格
            // 表示这个单元格占几横 代表合并行的行数，_row的值要么是1，或者更大的自然正整数，要么是0。
            rowspan: _row,

            colspan: _col
          }
        }
//        if (columnIndex === 1) {
//          const _row = this.spanArr[rowIndex]
//          const _col = _row > 0 ? 1 : 0
//          return {
//            rowspan: _row,
//            colspan: _col
//          }
//        }
      }
    },
    mounted () {
      this.queryData()
    }
  }
</script>
<style lang="scss" scoped>
  .el-select {
    margin-right: 15px;
  }

  .el-input {
    margin-right: 15px;
    width: 200px;
  }

  .tableArea {
    margin-top: 20px;
    box-shadow: 0 0 8px 0 #aaa;
  }

  i[class^="el-icon"] {
    margin-right: 5px;
    font-size: 16px;
    cursor: pointer;
  }

  .modify_table {

  td {
    padding: 10px;
  }

  }
  .item_title {
    text-align: right;
  }
</style>

