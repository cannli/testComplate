<template>
  <div>
    <my-table :col="col"
              :data="data">
    </my-table>
  </div>
</template>

<script>
  import MyTable from './components/myTable'

  export default {
    components: {
      MyTable
    },
    data() {
      return {
        col: [
          /*{prop: 'num1', label: ''},
          {
            label: '税费',
            children: [
              {prop: 'num2', label: '税费'},
            ]
          },
          {
            label: '费用',
            children: [
              {prop: 'num3', label: '托管费'},
              {prop: 'num4', label: '技术服务费'},
              {prop: 'num5', label: '信托费'}
            ]
          },
          {prop: 'num6', label: '加权平均利率'},*/
        ],
        data: [
          /* {
             date: '2016-05-03',

             provinceA: '上海A',
             cityA: '普陀区A',
             addressA: '上海市普陀区金沙江路 1518 弄A',

             provinceB: '上海B',
             cityB: '普陀区B',
             addressB: '上海市普陀区金沙江路 1518 弄B'
           },
           {
             date: '2016-05-02',

             provinceA: '上海A2',
             cityA: '普陀区A2',
             addressA: '上海市普陀区金沙江路 1518 弄A2',

             provinceB: '上海B2',
             cityB: '普陀区B2',
             addressB: '上海市普陀区金沙江路 1518 弄B2'
           }*/
        ],

        aaa: [
          {
            cashFlowTypeName: "税费",
            dataList: [{
              taxFeeType: "VALUE_ADDED_TAX",
              taxFeeName: "税费",
              currentPayAmountSum: 0,
              annualRate: 0.00,
              cashFlowType: "TAX",
              feeId: 104
            }]
          },
          {
            cashFlowTypeName: "费用",
            dataList: [
              {
                taxFeeType: "TECHSUPPORT_CONSULTANT_FEE",
                taxFeeName: "技术服务费",
                currentPayAmountSum: 162955.78,
                annualRate: 0.42,
                cashFlowType: "FEE",
                feeId: 103
              }, {
                taxFeeType: "TRUSTEESHIP_FEE",
                taxFeeName: "托管费",
                currentPayAmountSum: 7132.55,
                annualRate: 0.02,
                cashFlowType: "FEE",
                feeId: 102
              }, {
                taxFeeType: "TURST_MANAGEMENT_FEE",
                taxFeeName: "信托费",
                currentPayAmountSum: 285301.73,
                annualRate: 0.73,
                cashFlowType: "FEE",
                feeId: 101
              }]
          },
          {
            cashFlowTypeName: "加权平均利率",
            dataList: [{
              taxFeeName: "加权平均利率",
              currentPayAmountSum: "-",
              annualRate: 7.56,
              cashFlowType: "加权平均利率"
            }]
          }
        ]
      }
    },
    mounted() {
      console.log(this.aaa[1])
      let val = this.aaa
      let head = [{prop: 'num1', label: ''},]
      let data = [{num1: '金额'}, {num1: '年化%'}]
      let cua = 1
      for (let x in val) {
        head.push({label: val[x].cashFlowTypeName})
        if (val[x].dataList) {
          head[x * 1 + 1].children = []
          let dataList = val[x].dataList
          for (let y in dataList) {
            cua++
            head[x * 1 + 1].children.push(
              {prop: `num${cua}`, label: dataList[y].taxFeeName}
            )
            data[0][`num${cua}`] = dataList[y].currentPayAmountSum
            data[1][`num${cua}`] = dataList[y].annualRate
          }
        }
      }
      alert(cua)
      this.col = head
      this.data = data
      console.log(head, 999999)
    }
  }
</script>
<style>
</style>
